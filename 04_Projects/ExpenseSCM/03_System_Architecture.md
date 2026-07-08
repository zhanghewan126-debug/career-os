\# System Architecture｜ExpenseSCM



\---



\# 1. Architecture Overview



ExpenseSCM 采用企业内部系统常见的分层架构：



\- 表示层：EasyUI / Jinja2 / Vue

\- 后端层：Python / Flask

\- 业务逻辑层：业务模块 + Workflow

\- 数据访问层：SQL / PL/SQL Package

\- 数据库层：Oracle / MongoDB / Oracle EBS



\---



\# 2. Layered Architecture



```mermaid

flowchart TD

&#x20;   A\[User Browser] --> B\[Frontend Layer<br/>EasyUI / Jinja2 / Vue]

&#x20;   B --> C\[Backend Layer<br/>Python / Flask]

&#x20;   C --> D\[Business Layer<br/>Expense Modules / Workflow]

&#x20;   D --> E\[Data Access Layer<br/>SQL / PL/SQL Package]

&#x20;   E --> F\[(Oracle Database)]

&#x20;   E --> G\[(MongoDB Attachments)]

&#x20;   E --> H\[(Oracle EBS via DB Link)]

```



\---



\# 3. Core Module Architecture



```mermaid

flowchart LR

&#x20;   PR\[PR<br/>请购] --> PPR\[PPR<br/>采购准备]

&#x20;   PPR --> PO\[PO<br/>采购订单]

&#x20;   PO --> RCV\[Receiving<br/>验收]

&#x20;   RCV --> INV\[Inventory<br/>库存]

&#x20;   INV --> ISSUE\[Issue<br/>领用]

&#x20;   ISSUE --> COST\[Cost<br/>成本核算]



&#x20;   WF\[Workflow<br/>审批流] -.-> PR

&#x20;   WF -.-> PPR

&#x20;   WF -.-> RCV

&#x20;   WF -.-> ISSUE

```



\---



\# 4. Data Flow Architecture



```mermaid

flowchart TD

&#x20;   A\[PR 请购单] --> B\[Expense PO Prepare]

&#x20;   B --> C\[PO Headers / Lines / Locations]

&#x20;   C --> D\[Receiving Transactions]

&#x20;   D --> E\[Material Transactions]

&#x20;   E --> F\[OnHand Quantity]

&#x20;   F --> G\[Supply Layer]

&#x20;   G --> H\[Issue / Return]

&#x20;   H --> I\[Period Cost]

```



\---



\# 5. Design Principles



\## 5.1 Business Logic Layering



普通页面交互与查询逻辑放在 Python 层，涉及多表联动、库存扣减、验收入库、验退等复杂事务的逻辑下沉到 PL/SQL Package。



这样可以保证：



\- 事务一致性

\- 回滚可控

\- 数据处理性能

\- 复杂 SQL 能力充分利用



\---



\## 5.2 Database-Centric Transaction Design



系统中多个核心操作涉及 5 张以上业务表联动，例如：



\- 验收完成

\- 领用扣减

\- 验退退厂

\- 成本结转



这些操作统一通过 Oracle PL/SQL Package 处理，避免在应用层拆散事务。



\---



\## 5.3 Workflow-Driven Process



系统使用 `audit\_order\_id` 作为业务状态机，结合审批流表驱动流程流转。



业务单据不会只依赖页面状态，而是通过审批节点推动业务进入下一阶段。



\---



\## 5.4 Supply Layer Design



Supply Layer 用于记录物料在不同供应链节点中的状态：



\- PR

\- PPR

\- PO

\- RECEIVING

\- ACCEPT

\- ONHAND

\- RETURN



它解决了传统库存系统只能看到“在库数量”，却无法看到“在途数量”和“已预约需求”的问题。



\---



\# 6. Architecture Value



该架构适合企业 ERP 场景，因为它能够同时满足：



\- 复杂审批流

\- 高一致性库存事务

\- 多组织权限控制

\- 财务成本核算

\- Oracle EBS 集成

\- 大量复杂 SQL 报表查询



ExpenseSCM 的架构重点不是追求技术炫技，而是围绕企业业务系统的稳定性、一致性和可维护性进行设计。

