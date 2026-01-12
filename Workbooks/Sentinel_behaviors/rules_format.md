# Behavior Rules Format Documentation

The behavior detection rules are organized into 3 data source files containing lists of behavior names and titles.

## File Structure

The `Behaviors-rules/` directory contains exactly 3 YAML files, one for each data source:

- `aws_cloudtrail_behaviors.yaml` - AWS CloudTrail behaviors
- `gcp_auditlogs_behaviors.yaml` - GCP Audit Logs behaviors
- `commonsecuritylog_behaviors.yaml` - CommonSecurityLog behaviors

## YAML File Format

Each data source file has the following structure:

```yaml
dataSource: string
title: string
description: string
totalBehaviors: number
behaviors:
  - behavior: string
    title: string
  - behavior: string
    title: string
  - ...
```

## Field Descriptions

### dataSource
- **Type**: String
- **Description**: The data source table name
- **Examples**: `AWSCloudTrail`, `GCPAuditLogs`, `CommonSecurityLog`

### title
- **Type**: String
- **Description**: Human-readable title for the data source
- **Example**: `AWS CloudTrail Behaviors`

### description
- **Type**: String
- **Description**: Description of the behavior rules for this data source
- **Example**: `List of behavior detection rules for AWS CloudTrail data source`

### totalBehaviors
- **Type**: Number
- **Description**: Total count of behaviors in this data source
- **Example**: `184`

### behaviors
- **Type**: Array of objects
- **Description**: Alphabetically sorted list of behavior objects containing behavior name and title
- **Structure**:
  ```yaml
  behaviors:
    - behavior: string
      title: string
  ```

#### behavior
- **Type**: String
- **Description**: Unique behavior identifier
- **Example**: `BehaviorAccessKeyCredentialManagement`

#### title
- **Type**: String
- **Description**: Human-readable descriptive title for the behavior
- **Example**: `IAM Principal Access Key And Service-Specific Credential Management Activity`

## Example Complete File

```yaml
dataSource: AWSCloudTrail
title: AWS CloudTrail Behaviors
description: List of behavior detection rules for AWS CloudTrail data source
totalBehaviors: 184
behaviors:
- behavior: BehaviorAccessKeyCredentialManagement
  title: IAM Principal Access Key And Service-Specific Credential Management Activity
- behavior: BehaviorAccessKeyEnumeration
  title: Credential Access – IAM Access Key Last-Used Enumeration Across Multiple Access Keys
- behavior: BehaviorAnonymousS3Burst
  title: Burst of Anonymous Web-Based S3 Object Access from Single External IP
- behavior: BehaviorAssumedRoleAccountAudit
  title: Discovery – Cross-Account AWS Assumed Role Policy Simulation and Evaluation
- behavior: BehaviorCloudCidrAllocation
  title: Cloud Network Address Space Management via EC2 IPAM Pool CIDR Allocation
- behavior: BehaviorCredentialReportRetrieval
  title: Discovery – IAM Credential Report Generation and Retrieval by AWS Principal
- behavior: BehaviorEC2ReservationModification
  title: Concentrated EC2 Capacity Reservation and Fleet Modifications by Assumed Role
- behavior: BehaviorEbsEncryptionToggle
  title: AWS Account Toggles EBS Default Volume Encryption Setting
# ... (continues with all behavior names and titles)
```

## Notes

- Behavior entries are sorted alphabetically by behavior name within each data source
- All behavior names follow the pattern `Behavior{DescriptiveName}`
- Each behavior includes both the technical name and human-readable title
- Titles provide clear descriptions of what each behavior detects
- Total of 3 files instead of individual behavior YAML files
- Enhanced structure focused on behavior name and title organization by data source
