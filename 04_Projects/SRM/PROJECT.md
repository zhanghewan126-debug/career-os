# SRM Project Dashboard

> CareerOS - Enterprise Supplier Relationship Management System

---

## 📌 Project Information

| Item | Content |
|------|---------|
| Project Name | SRM |
| Project Type | Enterprise EIP Subsystem |
| Domain | Supplier Relationship Management |
| Status | 🟢 Active Development |
| Repository | CareerOS / 04_Projects / SRM |

---

## 🎯 Project Goal

将真实企业 SRM（供应商关系管理）项目整理为一份高质量的技术作品集。

项目不仅展示代码能力，更重点展示：

- 跨系统主数据治理能力（EIP ↔ Oracle EBS 双库一致性）
- 配置化 / 动态 SQL 设计能力
- 复杂业务校验规则设计能力
- 工作流深度集成与自动化设计能力
- Oracle PL/SQL 存储过程包开发能力

最终用于：

- Python 后端岗位
- ERP / EIP 开发岗位
- Oracle 开发岗位
- 企业信息化开发岗位
- 技术作品集展示

---

## 📈 Development Progress

### Phase 1：Project Foundation

- [x] Repository Structure
- [x] README（初版）
- [x] Project Overview
- [x] Business Process
- [x] System Architecture
- [x] Architecture Diagram（draw.io + SVG）

### Phase 2：Documentation

- [x] Database Design
- [x] Database ER Diagram
- [ ] 核心流程图（评鉴流程 / 绩效评分统计流程 / EIP-ERP 数据回写流程）

### Phase 3：Interview Preparation

- [ ] Technical Highlights
- [ ] STAR Interview
- [ ] Interview Q&A
- [ ] Resume Bullets

---

## 📂 Repository Structure

- README.md（项目首页）
- PROJECT.md（项目管理）
- docs/（技术文档）
- images/（架构图、流程图、ER 图）
- assets/（附件）

---

## 🗂 Current Milestone

**Milestone 2：Database Design**

当前任务：

- [x] 核心业务实体梳理（14 个核心实体，见 docs/04_Database_Design.md §2）
- [x] 核心表设计（含 EIP-ERP 双轨中间表、AP_SUPPLIER_MANAGE_PKG 相关钩子过程说明）
- [x] Database ER Diagram（images/database-er.drawio / database-er.svg）

---

## 🚀 Next Milestone

**Milestone 3：核心流程图**

完成：

- 评鉴流程图（多级签核状态机）
- 绩效评分统计流程图（动态 SQL 引擎、多维度加权、跨库整合）
- EIP-ERP 数据回写流程图（erp_/eip_ 双轨机制、Merge 回写）

---

## 📝 Development Principles

本项目遵循以下原则：

1. 一次只完成一个 Milestone
2. 每完成一个阶段即提交 Git
3. README 面向招聘方
4. docs 面向技术细节
5. images 保存所有 SVG、draw.io 图纸
6. 所有内容保持统一命名规范
7. 每完成一个模块进行 Review 后再进入下一阶段

---

## 📅 Change Log

| Version | Description |
|---------|-------------|
| v0.1 | 创建 SRM 项目目录结构 |
| v0.2 | 完成 Project Overview / Business Process / System Architecture / Architecture Diagram |
| v0.3 | 完成 Database Design 文档与 ER Diagram |

---

## 💡 Future Plan

后续计划包括：

- 补充核心业务流程图（评鉴流程、绩效评分统计流程、EIP-ERP 数据回写流程）
- 完成 STAR 面试案例、Interview Q&A、Resume Bullets
- 整合至 CareerOS Portfolio
