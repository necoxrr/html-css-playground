# CSS Hover Navigation Animation

一个使用 **CSS3 伪元素 + transform 动画** 实现的导航按钮悬浮动画小项目。

当鼠标悬浮在导航按钮上时，背景颜色会 **从左向右填充**；
当鼠标移开时，背景颜色会 **从右向左收缩消失**，形成流畅的交互动画效果。

---

# 📸 Preview

Hover 进入：

```
|              |
| >>>          |
| >>>>>>>      |
| >>>>>>>>>>>  |
|>>>>>>>>>>>>>>|
```

Hover 离开：

```
|>>>>>>>>>>>>>>|
| >>>>>>>>>>>  |
|   >>>>>>>    |
|      >>>     |
|              |
```

---

# ✨ Features

* 使用 **CSS 伪元素 `::before`** 创建动画背景层
* 使用 **`transform: scaleX()`** 实现高性能动画
* 使用 **`transform-origin` 控制动画方向**
* 使用 **`transition` 实现平滑过渡**
* 不依赖任何 JavaScript

---

# 📂 Project Structure

```
project
│
├── index.html
├── style.css
└── README.md
```

---

# 🧠 Implementation Principle

核心思路：

1️⃣ 使用 `::before` 创建背景层
2️⃣ 使用 `position:absolute` 覆盖按钮区域
3️⃣ 使用 `transform: scaleX()` 控制背景宽度
4️⃣ 使用 `transform-origin` 控制展开方向
5️⃣ 使用 `transition` 实现动画过渡

示例代码：

```css
ul li a::before{
    content: '';
    position: absolute;
    top:0;
    left:0;
    width:100%;
    height:100%;
    transform: scaleX(0);
    transform-origin: right;
    transition: transform 0.5s ease-in-out;
}
```

Hover 时：

```css
ul li a:hover::before{
    transform: scaleX(1);
    transform-origin: left;
}
```

---

# 🎯 Animation Logic

动画分为两个阶段：

### 鼠标进入

```
transform-origin: left
scaleX: 0 → 1
```

效果：

```
背景从左向右填充
```

---

### 鼠标离开

```
transform-origin: right
scaleX: 1 → 0
```

效果：

```
背景从右向左收缩
```

---

# 🚀 Why Use transform Instead of width

使用 `transform` 而不是 `width` 的原因：

| 方法           | 性能         |
| ------------ | ---------- |
| width 动画     | 会触发 layout |
| transform 动画 | GPU 加速     |

因此 `transform` 在动画性能上更优。

---

# 🛠 Technologies Used

* HTML5
* CSS3
* Flexbox
* CSS Transform
* CSS Transition

---

# 📚 Learning Points

通过这个小项目可以学习：

* CSS 伪元素 `::before`
* CSS 动画基础
* `transform-origin` 动画方向控制
* Hover 交互动画设计
* 前端 UI 动画优化

---

# 📈 Possible Improvements

可以扩展的方向：

* 增加图标（FontAwesome）
* 添加响应式布局
* 添加点击动画
* 使用 CSS Variables 管理颜色
* 添加暗黑模式

---

# 📄 L
