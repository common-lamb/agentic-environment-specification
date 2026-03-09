---
name: file-system-specification
description: defines a comprehensive filesystem-based taxonomy for organizing processes, knowledge, and operational state
---

# Overview

This document defines a comprehensive filesystem-based taxonomy for organizing processes, knowledge, and operational state.
Use this taxonomy when working with executive directives, organizing organizational knowledge, or structuring business process information.

# Process Taxonomy Specification

## 1. Introduction

### 1.1 Purpose

This document defines a comprehensive filesystem-based taxonomy for organizing processes, knowledge, and operational state. The taxonomy provides a standardized structure for business operations across diverse industries and organizational types.

### 1.2 Scope

This specification defines:
- A three-level hierarchical taxonomy of business processes
- Mapping to Toyota Production System (TPS) principles
- Guidelines for taxonomy usage and navigation

### 1.3 Design Principles

#### 1.3.1 Process-Oriented Structure

The taxonomy organizes around fundamental business flows rather than organizational structure. It models:
- **Value streams**: Creation and delivery of products/services
- **Knowledge streams**: Learning, innovation, and improvement
- **Resource streams**: Acquisition and allocation of capabilities
- **Coordination mechanisms**: Direction and optimization of the system

#### 1.3.2 Fixed Hierarchy with Flexible Implementation

- **Levels 1-3**: Fixed taxonomy structure (immutable)
- **Level 4**: Standardized categories of asdf systems for flexible content creation

#### 1.3.3 Universal Applicability

The taxonomy applies across domains.

#### 1.3.4 TPS Compatibility

All core Toyota Production System concepts map naturally to taxonomy locations without requiring extensions or modifications.

## 2. Taxonomy Structure

### 2.1 Hierarchical Organization

The taxonomy consists of a process root, three levels and a standard data system:

| Level | Description         | Count              | Mutability |
|-------|---------------------|--------------------|------------|
| 0     | Process Root        | 1                  | Immutable  |
| 1     | Streams             | 4                  | Immutable  |
| 2     | Universal Functions | 12                 | Immutable  |
| 3     | Process Areas       | 65                 | Immutable  |
| 4     | Data System         | 5 per process area | Immutable  |
| 5     | ASDF Systems        | create as needed   | Mutable    |

### 2.2 Level 1: Business Streams

Four fundamental flows exist in every business:

```
business/
├── coordination/
├── value-stream/
├── knowledge-stream/
└── resource-stream/
```

#### 2.2.1 coordination/

System-wide direction, control, and optimization spanning all other streams. Contains processes that operate at the whole-business level including strategic direction, governance mechanisms, and system optimization.

#### 2.2.2 value-stream/

The primary flow of creating and delivering products or services to customers. Encompasses the entire journey from understanding customer needs through production to final delivery and verification.

#### 2.2.3 knowledge-stream/

Organizational learning, innovation, and capability development. Captures how organizations understand their environment, create new capabilities, and develop their people.

#### 2.2.4 resource-stream/

Acquisition, development, and allocation of organizational capabilities and assets. Ensures value and knowledge streams have necessary resources: people, capital, and infrastructure.

### 2.3 Level 2: Universal Functions

Major functions that exist in some form in every business:

