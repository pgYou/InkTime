# InkTime 项目规则

本项目是 fork 自 [dai-hongtao/InkTime](https://github.com/dai-hongtao/InkTime) 的个人改造项目：墨水屏「回忆相框」。
目标：基于上游实现做个人化改造，并落地一套自己可用的硬件。

## 背景速查

- 上游实现概览：[spec/project-overview.md](spec/project-overview.md)（基于上游 commit `3cdab6c` 的基线快照）
- 决策记录：[JOURNAL.md](JOURNAL.md)（所有讨论结论以日志为准，不依赖 AI 会话记忆）
- fork 仓库：`git@github.com:pgYou/InkTime.git`，本地路径 `/Users/lukepeng/src/InkTime`

## 工作方式（跨会话开发）

- 每轮对话聚焦一个决策：给选项、讲清成本和风险，用户拍板后才动手
- 不擅自改代码：涉及代码/配置改动，先给方案征询确认
- 结论落盘：任何决策（选了什么、为什么）当轮写入 `JOURNAL.md`；新会话恢复上下文时，先读本文件和 `JOURNAL.md`，再按需读 `spec/`
- 设计文档不可变：`spec/design/` 下的设计定稿后不改原文，变更走新文档并在 `JOURNAL.md` 记录
- 上游同步：改动尽量收敛、模块化，方便未来 merge 上游更新

## 用户情况

- 软件是擅长领域，硬件不熟：硬件方案要给到「照着买 / 照着焊」的粒度，讲清风险与替代路线
- 开发节奏三阶段（详见 `JOURNAL.md` 阶段表）：
  1. 聊清需求：上游实现 + 预期功能 + 软硬件方案可行性
  2. 硬件定案：确定方案，指导 BOM 采购或打板
  3. 落地交付：软件开发、部署与硬件组装

## 合规注意

- ESP32 固件依赖 GxEPD2（GPL-3.0）：对外分发编译固件需遵守 GPL-3.0，个人自用无碍
- 离线城市索引基于 GeoNames 数据（CC BY 4.0）
