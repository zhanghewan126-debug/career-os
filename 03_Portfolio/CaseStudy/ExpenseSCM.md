# Case Study｜ExpenseSCM

> 本页仅作导航摘要，完整内容以 [04_Projects/ExpenseSCM](../../04_Projects/ExpenseSCM/README.md) 为准。

---

## 项目概述

ExpenseSCM 是企业内部 ERP 费用性供应链管理系统，围绕费用性物料管理建立了从需求提出、采购、验收、库存管理到成本核算的完整业务闭环，实现采购部门、仓库、财务及需求部门之间的数据协同。

## 我的角色

需求分析、系统设计、数据库设计、Python 后端开发、Oracle SQL/PL-SQL 开发、Workflow 审批流开发、库存事务设计、成本核算实现、Oracle EBS 系统集成、系统测试与上线维护。

## 核心亮点

- Supply Layer 七层供需数据模型，解决传统库存表看不到在途供应与已预约需求的问题
- Oracle PL/SQL Package + 行锁 + 幂等键，解决高并发库存扣减一致性问题
- 月度加权平均成本核算模型，支撑费用性物料期间成本自动化核算
- Workflow 审批流与业务代码解耦，审批规则可配置化
- Oracle EBS（DB Link）系统集成

## 深入阅读

| 文档 | 说明 |
|------|------|
| [项目概述](../../04_Projects/ExpenseSCM/docs/01_Project_Overview.md) | 背景、目标、职责 |
| [业务流程](../../04_Projects/ExpenseSCM/docs/02_Business_Process.md) | 端到端业务流程 |
| [数据库设计](../../04_Projects/ExpenseSCM/docs/04_Database_Design.md) | 核心数据模型 |
| [技术亮点](../../04_Projects/ExpenseSCM/docs/05_Technical_Highlights.md) | 技术难点与解决方案 |
| [STAR 面试案例](../../04_Projects/ExpenseSCM/docs/06_STAR_Interview.md) | 面试故事整理 |
| [面试问答](../../04_Projects/ExpenseSCM/docs/07_Interview_QA.md) | 高频问答 |
| [简历项目描述](../../04_Projects/ExpenseSCM/docs/08_Resume_Bullets.md) | 简历可用文案 |

返回 [Portfolio 首页](../README.md)
