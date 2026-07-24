# Resume Bullets｜ExpenseSCM

> 可直接用于简历的项目描述，提供不同长度和侧重点的版本。`【 】` 中为需要你本人核实填入的真实数据，没有把握的具体数字建议改用定性表达（如"显著提升/明显减少"），避免使用未经证实的数字。

---

## 1. 一句话项目简介（用于简历项目标题下的一行摘要）

企业 ERP 费用性供应链管理系统，独立负责数据库设计、后端开发与 Oracle PL/SQL 核心事务实现，覆盖请购、采购、验收、库存、成本核算全流程。

---

## 2. 标准简历版（3–5 条 bullet，适合大多数投递场景）

**ExpenseSCM · 企业 ERP 费用性供应链管理系统**　|　Python / Flask / Oracle / PL/SQL / Oracle EBS

- 独立完成系统数据库设计与后端开发，覆盖请购（PR）、采购准备（PPR）、采购订单（PO）、验收、库存、领用、退料、月度成本核算全业务流程，支撑【N】个业务模块、【N+】张核心业务表
- 设计 Supply Layer 七层供需数据模型，将物料在请购、在途、检验、在库、验退各阶段的数量统一建模，支撑可用量实时计算，减少重复采购与库存超发
- 使用 Oracle PL/SQL Package 封装验收入库、领用扣减、验退等多表联动事务，结合 SELECT FOR UPDATE 行锁与幂等键设计，解决高并发场景下的库存一致性问题
- 设计并实现月度加权平均成本核算模型，支撑费用性物料期间成本自动化核算与期末滚动结转，替代原有人工 Excel 核算流程
- 通过 Oracle EBS（DB Link）完成物料主档、供应商等基础数据的系统集成，并对接企业内部 Workflow 引擎实现审批流与业务状态解耦

---

## 3. 精简版（1–2 条，适合简历篇幅紧张或作为附加项目列出）

- 主导设计企业 ERP 费用性供应链系统的核心数据模型（Supply Layer 供需模型、月度加权平均成本模型），并使用 Oracle PL/SQL Package 实现高并发场景下的库存事务一致性控制
- 独立负责费用性供应链系统全链路开发（请购→采购→验收→库存→成本核算），涉及 Python/Flask 后端、Oracle/PL-SQL 数据库开发与 Oracle EBS 系统集成

---

## 4. 详细版（用于作品集 / Portfolio 页面，非简历正文）

**项目背景**：为解决企业费用性物料管理长期依赖 Excel 与邮件流转、库存账实不符、成本核算依赖人工的问题，主导设计并开发了 ExpenseSCM 企业 ERP 系统。

**核心职责**：

- 需求分析与业务流程梳理，独立完成数据库设计（ER 建模、表结构设计）
- Python/Flask 后端接口开发，EasyUI/Jinja2/Vue.js 前端页面开发
- Oracle SQL/PL-SQL 开发，核心业务逻辑（库存事务、成本核算）以 PL/SQL Package 实现
- 企业内部 Workflow 审批流对接与业务状态机设计
- Oracle EBS 系统集成（DB Link 同步物料、供应商、汇率等基础数据）
- 系统测试、上线及后续维护

**关键技术贡献**：

- 设计 Supply Layer 七层供需数据模型（PR/PPR/PO/RECEIVING/ACCEPT/ONHAND/RETURN），解决传统库存表无法反映在途供应与已预约需求的问题
- 使用 PL/SQL Package + 行锁 + 幂等键，解决多部门并发领用场景下的库存超扣问题
- 设计月度加权平均成本模型，支撑费用性物料的期间成本自动化核算

**量化成果**（请替换为真实数据，无把握请改为定性描述）：

- 库存差异 / 账实不符问题【减少 XX%】
- 财务月结耗时【从 X 天缩短至 X 天】
- 审批流程调整交付周期【从按天缩短到按小时】（源于审批规则配置化）

---

## 5. LinkedIn / 英文版本（可选，用于国际化投递场景）

Led database design and backend development for ExpenseSCM, an enterprise ERP expense supply chain management system covering the full lifecycle from purchase requisition to receiving, inventory, and monthly cost accounting.

- Designed a 7-layer supply model (Supply Layer) tracking material status across requisition, purchasing, receiving, and inventory stages, enabling real-time available-quantity calculation and reducing duplicate purchasing
- Implemented concurrency-safe inventory transactions using Oracle PL/SQL packages with row-level locking (SELECT FOR UPDATE) and idempotency keys, eliminating race conditions in high-concurrency material issue scenarios
- Built a monthly weighted-average cost accounting model with period-end rollover, replacing manual Excel-based cost calculation
- Integrated with Oracle EBS via DB Link for master data synchronization and connected the system to an internal workflow engine to decouple approval routing from business logic

---

## 使用建议

- 投递偏 ERP/Oracle 岗位：优先用「标准简历版」，突出 PL/SQL、数据库设计、EBS 集成
- 投递偏 Python 后端岗位：可将 Flask 后端开发放在第一条，PL/SQL 部分作为"复杂事务处理经验"补充说明
- 投递偏系统设计/架构岗位：优先突出 Supply Layer 设计和月度成本模型这两点的"设计取舍"能力
- 所有量化数据发布前务必核实真实性，无法核实的一律使用定性表达，避免面试时被追问具体数字却答不上来

---

## 相关文档

- [技术亮点](05_Technical_Highlights.md)
- [STAR 面试案例](06_STAR_Interview.md)
- [面试问答](07_Interview_QA.md)
- 返回 [项目首页](../README.md)
