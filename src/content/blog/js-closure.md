---
title: "JavaScript闭包"
description: "从“看懂”到“会用”"
pubDate: "Jul 22 2022"
heroImage: "/blog-placeholder-2.jpg"
---

# 引言

闭包（Closure）是 JavaScript 的核心概念之一，常用于封装数据和实现高阶函数。然而，许多初级开发者对其原理和应用场景感到困惑。

## 核心内容

### 闭包的定义

- 简单解释：函数访问其词法作用域（定义时的作用域），即使该函数在其作用域外执行。
- 示例：

```javascript
function outer() {
  const secret = "I am a secret!";
  return function inner() {
    console.log(secret); // inner函数访问outer的作用域
  };
}
const closure = outer();
closure(); // 输出 "I am a secret!"
```

### 闭包的应用场景

- 数据封装：

```javascript
function Counter() {
  let count = 0;
  return {
    increment: () => count++,
    get: () => count,
  };
}
const counter = Counter();
counter.increment();
console.log(counter.get()); // 输出 1
```

- 回调函数：

```javascript
setTimeout(() => {
  console.log("延迟执行");
}, 1000);
```

### 闭包的“陷阱”

- 内存泄漏：闭包会保留对外部作用域的引用，可能导致内存无法释放。
- 解决方案：在不需要时手动解绑引用（如 counter = null）。

### 常见问题

- Q：为什么循环中用闭包输出的索引总是最后一个值？
  - A：闭包共享同一个作用域，建议用 let 声明变量或立即执行函数（IIFE）：
    ```javascript
    for (let i = 0; i < 3; i++) {
      setTimeout(() => {
        console.log(i); // 输出 0, 1, 2
      }, 1000);
    }
    ```
