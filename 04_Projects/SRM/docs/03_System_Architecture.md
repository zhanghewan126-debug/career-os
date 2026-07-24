# System Architecture｜SRM

---

## 1. Architecture Overview

SRM 采用前后端分离的轻量 Web 架构：

- 表示层：模板渲染（template）+ 动态下拉（select）+ 数据网格（data2json）
- 后端层：Python 自研 Eip 框架（reqs 请求参数解析 / execute·execblock SQL 执行 / template 模板渲染 / data2json 数据网格）
- 业务逻辑层：8 大业务模块 + 工作流签核引擎（workflow_create / workflow_audit）
- 数据访问层：Oracle PL/SQL 存储过程包 AP_SUPPLIER_MANAGE_PKG
- 数据库层：Oracle EIP 本地库，经 DB Link 与 Oracle EBS（@iei_prod）、MES（@MES_QNP）等外部系统实时交互
- 外部集成：启信宝 API（企业工商信息）、邮件 / 企业微信通知渠道

---

## 2. Layered Architecture

系统总体架构图：

![System Architecture](../images/architecture.svg)

---

## 3. Core Module Architecture

业务逻辑层由以下核心模块组成，各模块通过工作流签核引擎与 PL/SQL 存储过程包串联：

| 模块 | 职责 |
|------|------|
| 建档申请 | 供应商建立申请单，含查重、动态下拉、评鉴前置、提交强校验 |
| 资料变更 | 已有供应商信息的新增/修改/失效变更 |
| 查询与合约附档 | 供应商主数据、合约附档、体系文件统一查询 |
| 评鉴管理 | 评鉴单据、稽核计划 |
| 配合性评分 | 品保对供应商服务配合度打分 |
| 绩效评分统计 | 交期/品质/价格/服务四维加权评分与分级（含动态 SQL 引擎） |
| Workflow | 签核流程引擎对接 |
| AP_SUPPLIER_MANAGE_PKG | PL/SQL 存储过程包，业务逻辑核心 |

模块详细说明见 [业务流程](02_Business_Process.md)。

---

## 4. Data Flow Architecture

主数据流沿业务链路推进：

```text
供应商建档/变更（EIP 录入） → 工作流签核 → PL/SQL 包驱动 → 抛转/回写 Oracle ERP（AP/PO）
```

绩效评分统计的数据流则是跨库汇聚：

```text
ERP 收料评分 + MES 品检数据（@MES_QNP） + 服务评分 → 动态 SQL 汇总 → 绩效评分统计 → 分级（A/B/C/D）
```

---

## 5. Design Principles

### 5.1 双轨标识与中间表设计

供应商数据可能来自 Oracle EBS 正式表，也可能来自 EIP 本地中间表（尚未回写 ERP 的新建/变更记录）。系统以 `erp_` / `eip_` 前缀机制统一标识两类来源的记录，变更经签核后通过 Merge 回写 ERP，解决"新单据在 EIP 录入、最终落地 ERP"的数据一致性问题。

### 5.2 配置化 + 动态 SQL

绩效评分统计模块以权重/阈值配置字典 + 占位符模板（{B}/{E}/{N}/{C} 等）驱动动态 SQL 生成，一套代码支撑多组织、多周期、多维度的差异化统计，避免为每个组织单独硬编码统计逻辑。

### 5.3 工作流节点钩子驱动业务自动化

业务逻辑下沉到 PL/SQL 存储过程包，以工作流流程节点钩子的形式驱动：签核通过后自动创建评鉴单、自动生成供应商编码、自动抛转/回写 ERP、自动发送通知，实现签核流转中无人工干预的端到端自动化。

### 5.4 复杂校验规则引擎

建档、变更、提交环节按"组织 × 供应商类型 × 特殊产品"组合维度落地大量业务防呆校验（如费用性物料对应资质、制造商体系文件、地址类型勾选等），从源头保障主数据质量。

### 5.5 多语言 / 多组织适配

CN/TW 与海外站点的付款资料、单据栏位支持中英文动态切换，业务规则按 org_id（境内外子公司）差异化配置。

---

## 6. Architecture Value

该架构适合企业供应商主数据治理场景，因为它能够同时满足：

- EIP-ERP 跨系统数据一致性
- 多组织差异化业务规则与统计口径
- 复杂强校验与查重规则
- 工作流驱动的端到端自动化
- 跨系统（EBS/MES/启信宝）多源数据整合

SRM 的架构重点不是追求技术炫技，而是围绕供应商主数据治理的一致性、可扩展性和自动化程度进行设计。
