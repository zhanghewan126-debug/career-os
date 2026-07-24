# Changelog

All notable changes to CareerOS will be documented here.

---

## v0.5.0 - 2026-07-08

### Changed

- 优化 ExpenseSCM README 首页（招聘方视角）：新增技术栈徽章、核心图纸速览表格（六张图一键直达）、项目文档按"核心技术文档 / 面试与作品集深潜"分组

---

## v0.4.0 - 2026-07-08

### Added

- 完成 ExpenseSCM Interview Preparation 四份文档：
  - Technical Highlights：并发一致性、多表事务原子性、Supply Layer、成本模型、审批解耦、EBS 集成六大技术难点与取舍说明
  - STAR Interview：四个 STAR 案例（Supply Layer 设计、并发库存一致性、月度成本模型、审批流解耦）
  - Interview Q&A：技术 / 数据库设计 / 业务供应链 / 系统设计四类共 17 道高频问答
  - Resume Bullets：标准版、精简版、详细版、英文版简历项目描述

### Fixed

- 为 5 张手写 SVG 流程图补充 XML 声明，修复 GitHub 渲染问题（后续发现仍需进一步排查独立文件预览渲染，已记录待跟进）

---

## v0.3.0 - 2026-07-08

### Added

- 完成 ExpenseSCM 四张核心流程图（drawio + SVG 双格式）：
  - Workflow Diagram：audit_order_id 审批状态机与审批流驱动的业务流转
  - Supply Layer Diagram：七层供需模型、在途供应与可用量公式
  - Inventory Flow Diagram：四类库存事务、PL/SQL Package 事务封装与三表协同
  - Cost Flow Diagram：月度加权平均公式、期间滚动结转与月结流程
- 四张流程图分别嵌入系统架构与数据库设计文档对应章节

---

## v0.2.0 - 2026-07-08

### Added

- 完成 ExpenseSCM Database Design 文档（docs/04_Database_Design.md）
- 覆盖核心实体建模、Supply Layer 七层供需模型、库存事务设计、月度加权平均成本模型与数据一致性设计
- 完成 Database ER Diagram（images/database-er.drawio / database-er.svg），并嵌入数据库设计文档
- 更新 ExpenseSCM PROJECT.md 与 CareerOS PROJECT.md 进度

### Changed

- 全仓库 Markdown 格式清理：移除转义符与 HTML 实体，统一标题层级，修复表格与流程图渲染

---

## v0.1.0 - 2026-07-08

### Added

- 初始化 CareerOS Repository
- 创建 GitHub Repository
- 完成目录结构
- 完成 ExpenseSCM 基础文档
- 完成 Architecture Diagram
