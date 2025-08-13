# Memo Enhanced - 优化版间隔重复插件

<p align="center">
  <strong>原版本演示：</strong><br/>
  <img src="https://user-images.githubusercontent.com/1279335/189250105-656e6ba3-7703-46e6-bc71-ee8c5f3e39ab.gif" alt="原版本演示" width="600">
</p>

<p align="center">
  <strong>优化版本演示：</strong><br/>
  <img src="https://raw.githubusercontent.com/issaker/roam-supermemo-release/main/assets/images/%E6%8F%92%E4%BB%B6%E4%B8%BB%E7%AA%97%E5%8F%A3.png" alt="插件主窗口" width="600">
</p>

<p align="center">
  <strong>点阵图管理界面：</strong><br/>
  <img src="https://raw.githubusercontent.com/issaker/roam-supermemo-release/main/assets/images/%E7%82%B9%E9%98%B5%E5%9B%BE%E7%AA%97%E5%8F%A3.jpg" alt="点阵图窗口" width="600">
</p>


> 🙏 **致谢**：本项目基于 [digitalmaster/roam-memo](https://github.com/digitalmaster/roam-memo) 开发，感谢原作者 [@digitalmaster](https://github.com/digitalmaster) 的杰出工作！同时特别感谢 [L-M-Sherlock (Jarrett Ye)](https://github.com/L-M-Sherlock) 老师对渐进阅读学习原理和方法的无私推广，受益匪浅。

一个专为 Roam Research 设计的渐进阅读插件。类似于 [supermemo](https://supermemo.guru/wiki/SuperMemo)，采用科学的记忆算法和制卡流程帮助你高效记忆任何内容。

## ✨ 核心功能

本插件基于科学的间隔重复理论，并围绕一个强大的可视化管理界面构建，旨在提供无缝、高效的渐进阅读和记忆体验。

### 1. 智能可视化排期 - 卡片点阵图 (Card Dot Matrix)
- **全局视野**: 在一个二维点阵图上可视化所有卡片。横坐标代表**优先级**（0-100 范围，数字越大越先学），纵坐标代表**复习间隔**（Y 轴越靠 0 越紧急，0 就是今天）。
- **直观管理**: 通过拖拽 X 轴的偏移和缩放滑块，轻松调整牌组的学习优先级整体的离散分布，从而控制不同牌组的混合穿插的先后和密度。高效管理全局的知识优先级。
- **状态一目了然**: 不同颜色的圆点清晰标识出卡片的复习状态（到期、新卡、未来以及卡片标题等）。
- **牌组优先级管理**: 在点阵图界面可批量调整牌组内卡片顺序与全局位置，支持撤销，方便集中调整学习重点。

### 2. 流畅体验 & 稳定可靠
- **瞬时响应**: 速度经过优化，即使几千张卡片也几乎秒开。
- **高效处理**: 即使面对数千张卡片，插件依然运行流畅，不会影响 Roam 的正常使用。
- **操作撤销**: 优先级滑块下方会自动弹出撤销栏，支持撤销上一步的优先级调整操作，再也不用担心手滑误操作。
- **稳定练习队列**: 会话期间固定练习队列（防“连刷”抖动），避免刷新数据导致的顺序跳变。
- **一键数据清理**: 自动检测并清理“孤立数据”（原块已删除但遗留的练习记录与缓存），保持数据与存储整洁。

### 3. 灵活的练习与牌组管理
- **牌组即标签**: 你的每一个 `#tag` 都是一个独立的牌组，可以进行针对性练习。
- **混合复习模式**: 一键切换到“混合模式”，打破牌组界限，所有到期卡片将根据你的全局优先级进行统一复习，践行渐进阅读理念。
- **每日限制与强化模式**: 自由设定每日学习量。完成目标后，可进入“强化模式”进行额外学习，适合考前冲刺。
- **每日限制规则**: 自动按 75% 到期 + 25% 新卡 分配名额；支持全局混合模式与单组模式分别应用限额；输入 0 表示无限制。
- **标签黑名单**: 可排除指定标签进入系统，插件内部系统字段会自动过滤。

### 4. 经典间隔重复功能
- **FSRS**: 支持业界领先的开源机器学习间隔重复算法：FSRS 算法，让你的记忆事半功倍。
- **文本遮挡 (挖空)**: 使用  `{隐藏内容}` 轻松制作填空题。
- **丰富的快捷键**: 提供全键盘操作流程，让你在复习时无需触碰鼠标。为避免误操作，已经关闭 esc 对主窗口的关闭快捷键，点阵图窗口可以用 esc 快速关闭。
- **问答倒置 (Swap Q/A)**: 可按牌组开启 Answer First 模式，先看答案再回顾问题，适配不同记忆策略。

## 🚀 快速安装

### 方法一：直接使用编译后文件（推荐）

1. 在 Roam Research 中，进入 **Settings** → **Roam Depot**
2. 点击**Developer Extensions** → **Load Extension from URL**
2. 粘贴以下地址：
   ```
   https://raw.githubusercontent.com/issaker/roam-supermemo-release/main/extension.js
   ```
4. 点击 **Load remote extension** 完成安装

### 方法二：从源码构建

1. 克隆仓库：
   ```bash
   git clone https://github.com/issaker/roam-supermemo.git
   cd roam-supermemo
   ```

2. 安装依赖并构建：
   ```bash
   npm install
   npm run build
   ```

3. 同样的设置路径，在 Roam Research 中加载生成的 `extension.js` 文件

## 🐛 问题反馈与功能建议

如有任何问题或建议，可以发送邮件到 issak.m@qq.com 进行反馈。

## 💖 支持项目发展

<div align="center">

如果觉得这个插件对你有帮助，欢迎给我一些激励~

[**💖 爱发电支持开发**](https://ifdian.net/item/185914144ecb11f0abea52540025c377)

**你的每一份支持都是推动项目发展的动力！** ✨

📈 支持资金将用于：
🔧 持续的功能开发与优化  
📚 用户文档与教程制作
🐛 bug修复与技术支持
</div>

## 🎉 致谢与支持
<div align="center">
  
**🙏 特别感谢**：<br/>
原作者 [@digitalmaster](https://github.com/digitalmaster) 创建了这个出色的插件<br/>
原项目地址：[digitalmaster/roam-memo](https://github.com/digitalmaster/roam-memo)<br/>
感谢 [L-M-Sherlock (Jarrett Ye)](https://github.com/L-M-Sherlock) 老师对渐进阅读学习原理和方法的无私推广，让更多人受益

</div>

## 许可证

**专有软件许可证** (Proprietary License)
版权所有 © 2025 issaker. 保留所有权利。
本软件为专有软件，受版权法保护。未经明确书面许可，不得复制、分发、修改或披露本软件及其相关文档。

---

*让学习变得更科学、更高效！🚀*
