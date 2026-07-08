# Changelog

All notable changes to CareerOS will be documented here.

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
