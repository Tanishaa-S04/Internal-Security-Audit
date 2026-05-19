# Internal-Security-Audit
Conducted an internal IT security audit for a simulated retail company. Assessed asset inventory, identified control gaps, and evaluated compliance across NIST CSF, PCI-DSS, GDPR, and SOC standards. 8 of 14 controls were not in place. Risk score: 8/10.

# Case Study Background :
Botium Toys is a fictional U.S.-based toy retailer used as a simulated case study in the Google Cybersecurity Certificate program.
The company had a single physical location serving as its office, storefront, and warehouse, but was rapidly growing its online presence and serving international customers — including in the EU. The IT manager initiated an internal audit because the organization lacked a clear security strategy despite increasing pressure to maintain compliance and protect customer data. The goal was to assess existing controls, identify gaps, and determine risk exposure before those gaps led to a breach or a regulatory fine.

# My role: Act as a security analyst conducting the internal audit :
Reviewing the asset inventory and risk assessment, then completing a controls and compliance checklist to evaluate the organisation's security posture and readiness for compliance.

# What I Did :
Reviewed a risk assessment report and completed a controls and compliance checklist to audit a fictional toy retailer's security posture across administrative, technical, and physical control categories.

# Frameworks Used & How I Applied Them:
## 1. NIST Cybersecurity Framework (CSF) : 
The NIST CSF organises security into 5 functions: Identify, Protect, Detect, Respond, and Recover. I used all 5 as a lens to evaluate Botium Toys' security posture. 
### Identify: 
The starting point of the audit. Botium Toys had listed its assets but had not classified them or assessed the impact of losing them. Without knowing which assets are critical, the organisation cannot prioritise protection effectively. I flagged this as a foundational gap - you can't protect what you haven't identified.
### Protect:
This is where the most critical gaps were found. Encryption was not in place for customer credit card data or PII. Access controls like least privilege and separation of duties had not been implemented, meaning all employees could access sensitive data regardless of their role. Password policies were weak and not enforced through a management system.
### Detect :
Botium Toys had no Intrusion Detection System (IDS), meaning there was no mechanism to identify suspicious or malicious activity on the network. Legacy systems were monitored inconsistently with no defined schedule — creating blind spots.
### Respond :
No formal incident response procedures were in place. While a 72-hour breach notification plan existed for EU customers, there was no broader response plan covering how the organization would contain or investigate an incident.
### Recover :
No disaster recovery plan existed and no backups of critical data were maintained. A ransomware attack, hardware failure, or any data loss event could permanently disrupt business operations with no path to recovery.

## 2. PCI-DSS (Payment Card Industry Data Security Standard) :
PCI-DSS applies because Botium Toys accepts and processes customer credit card payments online. Any organization that handles cardholder data must meet these standards or risk heavy fines and loss of payment processing privileges.

### How I applied it:
I evaluated Botium Toys against PCI-DSS best practices and found that all 4 key requirements were not being met:
1. All employees had unrestricted access to cardholder data - violating the principle that only authorized users should have access.
2. Credit card information was stored and transmitted without encryption - a direct violation of PCI-DSS data protection requirements.
3. No encryption procedures were in place at payment touchpoints.
4. Password policies were weak with no centralized management system, making accounts vulnerable to brute force attacks.
   
Conclusion: Botium Toys was fully non-compliant with PCI-DSS at the time of the audit, exposing the company to regulatory fines and potential data breaches.

## 3. GDPR (General Data Protection Regulation):
GDPR applies because Botium Toys serves customers in the European Union. Any organization that collects or processes EU customer data must comply with GDPR regardless of where the company is based.
### How I applied it:
I assessed 4 GDPR requirements and found a mixed picture — 2 met, 2 not met:

Not met:
1. EU customer data was not adequately secured — no encryption meant financial and personal data was exposed.
2. Assets had been listed but not formally classified, meaning the organization could not fully account for what data it held or where.

Met:
1. A 72-hour breach notification plan was in place for EU customers — meeting one of GDPR's most critical requirements.
2. Privacy policies and procedures had been developed and were enforced among IT staff and employees.

Conclusion: Botium Toys had made some progress toward GDPR compliance, but remained at risk due to the absence of encryption and incomplete asset classification.

## 4. SOC Type 1 & Type 2
SOC reports verify whether an organization's data handling controls exist and work effectively over time.
1. SOC Type 1 checks whether the right controls exist on paper.
2. SOC Type 2 checks whether those controls actually operate effectively over time.
   
### How I applied it:
I evaluated 4 SOC-related best practices and found that 2 were not met:

Not met:
1. No user access policies were established — least privilege and separation of duties were absent, meaning all employees could access sensitive internal data.
2. PII and SPII were not kept confidential — no encryption meant sensitive personal data was unprotected.

Met:
1. Data integrity was maintained — data was consistent, complete, and accurate.
2. Data was available to those who needed it (though access was too broad and needed to be restricted)

Conclusion: Botium Toys partially met SOC requirements — data integrity and availability were in place, but access control policies and PII
confidentiality were not. Full SOC Type 1 compliance was not achieved, and SOC Type 2 was not achievable without first addressing these gaps.

Key Findings Summary : 
1. Administrative : Least privilege, separation of duties, disaster recovery, password policy.
2. Technical : Encryption, IDS, backups, password management system.
3. Physical : All physical controls were adequate.
   
# Risk Score: 8/10 (High)

# Recommendations :
## Priority order for remediation:
1. Implement encryption across all cardholder and PII data (critical — impacts PCI-DSS, GDPR, SOC).
2. Enforce least privilege and separation of duties.
3. Create a disaster recovery plan and set up critical data backups.
4. Deploy an Intrusion Detection System (IDS).
5. Strengthen password policy and implement a password management system.
6. Formally classify all assets and establish a legacy system maintenance schedule.
