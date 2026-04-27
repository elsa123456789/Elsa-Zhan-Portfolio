# Enterprise SaaS Low-Code Platform | System Design & UAT Practice

## Project Background

**System Architecture** | 50+ core database tables | 80+ CRUD APIs | Supports multiple business modules  
**My Role** | Business Analyst, responsible for data table design, business process configuration, and system‑level UAT validation  
**Key Contributions** | Core design of inventory module, application of generic form framework, cross‑module UAT execution

> **Project Context**: This project is an enterprise SaaS low‑code platform that includes multiple modules such as Inventory, Approval, and Drive. I led the design of foundational data tables and front‑to‑back process configuration for modules like Inventory and Approval, as well as designing 400+ UAT test cases and tracking 30+ defects in the Drive system.

---

## Project Challenges

### Technical Requirements for the Inventory Module

- **Data Structure Design**: Support inventory tracking across multiple business lines, warehouses, and product types. Design core table relationships (product, warehouse, batch, stock, etc.).
- **Business Process Coverage**: Front‑end forms and API interfaces for basic operations such as inventory adjustment, internal transfer, and batch management.
- **System Integration**: Data flow and status synchronization between the inventory module and upstream/downstream modules (e.g., procurement, sales).

### General Quality Assurance for the Low‑Code Platform

- **Cross‑Module Test Coverage**: 50+ database tables and 80+ API interfaces distributed across Inventory, Approval, Drive, and other modules.
- **Test Case Organization**: How to systematically manage 400+ UAT test cases covering positive flows, exception handling, and boundary conditions.
- **Defect Tracking & Closure**: Collaborate with the development team to ensure transparent and efficient reproduction, root cause analysis, fixing, verification, and closure of 30+ critical defects.

---

## Solutions

### 1. Foundational Data Design for the Inventory Module

**Core Table Structure** (Key data models for inventory management):

| Table Name | Responsibility | Key Fields |
|------------|----------------|-------------|
| `product` | Product master record | Product ID, name, type, SKU, unit, default price |
| `warehouse` | Warehouse information | Warehouse ID, name, type, address, enabled status |
| `inventory_batch` | Inventory batch | Product ID, batch number, purchase date, source, supplier info |
| `inventory_stock` | Real‑time inventory | Batch ID, warehouse ID, quantity on hand, committed stock, real‑time price |
| `stock_adjustment` | Inventory adjustment | Adjustment ID, warehouse ID, reason, quantity before/after, execution date |
| `stock_transfer` | Inventory transfer | Transfer ID, source warehouse, destination warehouse, product, quantity, date |
| `stock_loss` | Inventory loss record | Batch ID, warehouse ID, lost quantity, loss source, discovery date |

**Design Principles**:
- **Separation of batch and location**: Independent management of batch attributes and inventory quantities, enabling tracking of a batch across multiple warehouses.
- **Traceability of operations**: Every inventory change (adjustment, transfer, loss) generates a separate record for easy historical query and root cause analysis.
- **Flexible extensibility**: Core table structure is kept simple, supporting configuration‑based or field‑based extension to fit different business lines.

### 2. Front‑End Implementation of Inventory Business Processes

**Core Inventory Management Processes**:
- **Inventory Adjustment**: Record reasons for inventory discrepancies (cycle count differences, damage, etc.) and adjustment quantities.
- **Inventory Transfer**: Support warehouse‑to‑warehouse transfers, automatically updating stock data in source and destination warehouses.
- **Batch Management**: Link procurement batches to inventory, enabling batch‑level inbound/outbound tracking.
- **Inventory Query**: Multi‑dimensional inventory views by product, batch, and warehouse.

**Implementation Key Points**: Use the low‑code platform’s form builder to configure business processes, leveraging field mapping and process rules to automate data transformation and flow.

### 3. Business Process Configuration Using the Generic Form Framework

The inventory module does not exist in isolation; it integrates with other modules through the **Approval** generic form capability:

**Configuration Approach**:
- **Form Builder**: Quickly generate front‑end interfaces for business forms (e.g., inventory adjustment, transfer) without coding.
- **Process Configuration**: Define the complete flow: form submission → data validation → business processing → result feedback.
- **Field Mapping**: Automatically map form fields to database tables for automatic data storage and association.

**Value**: Reduces delivery cycles and allows non‑technical personnel to participate in rapid iterative validation of business processes.

### 4. System‑Level UAT & Quality Assurance

While the inventory module is only part of the larger ERP, my primary responsibility was to conduct comprehensive, cross‑module UAT for the **Drive system**:

**Design & Execution of 400+ UAT Test Cases**:
- Cover integrated scenarios across Inventory, Approval, Drive, and other modules.
- Categorized by business process: create form → configure process → execute workflow → persist data → query feedback.
- Include positive tests (business process validation), exception tests (error handling), and boundary tests (data constraint validation).

**Tracking & Closure of 30+ Critical Defects**:
- Collaborate with development team to reproduce issues, identify root causes, verify fixes.
- Systematically manage the entire defect lifecycle (Report → Assign → Fix → Verify → Close) using the Drive system’s defect tracking module.
- Ensure data consistency and business process integrity before go‑live.

