---
title: "项目"
layout: "single"
url: "/projects/"
summary: projects
---

## [四足-轮式复合移动机器人底盘](https://github.com/Fredie06/wheel-leg-climber)

<span class="proj-tag">RT-Thread</span>
<span class="proj-tag">CAN 双总线</span>
<span class="proj-tag">VMC 姿态自稳</span>
<span class="proj-tag">MIT 阻抗控制</span>
<span class="proj-tag">PID 速度闭环</span>
<span class="proj-tag">六级状态机</span>
<span class="proj-tag">STM32F7</span>
<span class="proj-tag">DM4340</span>
<span class="proj-tag">M3508</span>

四足-轮式复合底盘，兼具平地全向移动与自主攀爬能力。

基于 RT-Thread，四线程并发，CAN1/CAN2 双总线分别承载 M3508 与 DM4340 电机。关节空间 VMC 实现 pitch/roll 姿态自稳，DM4340 工作在 MIT 阻抗模式，硬/软态动态切换。六级攀爬状态机全自动推进，力矩检测判定台阶接触，被动优先策略。实物爬越 20cm + 15cm 两级台阶。

<figure class="proj-figure">
  <img src="/images/wheel-leg-climber.jpg" alt="四足-轮式复合移动机器人底盘" class="proj-img">
  <figcaption>机械结构非本人设计</figcaption>
</figure>