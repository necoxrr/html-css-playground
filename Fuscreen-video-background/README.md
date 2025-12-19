# Fuscreen-video-background（全屏视频背景）

## 项目简介

这是一个使用 **HTML5 + CSS3** 实现的「全屏视频背景 Banner」小项目。页面加载后，视频会铺满整个首屏作为背景，文字内容叠加显示在视频之上，常用于官网首页、宣传页或个人展示站点。

---

## 技术点概览

* HTML5 `<video>` 视频标签
* CSS `position` 定位 + `z-index` 层级控制
* `object-fit: cover` 实现视频等比铺满
* Flex 布局实现内容居中
* `vh` 视口单位实现全屏效果

---

## 页面结构说明

```html
<div class="banner">
  <video autoplay muted loop>
    <source src="oceans.mp4" type="video/mp4" />
  </video>
  <div class="content">
    <h1>Fullscreen video background</h1>
    <p>...</p>
  </div>
</div>
```

* `banner`：整体容器，占满整个视口
* `video`：背景视频
* `content`：覆盖在视频上的文字内容

---

## 核心 CSS 解析

### 1️⃣ 让 Banner 占满整个屏幕

```css
.banner {
  width: 100%;
  height: 100vh;
}
```

* `100vh` 表示 **浏览器可视区域高度**
* 无论屏幕多大，首屏始终铺满

---

### 2️⃣ 视频作为“背景”的关键写法

```css
.banner video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

作用解释：

* `position: absolute`：脱离文档流，覆盖整个 banner
* `width / height: 100%`：铺满容器
* `object-fit: cover`：

  * 保持视频比例
  * 裁剪多余部分
  * 类似 `background-size: cover`

---

### 3️⃣ 为什么文字不会被视频盖住？

```css
.banner .content {
  position: relative;
  z-index: 1;
}
```

* 视频默认层级是 `z-index: auto (≈0)`
* 内容层 `z-index: 1` → 显示在视频上方

📌 **层级顺序**：

```
文字内容 (z-index: 1)
──────────────
视频背景 (z-index: 0)
```

---

### 4️⃣ 内容居中显示的原因

```css
.banner {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

* `flex` 让子元素（content）
* **水平 + 垂直同时居中**

这是目前最简单、最常用的居中方案之一。

---

### 5️⃣ 为什么视频无法点击？

```css
pointer-events: none;
```

* 禁止视频响应鼠标事件
* 防止挡住按钮 / 链接
* 提升交互体验

---

## 视频标签属性说明

```html
<video autoplay muted loop>
```

* `autoplay`：自动播放
* `muted`：静音（浏览器强制要求）
* `loop`：循环播放

⚠️ **注意**：

> 大多数浏览器 **不允许非静音视频自动播放**，所以 `muted` 是必须的。

---

## 使用场景

* 官网首页 Banner
* 产品宣传页
* 个人作品集
* 创意展示页面

---

## 项目运行方式

1. 下载项目代码
2. 将 `oceans.mp4` 放在同级目录
3. 使用浏览器直接打开 `index.html`

---



