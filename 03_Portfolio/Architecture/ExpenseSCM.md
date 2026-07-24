# Architecture｜ExpenseSCM

> 本页仅作导航摘要，原始图纸与完整说明以 [04_Projects/ExpenseSCM](../../04_Projects/ExpenseSCM/) 为准。

系统采用企业内部常见的分层架构：表示层（EasyUI/Jinja2/Vue）→ 后端层（Python/Flask）→ 业务逻辑层（业务模块 + Workflow）→ 数据访问层（SQL/PL-SQL Package）→ 数据库层（Oracle/MongoDB/Oracle EBS）。

![System Architecture](../../04_Projects/ExpenseSCM/images/architecture.svg)

- 完整说明：[系统架构文档](../../04_Projects/ExpenseSCM/docs/03_System_Architecture.md)
- 原始图纸：[architecture.drawio](../../04_Projects/ExpenseSCM/images/architecture.drawio) / [architecture.svg](../../04_Projects/ExpenseSCM/images/architecture.svg)

返回 [Portfolio 首页](../README.md)