---

## Work Showcase

### System Analysis & Process Design

![Modular Use Case Map](images/ERP%20-%20ERP%20Maps.png)
![Modular Use Case Map](images/ERP%20-%20ERP%20System%20Analysis.png)

*Modular use case map for the inventory module, clearly showing the decomposition from raw requirements to functions. Flowcharts clarify dependencies among major business flows such as inventory adjustment, internal transfer, batch management, and FIFO allocation, guiding data table design and API specification.*

### Database Architecture Design

![Product Inventory DB](images/ERP%20-%20Partial%20DB%20for%20Inventory.png)
![Product Inventory Module APIs](images/ERP%20-%20API%20listing%20screenshot1.png)
![Product Inventory Module Table Structure Design](images/ERP%20-%20API%20test%20sample.png)

*Configuration interface for table structures in the low‑code platform: field type constraints, auto‑numbering rules, primary‑foreign key relationships, data validation rules, demonstrating the flexibility of a table‑driven architecture. Business rule changes are achieved via parameter configuration without modifying backend code.*

### Approval Generic Form Framework Configuration

![Generic Form Configuration Framework](images/ERP%20-%20General%20forms%20implementation.png)

*Configuration interface for forms, workflows, and data relationships in the Approval module. It shows how the low‑code platform uses a drag‑and‑drop form builder, process configuration, and field mapping to quickly implement forms, approval routing, and data validation for any business module (including inventory) without backend coding.*

### System‑Level UAT Test Framework

![UAT Test Framework](images/ERP%20-%20Test%20case%20list%20of%20drive.png)

*Framework for managing 400+ UAT test cases in the Drive system. Test cases are organized by module and process, covering integrated scenarios across Inventory, Approval, etc., including positive flow validation, exception handling, and boundary condition verification to ensure cross‑module data integrity.*

### Defect Tracking & Quality Management

![Defect List & Follow‑up](images/ERP%20-%20Drive%20bug%20list.png)

*Examples of 30+ critical defect tracking in the Drive system, illustrating the complete defect lifecycle management: issue report → root cause analysis → development fix → UAT validation → final closure. Systematic tracking and two‑way communication ensure each issue is properly resolved, providing quality assurance before release.*

---

## Results

### Quantitative Metrics

- ✅ **Designed 50+ database tables**: Support 10+ business modules (product, location, batch, documents, finance, etc.), including product groups, warehouses, adjustments, and transfers.
- ✅ **Defined 80+ CRUD APIs**: Complete CRUD interfaces for inventory, allocation, and loss, supporting batch operations.
- ✅ **Executed 400+ UAT test cases**: Validated the inventory module based on the low‑code platform and business processes, assisting development in resolving 30+ critical defects.
- ✅ **Inventory accuracy improvement**: Shifted from manually identifying losses during cycle counts to proactive system‑driven loss cause tracking, increasing problem‑detection efficiency by 60%.
- ✅ **Automated allocation logic**: Parameterized FIFO rules – adding new products requires no code changes; parameter configuration is sufficient.

### Technical Value

1. **High extensibility**: Table‑driven architecture – new business requirements (e.g., inventory alerts, cross‑factory transfers, product group management, warehouse adjustments) only require extending tables and parameter configurations, not modifying core logic.
2. **Data integrity**: Every inventory change has traceability information (source, time, operator), supporting a complete audit trail.
3. **Real‑time accuracy**: FIFO logic executes instantaneously, inventory data is accurate at millisecond level, preventing overselling or stock‑outs.

### Business Enablement

- **Supply chain transparency**: Complete product traceability from batch dimension (procurement → inbound → allocation → outbound).
- **Cost control**: Precise root cause identification for inventory losses (procurement error vs. operational error vs. logistics damage), facilitating process improvement and accountability.
- **Operational efficiency**: Automated allocation decisions shift warehouse personnel from “manual recording and judgment” to “system‑recommended, human‑confirmed”, reducing human errors.

---

## Technical Retrospective

**Key Design Decisions**:
- **Why table‑driven?** Avoid hard‑coding business rules; parameterized configuration enhances system flexibility.
- **Why separate batch and location?** Enable independent management of the same batch across multiple warehouses, supporting multi‑warehouse scenarios.
- **Why an inventory loss table?** Loss is not just a data issue but a business problem that requires root cause tracking and improvement.
- **Why extend product and warehouse modules?** Provide complete product lifecycle management and warehouse operation support, ensuring integration of the inventory module with other modules.

**Iteration & Future Directions**:
- Add real‑time inventory alerting and demand forecasting to proactively detect stock shortages and trigger replenishment suggestions.
- Implement inventory snapshots and version management to support multi‑point reconciliation and historical tracing.
- Integrate a Product Lifecycle Management (PLM) module to support product versioning, specification changes, and mapping to inventory.
- Extend to multi‑factory, cross‑geography inventory collaboration to support global supply chain scenarios.