Project 1: Azure Landing Zone
Author
Phumlani Magubane

Project Goal
Design and implement a secure Azure Landing Zone for a financial services organization inspired by Alex Forbes.

The Landing Zone establishes governance, networking, and security foundations before application teams begin deploying workloads into Azure.

Business Scenario
Alex Forbes Financial Services is beginning its Azure cloud journey.

The organization manages sensitive customer data including:

Retirement fund information
Investment portfolios
Employee benefits records
Personal customer information
The company requires a secure Azure foundation that supports:

Governance
Security
Compliance
Scalability
Future cloud growth
Project Requirements
Separate Production and Non-Production environments
Restrict deployments to approved Azure regions
Centralize governance
Standardize cloud deployment practices
Prepare for hybrid connectivity
Prepare for future shared services
Phase 1: Governance
Management Group Hierarchy
Implemented hierarchy:

Tenant Root Group
│
└── Alex Forbes Landing Zone
    ├── Production
    ├── Non-Production
    └── Platform
Why Management Groups?
Management Groups allow governance controls to be inherited by all child subscriptions and resources.

Benefits:

Centralized governance
Policy inheritance
Improved scalability
Reduced administrative effort
Azure Policy
Allowed Locations Policy
Scope
Alex Forbes Landing Zone

Allowed Regions
South Africa North
South Africa West
Policy Enforcement
Enabled

Business Reason
The organization requires all workloads to remain within approved South African Azure regions.

Benefits:

Data residency compliance
Reduced latency
Consistent governance
Regulatory alignment
Key Governance Concepts Learned
Inheritance
Policies assigned at a Management Group level automatically flow down to child resources.

Example:

Alex Forbes Landing Zone
        │
Production
        │
Subscription
        │
Resources
This allows a single policy assignment to govern multiple environments.

Phase 2: Network Planning
Hub-and-Spoke Network Design
A Hub-and-Spoke network model will be used.

The Hub Virtual Network hosts shared infrastructure services.

Future application workloads will be deployed into spoke VNets.

Hub Virtual Network
VNet Information
Setting	Value
Name	vnet-hub-prod
Region	South Africa North
Address Space	10.0.0.0/16
Subnet Design
Subnet	Address Range	Purpose
AzureFirewallSubnet	10.0.0.0/26	Azure Firewall
AzureBastionSubnet	10.0.1.0/26	Azure Bastion
GatewaySubnet	10.0.2.0/24	VPN Gateway
AzureFirewallManagementSubnet	10.0.3.0/26	Firewall Management

Why These Subnets?
 - AzureFirewallSubnet
 - Dedicated subnet for Azure Firewall deployment.
---
Purpose:

 - Traffic inspection
 - Network security
 - Centralized logging
 - AzureBastionSubnet
 - Dedicated subnet for Azure Bastion.

Purpose:

 - Secure VM access
 - Eliminate public RDP/SSH exposure
 - GatewaySubnet
 - Dedicated subnet for VPN Gateway.

Purpose:

 - Future Site-to-Site VPN connectivity
 - Hybrid cloud architecture
 - AzureFirewallManagementSubnet
 - Dedicated management subnet for Azure Firewall administration.

Purpose:

 - Segregate management traffic
 - Improve operational security
---
Current Progress
Completed
 - Created Management Group Hierarchy
 - Created Landing Zone Structure
 - Assigned Allowed Locations Policy
 - Designed Hub Network
 - Designed Subnet Layout
---
In Progress
 - Deploy Hub Virtual Network
---
Upcoming
 - Azure Firewall
 - Azure Bastion
 - VPN Gateway
 - Route Planning
 - Cost Analysis
 ---
Skills Demonstrated
 - Azure Governance
 - Management Groups
 - Azure Policy
 - Policy Inheritance
 - Azure Networking
 - Hub-and-Spoke Architecture
 - CIDR Planning
 - Azure Landing Zones
 ---
Lessons Learned
 - Governance should be implemented before deploying workloads.
 - Management Groups improve scalability through inheritance.
 - Azure Policy enforces standards automatically.
 - Hub-and-Spoke networking supports enterprise scalability.
 - Network planning should occur before infrastructure deployment.
 - Azure managed services require dedicated subnets.
  
