# Behavior Rules Format Documentation

The behavior detection rules are organized into 3 data source files containing lists of behavior names.

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
  - string
  - string
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
- **Type**: Array of strings
- **Description**: Alphabetically sorted list of behavior names
- **Example**: `["BehaviorAccessKeyCredentialManagement", "BehaviorAnonymousS3Burst", ...]`

## Example Complete File

```yaml
dataSource: AWSCloudTrail
title: AWS CloudTrail Behaviors
description: List of behavior detection rules for AWS CloudTrail data source
totalBehaviors: 184
behaviors:
- BehaviorAccessKeyCredentialManagement
- BehaviorAnonymousS3Burst
- BehaviorAssumedRoleAccountAudit
- BehaviorCloudCidrAllocation
- BehaviorCredentialReportRetrieval
- BehaviorEC2ReservationModification
- BehaviorEbsEncryptionToggle
- BehaviorEbsSnapshotPermissionAudit
# ... (continues with all behavior names)
```

## Notes

- Behavior names are sorted alphabetically within each data source
- All behavior names follow the pattern `Behavior{DescriptiveName}`
- Each file represents a complete list for that specific data source
- Total of 3 files instead of individual behavior YAML files
- Simplified structure focused on behavior name organization by data source
