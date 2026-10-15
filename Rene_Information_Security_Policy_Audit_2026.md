Corporate Information Security & Data Governance Policy
Document Reference: ISP-2026-v1.0
Effective Date: October 2026
Target Organization: Apex Global Logistics
1. Purpose and Scope
This Information Security Policy (ISP) establishes the foundational governance framework for protecting the confidentiality, integrity, and availability (CIA triad) of all digital assets, proprietary data, and network infrastructure within the Organization. Grounded in corporate jurisprudence and aligned with international security standards—specifically the NIST Cybersecurity Framework (CSF) and ISO/IEC 27001—this directive translates legal data privacy mandates into enforceable technical controls.
The scope of this policy applies universally to all personnel, third-party contractors, network systems, and physical infrastructure. It explicitly dictates the operational parameters for network segmentation, data transmission, and asset access boundaries. The primary objective is to systematically mitigate organizational risk, minimize regulatory liability, and protect sensitive data points from unauthorized exfiltration or compromise.
2. Regulatory & Legal Alignment
As a binding internal corporate directive, this policy serves as the operational implementation of the Organization's legal obligations under prevailing global data protection frameworks, including but not limited to the General Data Protection Regulation (GDPR) and equivalent cross-border privacy statutes. Non-compliance with the technical and administrative controls outlined herein constitutes a breach of corporate governance, exposing the entity to severe legal liability and operational risk, and will result in immediate disciplinary action up to and including contractual termination.
3. Technical Access Control Standards (Cisco ACL Implementation)
3.1 Administrative Policy: The Principle of Least Privilege
In accordance with global data protection mandates (GDPR Article 25 - Privacy by Design), the Organization strictly enforces the Principle of Least Privilege (PoLP). No user, endpoint, or department shall possess network access permissions beyond the absolute minimum required to execute their specific corporate functions. Broad, unrestricted internal network access is recognized as an unmitigated corporate liability and is expressly prohibited.
3.2 Technical Control: Network Segmentation via Cisco VLANs
To systematically isolate high-risk data repositories, the internal network architecture is logically segmented using virtual local area networks (VLANs). Network domains are strictly categorized as follows:
• VLAN 10 (Corporate Operations & HR): Contains restricted employee records, payroll infrastructure, and contract repositories.
• VLAN 20 (Finance & Accounting): Contains sensitive financial ledgers, transactional databases, and banking portals.
• VLAN 30 (Guest Wi-Fi): Provides isolated public internet access for visitors. This network is completely detached from the corporate backbone.
3.3 Enforcement Mechanism: Cisco Extended Access Control Lists (ACLs)
Logical boundaries between the configured VLANs are strictly enforced at the Layer 3 routing boundary using Cisco Extended Access Control Lists (ACLs). Unlike basic packet filtering, extended ACLs evaluate packet traffic based on source IP address, destination IP address, and specific TCP/UDP port protocols to ensure comprehensive compliance.
• Guest Network Isolation (VLAN 30): An inbound extended ACL is applied to the router interface of VLAN 30. This ACL contains an explicit deny rule preventing any IP packet originating from the guest pool from routing into the corporate subnets (VLAN 10 and VLAN 20).
• Inter-Departmental Filtering: To protect corporate financial records, a restricted ACL permits traffic to the Finance database server (VLAN 20) exclusively from verified static IP addresses within the Accounting department. All other transactional requests are dropped at the interface level.
• Protocol Restrictions: To secure remote administrative access, standard telnet traffic (Port 23) is completely blocked across all internal switches. All remote device management must be secured using encrypted SSH (Port 22) protocols, restricted entirely to the IT Administration VLAN.
