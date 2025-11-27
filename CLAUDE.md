# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个FaceReader Landmarks可视化工具的Web应用，用于2D和3D面部特征点的可视化分析。项目是一个纯前端应用，使用HTML、CSS和JavaScript实现。

## 项目结构

- `index.html` - 主应用文件，包含完整的HTML、CSS和JavaScript代码
- `.claude/settings.local.json` - Claude Code本地设置文件
- `.git/` - Git版本控制目录

## 技术架构

### 前端技术栈
- **HTML5** - 页面结构和语义化标记
- **CSS3** - 响应式样式和动画效果
- **原生JavaScript** - 应用逻辑和交互
- **Three.js** - 3D图形渲染和可视化
- **D3.js** - 2D图形绘制

### 核心功能模块

#### 2D Landmarks可视化
- 使用HTML5 Canvas绘制67个2D面部特征点
- 支持面部轮廓、眉毛、眼睛、鼻子、嘴巴等区域的网格连接
- 提供缩放、平移等基础交互

#### 3D Landmarks可视化
- 使用Three.js渲染468个3D面部特征点
- 支持鼠标拖拽旋转、滚轮缩放等3D交互
- 包含坐标轴辅助和光照系统

#### 交互功能
- Landmark点选择和快速定位
- 坐标信息显示
- 键盘快捷键支持（Enter键跳转）
- 响应式设计适配移动设备

### 数据格式

#### 2D Landmarks
- 67个点，共134个数字 (X1,Y1,X2,Y2,...,X67,Y67)
- 点索引范围：0-66

#### 3D Landmarks
- 468个点，共1404个数字 (X1,Y1,Z1,X2,Y2,Z2,...,X468,Y468,Z468)
- 点索引范围：0-467

## 开发说明

### 运行项目
由于这是一个纯前端项目，可以直接在浏览器中打开`index.html`文件运行：

```bash
# 使用本地服务器运行（推荐）
python -m http.server 8000
# 或
npx serve .

# 直接打开文件
open index.html
```

### 依赖库
项目通过CDN引入以下外部库：
- `d3.v7.min.js` - D3.js数据可视化库
- `three.min.js` - Three.js 3D图形库

### 主要JavaScript函数

- `initPage()` - 页面初始化
- `draw2dLandmarks()` - 绘制2D特征点
- `draw3dLandmarks()` - 绘制3D特征点
- `initThreeScene()` - 初始化Three.js场景
- `loadFirstFrameData()` - 加载示例数据
- `highlightLandmark2d()` / `highlightLandmark3d()` - 高亮选中的特征点

### 样式特点
- 响应式设计，支持移动设备
- 现代化UI设计，使用渐变背景和卡片布局
- 支持深色/浅色主题

## 注意事项

- 项目使用相对路径引用外部库，需要网络连接
- 3D可视化使用WebGL，需要浏览器支持
- 数据格式需要严格按照指定的坐标顺序