**coordination/**
- governance/
- flow-optimization/
- cross-cutting-concerns/

**value-stream/**
- customer-interface/
- fulfillment/
- supply/

**knowledge-stream/**
- insight/
- innovation/
- learning/

**resource-stream/**
- people/
- capital/
- infrastructure/

coordination/governance/
Purpose: Strategic direction, standards, risk management, and performance oversight.
Governance establishes the destination (strategy), the rules of the road (policy), the guardrails (risk management), the legal boundaries (compliance), and measures whether we're getting there (performance oversight). It also houses the executive directive - the source of truth that guides the entire system.
This is distinct from flow-optimization in that governance focuses on what and why, while flow-optimization focuses on how. Governance sets direction; flow-optimization improves execution.

coordination/flow-optimization/
Purpose: System-level process improvement and integration.
Flow-optimization works to make the entire business system run better. It maps how work flows across the organization (value stream mapping), identifies where work gets stuck (bottleneck analysis), improves processes (process improvement), ensures systems work together (system integration), and measures system health (metrics).
This is where the organization applies systems thinking to optimize the whole rather than sub-optimizing parts.

coordination/cross-cutting-concerns/
Purpose: System-level process aspects
cross cutting concerns are aspects of the process that affect several modules, without the possibility of being encapsulated in any of them. These concerns often cannot be cleanly decomposed from the rest of the system in both the design and implementation, and can result in either scattering (code duplication), tangling (significant dependencies between systems), or both

value-stream/customer-interface/
Purpose: All processes involving direct customer interaction and relationship management.
The customer interface is where the organization connects with the market. It includes understanding what customers want (market-analysis), attracting them (demand-generation), closing transactions (sales), managing orders (order-management), helping them (customer-support), keeping them (retention), and building reputation (brand).
This is the "pull" in TPS terms - the customer signal that drives everything else.

value-stream/fulfillment/
Purpose: Creating and delivering the actual product or service.
Fulfillment is the core transformation process where inputs become outputs that customers pay for. It includes the actual making/doing (production), ensuring quality (quality-assurance), planning the work (scheduling), getting it to customers (delivery), and confirming satisfaction (verification).
This is where most traditional "operations" work happens, but it's defined by the transformation rather than by departments.

value-stream/supply/
Purpose: Acquiring and managing inputs needed for fulfillment.
Supply processes ensure that fulfillment has what it needs, when it needs it. This includes finding suppliers (sourcing), contracting and ordering (procurement), accepting deliveries (receiving), managing buffers (inventory), and maintaining supplier relationships (supplier-relations).

knowledge-stream/insight/
Purpose: Understanding customers, markets, competitors, regulations, and performance.
Insight processes generate understanding about the external environment and internal performance. This includes learning what customers need (customer-research), tracking competitors (competitive-intelligence), monitoring regulations (regulatory-monitoring), analyzing how we're doing (performance-analysis), and predicting the future (forecasting).
This intelligence feeds into strategy, innovation, and operational decisions across all streams.

knowledge-stream/innovation/
Purpose: Creating new products, services, and capabilities.
Innovation processes transform ideas into deployable capabilities. This includes generating possibilities (ideation), testing viability (concept-validation), building prototypes (development), verifying they work (testing), and moving to operations (transition).
Innovation outputs eventually become new offerings in the value stream or new methods in other processes.

knowledge-stream/learning/
Purpose: Developing individual and organizational capability.
Learning processes ensure people have the knowledge and skills to perform their roles and improve over time. This includes bringing new people up to speed (onboarding), growing capabilities (skills-development), capturing knowledge (documentation), improving processes (kaizen), and spreading best practices (knowledge-sharing).

resource-stream/people/
Purpose: Building and organizing human capability.
People processes ensure the organization has the right talent, organized effectively. This includes finding people (recruiting), structuring work (organization), managing performance (performance-management), keeping talent (retention), and ensuring adequate staffing (capacity).
Note that skills development is in knowledge-stream/learning/, as it's about building capability rather than managing resources.

resource-stream/capital/
Purpose: Financial planning, tracking, and allocation.
Capital processes manage money flow. This includes planning spend (budgeting), tracking transactions (accounting), ensuring liquidity (cash-management), making capital decisions (investment), and reducing waste (cost-management).

resource-stream/infrastructure/
Purpose: Digital systems, physical facilities, equipment, security, and maintenance.
Infrastructure processes ensure the physical and digital environment supports operations. This includes IT systems (systems), buildings and spaces (facilities), tools and machinery (equipment), protecting assets (security), and keeping everything functional (maintenance).

### 2.4 Level 3: Process Areas

Specific process areas providing comprehensive coverage:

```

business/
│
├── binary-artefacts-store/
│
├── coordination/
│   ├── governance/
│   │   ├── strategy/
│   │   ├── policy/
│   │   ├── risk/
│   │   ├── compliance/
│   │   ├── performance-oversight/
│   │   └── interpreted-executive-directive/
│   ├── cross-cutting-concerns/
│   │   ├── communication/
│   │   ├── change-management/
│   │   ├── project-management/
│   │   ├── data-governance/
│   │   ├── continuous-improvement/
│   │   ├── vendor-management/
│   │   └── emergency-response/
│   └── flow-optimization/
│       ├── value-stream-mapping/
│       ├── bottleneck-analysis/
│       ├── process-improvement/
│       ├── system-integration/
│       └── metrics/
│
├── value-stream/
│   ├── customer-interface/
│   │   ├── market-analysis/
│   │   ├── demand-generation/
│   │   ├── sales/
│   │   ├── order-management/
│   │   ├── customer-support/
│   │   ├── retention/
│   │   └── brand/
│   ├── fulfillment/
│   │   ├── production/
│   │   ├── quality-assurance/
│   │   ├── scheduling/
│   │   ├── delivery/
│   │   └── verification/
│   └── supply/
│       ├── sourcing/
│       ├── procurement/
│       ├── receiving/
│       ├── inventory/
│       └── supplier-relations/
│
├── knowledge-stream/
│   ├── insight/
│   │   ├── customer-research/
│   │   ├── competitive-intelligence/
│   │   ├── regulatory-monitoring/
│   │   ├── performance-analysis/
│   │   └── forecasting/
│   ├── innovation/
│   │   ├── ideation/
│   │   ├── concept-validation/
│   │   ├── development/
│   │   ├── testing/
│   │   └── transition/
│   └── learning/
│       ├── onboarding/
│       ├── skills-development/
│       ├── documentation/
│       ├── kaizen/
│       └── knowledge-sharing/
│
└── resource-stream/
    ├── people/
    │   ├── recruiting/
    │   ├── organization/
    │   ├── performance-management/
    │   ├── retention/
    │   └── capacity/
    ├── capital/
    │   ├── budgeting/
    │   ├── accounting/
    │   ├── cash-management/
    │   ├── investment/
    │   └── cost-management/
    └── infrastructure/
        ├── systems/
        ├── facilities/
        ├── equipment/
        ├── security/
        └── maintenance/
```

### 2.5 Level 4: File Type Containers

Every Level 3 process area contains exactly five subdirectories:

```
<process-area>/
├── lisp-asdf-systems/
├── screamer-asdf-systems/
├── lisa-asdf-systems/
├── sqlite-asdf-systems/
└── lisa-binary-reference-asdf-systems/

```

Each directory of asdf systems can contain any number of asdf systems.
Each system will pertain to the process and data type which is described by the path to the system. The data system and system naming is described in detail in the data-system-specification.

## 3. Process Area Definitions

### 3.1 Coordination Stream

#### 3.1.1 coordination/governance/

System-wide direction, standards, risk management, and performance oversight.

**strategy/**
- Long-term direction and competitive positioning
- Multi-year horizons, market positioning, growth plans
- Strategic plans, investment priorities

**policy/**
- Operating principles and decision-making frameworks
- Standards, guidelines, approval workflows
- Translates strategy into actionable constraints

**risk/**
- Identification, assessment, and mitigation of organizational risks
- Operational, financial, strategic, reputational risks
- Crisis management and monitoring

**compliance/**
- Meeting legal, regulatory, and contractual obligations
- Understanding regulations, implementing controls
- Reporting to authorities, managing audits

**performance-oversight/**
- Monitoring organizational performance against objectives
- KPI definition, data collection, trend analysis
- Leadership reporting, triggering corrective action

**interpreted-executive-directive/**
- Contains interpretations of the executive-directive, mapping, compliance tracking
- Source of truth for organizational direction

#### 3.1.2 coordination/flow-optimization/

System-level process improvement and integration.

**value-stream-mapping/**
- Visualizing how value flows through the organization
- Current state maps, future state maps
- Lead time analysis, value-added activity identification

**bottleneck-analysis/**
- Identifying constraints limiting system throughput
- Constraint identification, capacity analysis
- WIP measurement, bottleneck mitigation

**process-improvement/**
- Systematically improving work methods
- Lean, Six Sigma, PDCA, A3 methodologies
- Waste elimination, continuous improvement culture

**system-integration/**
- Ensuring different parts work together effectively
- Handoff optimization, information flow design
- Cross-functional coordination

**metrics/**
- Designing and managing system-level measurements
- Metric definition, data collection, visualization
- Ensuring metrics drive desired behavior

#### 3.1.3 coordination/cross-cutting-concerns/

System-wide capabilities and activities that span multiple streams and process areas.

**communication/**
- Internal and external communication management
- Messaging strategy, announcement systems
- Information dissemination, stakeholder communication
- Communication channels and protocols

**change-management/**
- Managing organizational transitions and transformations
- Change planning, stakeholder engagement
- Resistance management, adoption tracking
- Transition support and stabilization

**project-management/**
- Cross-functional project coordination
- Project portfolio management, resource allocation
- Timeline management, milestone tracking
- Project governance and reporting

**data-governance/**
- Enterprise-wide data management and standards
- Data quality, data architecture, master data
- Data privacy, data lifecycle management
- Data access and sharing policies

**continuous-improvement/**
- Organization-wide improvement initiatives
- Improvement culture development, suggestion systems
- Cross-functional improvement teams
- Improvement methodology standardization

**vendor-management/**
- Managing relationships with external service providers
- Vendor selection, contract management
- Performance monitoring, vendor coordination
- Strategic vendor partnerships

**emergency-response/**
- Business continuity and crisis management
- Incident response, disaster recovery
- Emergency protocols, crisis communication
- Business resilience planning

### 3.2 Value Stream

#### 3.2.1 value-stream/customer-interface/

All processes involving direct customer interaction.

**market-analysis/**
- Understanding market size, trends, segments
- Market sizing, trend analysis, opportunity assessment
- Competitive landscape mapping

**demand-generation/**
- Creating awareness and interest
- Marketing campaigns, content creation, advertising
- Lead generation, filling sales pipeline

**sales/**
- Converting prospects into paying customers
- Qualification, proposal, negotiation, closing
- Sales methodology, opportunity management

**order-management/**
- Processing, tracking, and fulfilling orders
- Order entry, validation, tracking
- Backlog management, fulfillment coordination

**customer-support/**
- Helping customers and resolving issues
- Technical support, troubleshooting, escalation
- Post-sale assistance

**retention/**
- Keeping customers and maximizing lifetime value
- Customer success, renewal management
- Upselling, loyalty programs, churn prevention

**brand/**
- Building and protecting reputation and identity
- Brand strategy, messaging, visual identity
- Public relations, crisis communications

#### 3.2.2 value-stream/fulfillment/

Creating and delivering actual products or services.

**production/**
- Core transformation process creating customer value
- Manufacturing, development, service delivery
- Creating outputs customers pay for

**quality-assurance/**
- Ensuring outputs meet requirements
- Inspection, testing, quality control
- Defect detection, quality improvement

**scheduling/**
- Planning what gets produced when
- Production planning, capacity loading
- Prioritization, work sequencing

**delivery/**
- Transporting and deploying outputs to customers
- Logistics, shipping, installation
- Deployment coordination

**verification/**
- Confirming delivered outputs satisfy requirements
- Acceptance testing, customer sign-off
- Delivery confirmation

#### 3.2.3 value-stream/supply/

Acquiring and managing inputs for fulfillment.

**sourcing/**
- Identifying, evaluating, and selecting suppliers
- Supplier identification, capability assessment
- Quote requests, supplier selection

**procurement/**
- Contracting with and ordering from suppliers
- Contract negotiation, purchase orders
- Order tracking, supplier communication

**receiving/**
- Accepting, inspecting, and processing incoming materials
- Delivery acceptance, quantity verification
- Quality inspection, documentation

**inventory/**
- Managing buffers of materials and goods
- Raw materials, work-in-process, finished goods
- Buffer sizing, stock replenishment

**supplier-relations/**
- Building and maintaining supplier partnerships
- Performance monitoring, relationship management
- Collaboration on improvement

### 3.3 Knowledge Stream

#### 3.3.1 knowledge-stream/insight/

Understanding environment and performance.

**customer-research/**
- Understanding customer needs, behaviors, preferences
- User research, surveys, interviews
- Usage analysis, satisfaction measurement

**competitive-intelligence/**
- Monitoring and analyzing competitor actions
- Competitor monitoring, product comparison
- Market share tracking, competitive positioning

**regulatory-monitoring/**
- Tracking changes in laws and regulations
- Regulation tracking, impact assessment
- Industry standard monitoring

**performance-analysis/**
- Analyzing internal operational and financial performance
- Operational metrics analysis, financial analysis
- Variance analysis, trend identification

**forecasting/**
- Predicting future demand, costs, and conditions
- Demand forecasting, financial projections
- Capacity forecasting, scenario planning

#### 3.3.2 knowledge-stream/innovation/

Creating new products, services, and capabilities.

**ideation/**
- Generating and capturing new ideas
- Brainstorming, design thinking workshops
- Suggestion systems, innovation challenges

**concept-validation/**
- Testing viability before full investment
- Business case development, market validation
- Technical feasibility assessment

**development/**
- Building new capabilities from validated concepts
- Product development, feature development
- Process design, testing, refinement

**testing/**
- Verifying innovations work as intended
- Functional testing, user acceptance testing
- Performance testing, security testing

**transition/**
- Moving innovations into operational use
- Deployment planning, training, documentation
- Change management, rollout, stabilization

#### 3.3.3 knowledge-stream/learning/

Developing individual and organizational capability.

**onboarding/**
- Bringing new employees up to speed
- Orientation, role training, cultural integration
- Relationship building, initial performance support

**skills-development/**
- Growing capabilities beyond initial requirements
- Training programs, mentoring, job rotation
- Certification programs, leadership development

**documentation/**
- Capturing and organizing organizational knowledge
- Standard operating procedures, work instructions
- Best practices, lessons learned, knowledge bases

**kaizen/**
- Continuously improving through incremental changes
- Improvement suggestions, small experiments
- PDCA cycles, problem solving

**knowledge-sharing/**
- Spreading best practices and learnings
- Communities of practice, lessons learned sessions
- Best practice sharing, peer learning

### 3.4 Resource Stream

#### 3.4.1 resource-stream/people/

Building and organizing human capability.

**recruiting/**
- Attracting, assessing, and hiring talent
- Talent sourcing, candidate screening
- Interviewing, assessment, offer negotiation

**organization/**
- Structuring roles, teams, and relationships
- Organization design, team formation
- Role definition, reporting structure

**performance-management/**
- Setting expectations, providing feedback
- Goal setting, performance reviews
- Feedback, performance improvement plans

**retention/**
- Keeping valuable employees
- Compensation strategy, career development
- Work environment, culture building

**capacity/**
- Ensuring adequate staffing levels
- Workforce planning, headcount management
- Hiring forecasts, contractor management

#### 3.4.2 resource-stream/capital/

Financial planning, tracking, and allocation.

**budgeting/**
- Planning and allocating financial resources
- Budget development, resource allocation
- Budget approval, monitoring

**accounting/**
- Recording, classifying, and reporting transactions
- Transaction recording, financial reporting
- Accounts payable/receivable, payroll processing

**cash-management/**
- Ensuring sufficient liquidity
- Cash flow forecasting, working capital management
- Payment timing, collection management

**investment/**
- Making capital allocation decisions
- Business case evaluation, ROI analysis
- Project prioritization, capital approval

**cost-management/**
- Controlling and reducing costs
- Cost analysis, cost reduction initiatives
- Spend optimization, value engineering

#### 3.4.3 resource-stream/infrastructure/

Digital systems, facilities, equipment, and support.

**systems/**
- Digital systems, software, networks
- Application management, network operations
- Cloud infrastructure, cybersecurity

**facilities/**
- Buildings, workspaces, physical environment
- Facility planning, space management
- Workplace services, utilities

**equipment/**
- Tools, machinery, and production equipment
- Equipment acquisition, setup, operation
- Preventive maintenance

**security/**
- Protecting physical and digital assets
- Physical security, cybersecurity
- Access control, threat monitoring

**maintenance/**
- Keeping infrastructure and equipment functional
- Preventive maintenance, predictive maintenance
- Breakdown repair, spare parts management

## 4. Toyota Production System Mapping

### 4.1 Core TPS Principles

| TPS Principle                               | Primary Location                               | Supporting Locations                                |
|---------------------------------------------|------------------------------------------------|-----------------------------------------------------|
| Jidoka (automation with human intelligence) | value-stream/fulfillment/quality-assurance/    | resource-stream/infrastructure/equipment/           |
| Just-in-Time                                | value-stream/supply/inventory/                 | value-stream/fulfillment/scheduling/                |
| Kaizen (continuous improvement)             | knowledge-stream/learning/kaizen/              | coordination/flow-optimization/process-improvement/ |
| Heijunka (level loading)                    | value-stream/fulfillment/scheduling/           | resource-stream/people/capacity/                    |
| Genchi Genbutsu (go and see)                | knowledge-stream/insight/performance-analysis/ | coordination/governance/performance-oversight/      |
| Hoshin Kanri (policy deployment)            | coordination/governance/strategy/              | coordination/governance/policy/                     |
| Respect for People                          | resource-stream/people/retention/              | knowledge-stream/learning/skills-development/       |

### 4.2 TPS Practices and Tools

| Practice/Tool                      | Location                                                                       |
|------------------------------------|--------------------------------------------------------------------------------|
| Value Stream Mapping               | coordination/flow-optimization/value-stream-mapping/                           |
| 5S (workplace organization)        | resource-stream/infrastructure/facilities/                                     |
| Poka-Yoke (error proofing)         | value-stream/fulfillment/quality-assurance/                                    |
| Andon (stop and fix)               | value-stream/fulfillment/quality-assurance/                                    |
| Kanban                             | value-stream/supply/inventory/, value-stream/fulfillment/scheduling/           |
| TPM (Total Productive Maintenance) | resource-stream/infrastructure/maintenance/                                    |
| Standardized Work                  | value-stream/fulfillment/production/, knowledge-stream/learning/documentation/ |
| Visual Management                  | coordination/flow-optimization/metrics/                                        |
| SMED (quick changeover)            | resource-stream/infrastructure/equipment/                                      |
| Takt Time                          | value-stream/fulfillment/scheduling/                                           |

### 4.3 Waste Elimination (Muda, Muri, Mura)

Waste elimination is distributed throughout the taxonomy:

- **Process waste**: coordination/flow-optimization/process-improvement/
- **Financial waste**: resource-stream/capital/cost-management/
- **Defect waste**: value-stream/fulfillment/quality-assurance/
- **Inventory waste**: value-stream/supply/inventory/
- **Motion waste**: value-stream/fulfillment/production/
- **Overproduction waste**: value-stream/fulfillment/scheduling/

## 5. Usage Guidelines

### 5.1 Naming Conventions

Since Levels 0-4 are immutable, specificity is achieved through descriptive system, package and file names below Level 4.
Descriptive naming is described in detail in data-system-specification

### 5.2 Cross-Process References

Many initiatives span multiple process areas.
Loading asdf systems into the lisp image will facilitate this.
Document cross-process relationships using time-stamped metadata comments.
Control cross-process interactions using cross cutting concerns.

### 5.3 Executive Directive Interpretation and Integration

The interpreted-executive-directive process area serves as the integration point:
1. Executive directives reside in the executive-directive skill
5. Periodic review and reinterpretation ensures alignment
2. The interpreted-executive-directive holds the interpretation, process mapping and documents in same location
3. Each affected process area refers back to interpreted executive directives explaining relevance
4. Compliance tracking occurs in interpreted-executive-directive area

### 5.4 Industry Adaptation

The taxonomy remains constant across industries; adaptation occurs through:

- **Level 3 interpretation**: What "production" means varies by industry
- **Naming**: Industry-specific terminology in system, package and file names
- **System implementation**: Industry-specific code procedures and knowledge in asdf systems

## 6. Specification Conformance

### 6.1 Mandatory Requirements

Implementations SHALL:

1. Maintain exactly the multi level structure defined in Section 2
2. Use exactly the process areas defined in Section 2
3. Implement exactly the subdirectories at Level 4 as defined in Section 2.5 and in the data-system-specification
4. Treat Levels 0-4 as immutable
5. Use self-documenting asdf system names, package names and file names as documented in data-system-specification

### 6.2 Optional Extensions

Implementations MAY:

1. Add internal metadata via dated comments within code files ;; (<YYYY-MM-DD> tags:<> etc)
1. Add internal metadata via dated comments within code files ;; <YYYY-MM-DD> description of why something has been done
3. Implement additional tooling for taxonomy navigation
4. Implement version control systems
5. Implement automated compliance checking

### 6.3 Prohibited Modifications

Implementations SHALL NOT:

1. Create additional taxonomy levels beyond Level 3
2. Modify or rename Level 0-3 categories
3. Add or remove Level 4 subdirectories
4. Restructure the hierarchy
5. Create alternative parallel taxonomies

## 7. Taxonomy Usage Patterns

### Directive Interpretation

When an agent receives or reviews an executive-directive, it should:

Parse the directive into objectives, constraints, values, methods, and affected domains
Map each to relevant third-level process areas
Create or update systems in interpreted-executive-directive
Identify cross-process dependencies and document them
Generate metrics to track progress
Assess existing asdf systems
Modify existing asdf systems only if appropriate
Create additional asdf systems only if needed
Create tests to ensure processes and software are aligned and correct
Assess and modify existing asdf systems to harmonize them with the system
Assess the alignment and effectiveness and harmony of the overall system
Review the executive-directive

### Periodic Review and Self-Correction

Agents should regularly:

Re-read executive-directive and coordination/governance/interpreted-executive-directive/
Verify that populated process areas still align with intent
Check for new directive implications not yet captured
Audit metrics for accuracy and relevance
Audit knowledge base (LISA and SCREAMER) for accuracy and relevance
Consolidate or refactor code and rules as understanding evolves
Update documentation to reflect current state

### Filesystem Navigation
Agents navigate by understanding:

Stream (which fundamental flow?)
Function (which universal business activity?)
Process Area (which specific process?)
Data Type (which representation?)

Example: "Where should I put manufacturing defect tracking?"

Stream: value-stream/ (it's about product creation)
Function: fulfillment/ (it's about production)
Process Area: quality-assurance/ (it's about defects)
Data Type: sqlite-asdf-systems/defect-tracking.asd (this system defines and exports pertinent packages, symbols and functions)

## 8. Appendices

### Appendix A: Complete Taxonomy Tree

See Section 2.4 for complete three-level tree structure.

### Appendix B: Example Directive Mappings

**"Reduce manufacturing defects to below 0.5%"**
- Primary: value-stream/fulfillment/quality-assurance/
- Supporting: knowledge-stream/learning/skills-development/
- Supporting: resource-stream/infrastructure/equipment/
- Governance: coordination/governance/performance-oversight/

**"Launch new product"**
- Primary: value-stream/customer-interface/market-analysis/
- Supporting: knowledge-stream/insight/customer-research/
- Supporting: resource-stream/people/recruiting/
- Supporting: value-stream/supply/sourcing/

**"Reduce operational costs by 15%"**
- Primary: resource-stream/capital/cost-management/
- Supporting: coordination/flow-optimization/process-improvement/
- Supporting: value-stream/fulfillment/production/

**"Implement lean manufacturing"**
- Primary: coordination/flow-optimization/process-improvement/
- Touches: All of value-stream/
- Supporting: knowledge-stream/learning/kaizen/

### Appendix C: Glossary

**Process Area**: A Level 3 category representing a specific business process

**Stream**: A Level 1 category representing a fundamental business flow

**Function**: A Level 2 category representing a universal business activity

**Directive**: Executive guidance defining organizational objectives and constraints

**TPS**: Toyota Production System, a comprehensive approach to manufacturing and process management

**Kaizen**: Continuous improvement through incremental changes

**Jidoka**: Automation with human intelligence; building quality into processes

**Just-in-Time**: Producing exactly what is needed, when needed, in the amount needed

**Heijunka**: Production leveling to smooth demand variability

---
