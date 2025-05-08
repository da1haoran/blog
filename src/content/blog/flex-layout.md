---
title: "CSS Flex布局完全指南"
description: "轻松实现响应式设计"
pubDate: "Jul 15 2022"
heroImage: "/blog-placeholder-4.jpg"
---

# 引言

Flex 布局（Flexbox）是 CSS 中最强大的布局工具之一，尤其适合一维布局（如导航栏、卡片列表）。

## 核心内容

### Flex 容器与子元素

- 容器属性：

```css
.container {
  display: flex; /* 启用 Flex 布局 */
  flex-direction: row; /* 主轴方向（row/column） */
  justify-content: center; /* 主轴对齐方式 */
  align-items: center; /* 交叉轴对齐方式 */
}
```

- 子元素属性：

```css
.item {
  flex: 1; /* 自动填充剩余空间 */
  margin: 10px; /* 子元素间距 */
}
```

## 实战场景

- 水平居中：

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

- 垂直排列按钮组：

```css .vertical-buttons {
  display: flex;
  flex-direction: column;
}
```

## 响应式设计技巧

- 媒体查询结合 Flex：

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column; /* 小屏下垂直排列 */
  }
}
```

## 常见问题

- Q：Flex 子元素如何设置固定宽度？
  - A：直接指定 width，或使用 flex-shrink: 0 防止压缩。
