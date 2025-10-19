---
id: methods
title: API 方法
layout: default
---

# API

我们提供了一个内容广泛的 JavaScript API，用于控制演示文稿的导航和检查其当前状态。如果您使用的是单个演示文稿实例，则可以通过全局的 `Reveal` 对象来访问该 API。

### 导航

```javascript
// 导航至指定幻灯片
Reveal.slide(indexh, indexv, indexf);

// 相对导航
Reveal.left();
Reveal.right();
Reveal.up();
Reveal.down();
Reveal.prev();
Reveal.next();

// 片段导航
Reveal.navigateFragment(indexf); // (-1 表示隐藏所有片段)
Reveal.prevFragment();
Reveal.nextFragment();

// 检查可导航的所有方向
// {top: false, right: true, bottom: false, left: false}
Reveal.availableRoutes();

// 检查可导航的片段方向
// {prev: false, next: true}
Reveal.availableFragments();
```

### 其他

```javascript
// 添加/删除幻灯片后调用此函数来更新控制与进度等
Reveal.sync();
// 调用此函数仅更新当前幻灯片
Reveal.syncSlide((slide = currentSlide));
// 调用此函数仅更新当前幻灯片的片段
Reveal.syncFragments((slide = currentSlide));

// 调用此函数利用可用视口来更新幻灯片比例
Reveal.layout();

// 随机打乱幻灯片顺序
Reveal.shuffle();

// 获取当前配置选项
Reveal.getConfig();

// 获取当前比例
Reveal.getScale();

// 返回包含缩放后幻灯片尺寸的对象
Reveal.getComputedSlideSize();

Reveal.getIndices((slide = currentSlide)); // 幻灯片索引 (e.g. { h: 0, v: 0, f: 0 })
Reveal.getProgress(); // (0 == 第一张, 1 == 最后一张)

// 包含每一张幻灯片属性（键值对形式）的数组
Reveal.getSlidesAttributes();

// 返回指定幻灯片的背景元素
Reveal.getSlideBackground(indexh, indexv);

// 返回幻灯片的演讲者备注内容
Reveal.getSlideNotes((slide = currentSlide));

// 将请求字符串转换为键值对
Reveal.getQueryHash();

// 返回幻灯片的 URL 路径
Reveal.getSlidePath((slide = currentSlide));
```

### 幻灯片

```javascript
// 返回匹配指定索引的幻灯片元素
Reveal.getSlide(indexh, indexv);

// 获取前一个与当前幻灯片元素
Reveal.getPreviousSlide();
Reveal.getCurrentSlide();

// 返回演示文稿中所有的水平/垂直幻灯片
Reveal.getHorizontalSlides();
Reveal.getVerticalSlides();

// 幻灯片数目
Reveal.getTotalSlides();
Reveal.getSlidePastCount();

// 所有幻灯片数组
Reveal.getSlides();
```

### 幻灯片状态

```javascript
// 检查演示文档是否包含两个或更多
// 水平/垂直幻灯片
Reveal.hasHorizontalSlides();
Reveal.hasVerticalSlides();

// 检查演示文档是否在任一方向导航过至少一次
Reveal.hasNavigatedHorizontally();
Reveal.hasNavigatedVertically();

Reveal.isFirstSlide();
Reveal.isLastSlide();
Reveal.isVerticalSlide();
Reveal.isLastVerticalSlide();
```

### 模式

```javascript
// 展示一个包含键盘快捷键的帮助悬浮窗，可传入 true/false 来强制显示/隐藏
Reveal.toggleHelp();

// 切换演示状态，可传入 true/false 来强制开启/关闭
Reveal.toggleOverview();
Reveal.toggleAutoSlide();
Reveal.togglePause();

Reveal.isOverview();
Reveal.isAutoSliding();
Reveal.isPaused();
```

### DOM 元素

```javascript
// 获取关键 DOM 元素
Reveal.getRevealElement(); // <div class="reveal">
Reveal.getSlidesElement(); // <div class="slides">
Reveal.getViewportElement(); // <div class="reveal-viewport">
Reveal.getBackgroundsElement(); // <div class="backgrounds">
```

## 阅读更多

- [插件 API](/plugins/#api)
