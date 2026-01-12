# UEBA Behaviors Layer for Microsoft Sentinel

This contribution adds comprehensive behavior detection rules documentation and reference materials for Microsoft Sentinel's UEBA (User and Entity Behavior Analytics) Behaviors layer.

## What's Included

- **Workbooks/Sentinel_behaviors/**: Complete UEBA behaviors reference with 429 behavior detection rules
  - **README.md**: Overview and explanation of the Behaviors layer
  - **rules_format.md**: Documentation of the behavior file formats and structure
  - **use_cases.md**: SOC analyst, threat hunter, and detection engineer use cases with KQL examples
  - **Behaviors-rules/**: Organized behavior listings by data source in markdown table format
    - `aws_cloudtrail_behaviors.md` - 184 AWS CloudTrail behaviors
    - `gcp_auditlogs_behaviors.md` - 103 GCP Audit Logs behaviors
    - `commonsecuritylog_behaviors.md` - 142 CommonSecurityLog behaviors

## Target Audience

- **SOC Analysts**: Quick reference for behavior-based incident investigation
- **Threat Hunters**: Proactive hunting using behavior patterns and MITRE ATT&CK mappings
- **Detection Engineers**: Building analytics rules using behaviors as building blocks

## Data Sources Covered

- **AWS CloudTrail**: EC2, IAM, S3, EKS, Secrets Manager, and other AWS services
- **GCP Audit Logs**: Data Catalog, BigQuery, Compute Engine, IAM, Resource Manager
- **CommonSecurityLog**: CyberArk Vault, Palo Alto Networks, and other security appliances

## MITRE ATT&CK Coverage

All behaviors are mapped to MITRE ATT&CK tactics including Collection, Discovery, Defense Evasion, Initial Access, Persistence, Command and Control, Lateral Movement, and Privilege Escalation.

## Usage

Navigate to `Workbooks/Sentinel_behaviors/` for the complete reference. Each behavior includes both technical identifiers and human-readable descriptions to help security teams understand and utilize the Behaviors layer effectively.