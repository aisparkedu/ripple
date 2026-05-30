<div align="center">

# 💧 Ripple · 手势交互式水波纹

**摄像头 + 手势识别 + WebGL 波动方程** —— 手指在镜头前划过，画面泛起涟漪、折射扭曲，像隔着一层流动的水。

![Three.js](https://img.shields.io/badge/Three.js-WebGL2-000000?logo=three.js&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hands-00897B?logo=google&logoColor=white)
![Single File](https://img.shields.io/badge/single--file-HTML-orange)
![AI Spark](https://img.shields.io/badge/AI%20Spark-开源案例-4ea8ff)

</div>

## 效果

打开摄像头作为背景，手指在镜头前划过的地方产生涟漪并向外扩散、约 1 秒消散；水波会折射、放大、扭曲背后的画面，带彩虹色散边缘和水光高光。静止时画面清晰，手一动才起波。

> 💡 欢迎补充演示 GIF / 截图

## ✨ 特性

- 🌊 **真实水波物理**：FBO ping-pong 双缓冲跑波动方程，9-tap 各向同性拉普拉斯减方形伪影，非线性衰减做出表面张力质感
- ✋ **手势驱动**：MediaPipe Hands 追踪 10 个指尖，capsule SDF（线段）让快速划过的轨迹连续不断点
- 🎨 **丰富光学**：grad 折射 / Laplacian 透镜 / RGB 色散 / Schlick Fresnel / 波深明暗 / 双瓣高光
- ⚡ **性能优化**：1x 渲染 + 640×480 输入 + 手势检测节流，降卡顿、降发热
- 🎛 **实时调参**：右上角面板，十余个滑块实时微调手感
- 📦 **单文件**：纯前端单 HTML，CDN 依赖，无需构建

## 🚀 快速开始

摄像头需要安全上下文，不能直接双击 `.html` 打开，需起本地服务器：

```bash
git clone https://github.com/aisparkedu/ripple.git
cd ripple
python3 -m http.server 8000
```

浏览器打开 <http://localhost:8000>，允许摄像头权限，把手伸到镜头前划动即可。打开后点右上角「参数调校」可实时拖滑块微调。

## 🛠 技术栈

| 模块 | 方案 |
|------|------|
| 渲染 | Three.js (WebGL2) ShaderMaterial |
| 手势识别 | MediaPipe Hands @0.4 |
| 物理模拟 | FBO ping-pong 波动方程 + 9-tap 拉普拉斯 + capsule SDF 注入 |
| 摄像头 | getUserMedia |

## 📝 复现提示词

本项目用 **AI 编程（Vibe Coding）** 完成，附带一份完整的复现提示词 [`prompt.md`](./prompt.md)——复制整段喂给任意 AI 编程工具（Claude / Cursor / bolt.new 等），即可从零生成同款效果，已内置调好的默认参数。

---

## 关于 AI Spark

**AI Spark** 聚焦 AI 实战与超级个体成长，是由一线 AI 实战者维护的**开源知识社区**。我们把真实跑通的经验公开出来——能直接用的工具、Prompt、工作流和案例，让每个想用 AI 的人，都能从「看不懂」走到「跑通第一个工作流」，再走到「靠 AI 提效增收」。普通人不用再花 999 买课，就能拿到一线在用的东西。

本仓库就是 AI Spark 知识库「AI 编程与智能体 / AI 内容创作」模块下的一个实战案例。

📚 **知识库模块**

| | | |
|---|---|---|
| 01 AI 小白入门 | 02 AI 工具与大模型 | 03 AI 编程与智能体 |
| 04 AI 内容创作 | 05 AI 效率提升 | 06 AI 行业观察 |

资料全部公开免费，每周更新。更多开源项目 👉 **[github.com/aisparkedu](https://github.com/aisparkedu)**

<div align="center">
<sub>Made with 💧 by AI Spark · 一线 AI 实战者的开源知识社区</sub>
</div>
