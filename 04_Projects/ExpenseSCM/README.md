# ExpenseSCM｜企业 ERP 费用性供应链管理系统

> 一个覆盖请购、采购、验收、库存、领用、退料、成本核算全过程的企业级 ERP 费用性供应链管理系统。

![Python](https://img.shields.io/badge/Python-Flask-3776AB?logo=python&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-PL%2FSQL-F80000?logo=oracle&logoColor=white)
![EBS](https://img.shields.io/badge/Integration-Oracle%20EBS-red)
![MongoDB](https://img.shields.io/badge/MongoDB-Attachments-47A248?logo=mongodb&logoColor=white)
![Status](https://img.shields.io/badge/status-active%20development-brightgreen)

---

# 🏗 系统架构

> 系统总体架构图

![System Architecture](images/architecture.svg)

---

# 📌 项目简介

ExpenseSCM 是企业内部 ERP 费用性供应链管理系统。

系统围绕费用性物料管理，建立了从需求提出、采购、验收、库存管理到成本核算的完整业务闭环，实现采购部门、仓库、财务及需求部门之间的数据协同。

系统覆盖：

- 请购（PR）
- 采购准备（PPR）
- 采购订单（PO）
- 收货验收
- 入库管理
- 库存管理
- 领料管理
- 退料管理
- 月度成本核算
- 审批工作流
- Oracle EBS 集成

---

# ✨ 项目亮点

- 企业级 ERP 费用性供应链管理系统
- 完整覆盖费用性物料业务流程
- 支持请购 → 采购 → 验收 → 入库 → 领料 → 成本核算全流程
- Workflow 审批流驱动业务流转
- Supply Layer 七层库存模型
- 月度加权平均成本核算
- Oracle PL/SQL Package 复杂事务处理
- Oracle EBS（DB Link）系统集成
- MongoDB 附件管理
- 多组织、多部门权限控制

---

# 🛠 技术栈

| 分类 | 技术 |
|------|------|
| 后端 | Python、Flask |
| 前端 | EasyUI、Jinja2、Vue.js |
| 数据库 | Oracle、PL/SQL |
| 数据处理 | Pandas、Excel |
| 集成 | Oracle EBS、DB Link |
| 文件存储 | MongoDB |
| 工作流 | 企业内部 Workflow Engine |

---

# 🗂 核心图纸速览

| 图纸 | 说明 |
|------|------|
| [系统架构图](images/architecture.svg) | 分层架构、模块划分、数据流向 |
| [数据库 ER 图](images/database-er.svg) | 14 张核心表关系、采购/验收/库存/成本四大分区 |
| [Workflow 审批流](images/workflow.svg) | audit_order_id 状态机与审批驱动的业务流转 |
| [Supply Layer 供需模型](images/supply-layer.svg) | 七层供应状态与可用量计算公式 |
| [Inventory Flow 库存事务](images/inventory-flow.svg) | 四类库存事务、PL/SQL Package 与三表协同 |
| [Cost Flow 成本核算](images/cost-flow.svg) | 月度加权平均公式与月结流程 |

---

# 📚 项目文档

**核心技术文档**

| 文档 | 内容 |
|------|------|
| [项目概述](docs/01_Project_Overview.md) | 项目背景、建设目标及职责 |
| [业务流程](docs/02_Business_Process.md) | 费用性供应链完整业务流程 |
| [系统架构](docs/03_System_Architecture.md) | 系统分层架构设计 |
| [数据库设计](docs/04_Database_Design.md) | 核心数据模型与表结构 |

**面试与作品集深潜**

| 文档 | 内容 |
|------|------|
| [技术亮点](docs/05_Technical_Highlights.md) | 核心技术难点与解决方案 |
| [STAR 面试案例](docs/06_STAR_Interview.md) | STAR 面试故事整理 |
| [面试问答](docs/07_Interview_QA.md) | 高频技术与业务问题 |
| [简历项目描述](docs/08_Resume_Bullets.md) | 可直接用于简历的项目描述 |

---

# 📂 项目结构

```text
ExpenseSCM
│
├── README.md                项目首页
├── PROJECT.md               项目开发看板
│
├── docs                     项目文档
│   ├── 01_Project_Overview.md
│   ├── 02_Business_Process.md
│   ├── 03_System_Architecture.md
│   ├── 04_Database_Design.md
│   ├── 05_Technical_Highlights.md
│   ├── 06_STAR_Interview.md
│   ├── 07_Interview_QA.md
│   └── 08_Resume_Bullets.md
│
├── images                   架构图、流程图、ER 图
│
└── assets                   附件、示例文件
```

---

# 🚀 当前建设进度

- ✅ 项目概述 / 业务流程 / 系统架构
- ✅ 数据库设计 / ER 图
- ✅ Workflow / Supply Layer / Inventory Flow / Cost Flow 四张核心流程图
- ✅ 技术亮点 / STAR 面试案例 / 面试问答 / 简历项目描述
- ⏳ 系统截图（脱敏）
- ⏳ 整合至 CareerOS Portfolio

---

# 👨‍💻 我的职责

我在项目中主要负责：

- 需求分析与业务流程梳理
- 系统设计
- 数据库设计
- Python 后端开发
- Oracle SQL / PL/SQL 开发
- Workflow 审批流开发
- 库存事务设计
- 成本核算实现
- Oracle EBS 系统集成
- 系统测试、上线及维护

---

# 🎯 项目价值

ExpenseSCM 建立了企业费用性物料管理的统一平台，实现了业务流、审批流和数据流的一体化管理。

系统有效提升了库存准确率、采购效率及财务成本核算能力，为企业费用性供应链管理提供了完整的信息化解决方案。
