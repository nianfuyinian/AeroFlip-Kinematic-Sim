# AeroFlip: 无人机双钩卸货系统仿真 🚁📦

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0-brightgreen)
![Tech Stack](https://img.shields.io/badge/tech-HTML5%20Canvas%20%7C%20Vanilla%20JS-orange)

**AeroFlip** 是一种面向末端物流/特种投递的“极简纯物理”无人机卸货解决方案。本项目是该系统的 2D 运动学与物理逻辑交互式仿真演示平台，旨在直观展示其核心的**差动双索架构**与**重力触发自锁逻辑**。

## 🌟 核心工程亮点

传统的无人机空投往往需要搭载额外的电动舵机、复杂的电控夹爪及传感器，这不仅增加了机载起飞重量（降低续航），还在复杂的户外环境中面临较高的电控失效风险。

AeroFlip 采用**零能耗（Zero-Power）**的纯机械设计思路：
- **自适应脱钩**：利用重力势能与张力变化，触底瞬间机械锁扣自动弹开。
- **差动索倾倒**：利用一长一短两根柔性索的几何长度差，将无人机单纯的“Z轴拉升”运动，巧妙转化为货袋的“翻转倾倒”力矩。
- **高可靠性**：无电子元器件参与卸货执行层，具有极强的环境鲁棒性与高度误差容忍率。

## ⚙️ 运动学状态机 (The 4 Stages)

本仿真系统严谨复刻了 AeroFlip 卸货过程的四个关键物理阶段：

1. **悬吊下降 (Hover & Descend):** 短绳（承重索）受力绷紧，自锁钩咬合，长绳（翻转索）处于松弛状态。
2. **触底脱钩 (Touchdown & Release):** 货袋底部接触接收端基站。短绳瞬间失去张力，纯机械重力钩失去咬合力自动弹开脱落。
3. **拉升倾倒 (Ascend & Invert):** 无人机重新拉升高度。短绳空载，长绳逐渐绷直。当长绳受力时，以货袋底边为支点产生力矩，迫使货袋逆时针翻转，货物受重力作用物理滑落。
4. **空袋起飞 (Departure):** 无人机继续上升，长绳将空货袋整体拔起，呈稳定倒挂姿态随无人机返航。

## 🚀 快速开始 (Quick Start)

本项目采用纯前端技术栈（HTML5 Canvas + Vanilla JavaScript）编写，无需任何编译环境或依赖安装。

1. 克隆本仓库：
   ```bash
   git clone https://github.com/yearafteryear/AeroFlip-Kinematic-Sim.git
2. 使用任何现代浏览器（Chrome, Edge, Firefox, Safari）直接双击打开 index.html 文件。
3. 拖动页面中的滑块，即可交互式体验卸货全过程。

## 🛠️ 技术实现细节

1. 防穿模计算：底层物理引擎引入了动态边界碰撞检测，确保翻转圆弧轨迹完美贴合接货篮内壁。

2. 绳索柔性模拟：采用二次贝塞尔曲线（Quadratic Bézier Curves）实时解算绳索在受力（直线）与空载（下垂）状态下的视觉过渡。

3. 粒子掉落引擎：内置简易重力加速度与反弹阻尼算法，模拟货物倾泻的真实物理堆积感。

## 📄 开源协议 (License)

本项目采用 MIT License 开源协议。欢迎交流、复刻与提交 PR！