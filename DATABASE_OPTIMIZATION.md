# 数据库性能优化方案

## 当前性能问题分析

### 1. 画布页面加载慢
- **问题**: 每次加载项目时，先查询项目元数据，再查询所有画布元素
- **影响**: 两次数据库往返，增加延迟

### 2. 项目列表加载慢
- **问题**: 同时查询项目列表和用户积分，两个独立请求
- **影响**: 串行请求增加总加载时间

### 3. 保存操作慢
- **问题**: 每次保存都删除所有元素再重新插入
- **影响**: 大量元素时性能差，数据库负载高

### 4. RLS 策略性能
- **问题**: canvas_elements 的 RLS 策略使用子查询检查权限
- **影响**: 每个元素查询都要额外查询 projects 表

## 优化方案

### 方案 1: 添加数据库索引（已完成 ✅）
当前已有的索引：
- `idx_projects_user_id` - 项目用户查询
- `idx_projects_updated_at` - 项目排序
- `idx_canvas_elements_project_id` - 元素查询

### 方案 2: 使用批量查询和并行请求
优化前端代码，减少数据库往返次数

### 方案 3: 实现增量保存
只更新变化的元素，而不是全部删除重建

### 方案 4: 添加缓存层
使用 React Query 或 SWR 缓存数据

### 方案 5: 优化 RLS 策略
使用更高效的权限检查方式

## 立即可实施的优化

### A. 并行查询（前端优化）
```typescript
// 优化前：串行查询
const projects = await loadProjects();
const credits = await loadCredits();

// 优化后：并行查询
const [projects, credits] = await Promise.all([
  loadProjects(),
  loadCredits()
]);
```

### B. 增量保存（前端优化）
```typescript
// 优化前：删除所有 + 插入所有
await deleteAll();
await insertAll();

// 优化后：只更新变化的
await upsertChanged();
```

### C. 添加 JSONB 索引（数据库优化）
```sql
-- 为 element_data 添加 GIN 索引，加速 JSONB 查询
CREATE INDEX idx_canvas_elements_data ON canvas_elements USING GIN (element_data);
```

### D. 优化 RLS 策略（数据库优化）
```sql
-- 使用 JOIN 代替子查询
CREATE POLICY "Users can view their own canvas elements v2"
  ON canvas_elements
  FOR SELECT
  USING (
    project_id IN (
      SELECT id FROM projects WHERE user_id = auth.jwt()->>'sub'
    )
  );
```

## 预期性能提升

| 优化项 | 预期提升 | 实施难度 |
|--------|---------|---------|
| 并行查询 | 30-50% | 低 |
| 增量保存 | 50-70% | 中 |
| JSONB 索引 | 20-30% | 低 |
| RLS 优化 | 10-20% | 低 |

## 实施顺序

1. ✅ **立即实施**: 并行查询（前端）
2. ✅ **立即实施**: JSONB 索引（数据库）
3. **短期**: 增量保存（前端）
4. **中期**: 添加缓存层
5. **长期**: 考虑使用 Supabase Realtime 实现协作

