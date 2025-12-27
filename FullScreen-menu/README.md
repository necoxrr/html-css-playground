# Full Screen Overlay Navigation Menu

这是一个基于 **HTML + CSS + JavaScript** 实现的 **全屏覆盖响应式导航菜单**。  
通过点击右上角的菜单按钮，实现菜单的展开与关闭，适用于个人主页、作品集网站或移动端响应式页面。

---

## ✨ 项目特点

- 🔹 全屏覆盖式导航菜单（Overlay Menu）
- 🔹 CSS `transform: scale()` 实现平滑展开/收起动画
- 🔹 纯原生 JavaScript 控制，无第三方依赖
- 🔹 响应式布局，适配不同屏幕尺寸
- 🔹 悬停菜单项带高亮动画效果
- 🔹 菜单按钮支持切换图标（打开 / 关闭）

---

## 🛠 技术栈

- **HTML5**
- **CSS3**
  - Flex 布局
  - 过渡动画（transition）
  - 伪元素 `::before`
- **JavaScript**
  - DOM 操作
  - `classList.toggle()` 切换状态

---

## 📁 项目结构

FullScreen-menu/
│
├── index.html # 页面结构
├── style.css # 样式文件
├── pp.png # 菜单打开图标
├── close.png # 菜单关闭图标
└── README.md # 项目说明

---

## 🚀 功能说明

### 1️⃣ 菜单切换

点击右上角按钮：
- 菜单从 **scale(0)** 动画放大至 **scale(1)**  
- 背景全屏覆盖
- 按钮图标从菜单图标切换为关闭图标

核心 JS 逻辑：

```js
function toggleMenu(){
    var nav = document.getElementById('munu-overplay');
    nav.classList.toggle('active');
    var toggle = document.getElementById('toggle');
    toggle.classList.toggle('active');
}
2️⃣ 导航菜单动画

- 使用 **flex** 实现菜单居中

- 使用 ::before 伪元素实现菜单项 hover 高亮横线动画

#munu-overplay {
    transform: scale(0);
    transition: 0.5s;
}

#munu-overplay.active {
    transform: scale(1);
}

