# CSS3 滚动转换效果 (Scroll Transform Effect)

## 项目简介

本项目演示了一个 **CSS3 + JavaScript 的滚动转换效果**，通过监听浏览器滚动事件，使图片（PNG）在页面滚动时发生纵向缩放，从而实现曲线拉伸或压扁的动态视觉效果。  
该效果可用于网页头部、横幅或分隔内容的装饰性动画，提高页面的交互感和视觉美感。

---

## 效果说明

- **页面滚动时**， PNG 图片会随滚动距离进行纵向缩放（scaleY）。
- 支持浏览器自适应宽度，保证响应式显示。
## 技术栈

- HTML5
- CSS3
- JavaScript（原生）

**关键技术点：**

1. CSS3 `display: block` 与 `width: 100%` 保证图片宽度填满父元素。
2. JavaScript `window.scrollY` 监听滚动距离，动态修改 `transform: scaleY()`。

---
- 可通过调整 JavaScript 中的缩放系数控制图片缩放幅度：
    window.addEventListener('scroll', function(){
        var value = 1 + window.scrollY / -900;
        document.querySelector('.curve img').style.transform = `scaleY(${value})`;
    });



