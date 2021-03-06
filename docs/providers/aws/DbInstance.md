# Terraform::AWS::DbInstance

Provides an RDS instance resource.  A DB instance is an isolated database
environment in the cloud.  A DB instance can contain multiple user-created
databases.

Changes to a DB instance can occur when you manually change a parameter, such as
`AllocatedStorage`, and are reflected in the next maintenance window. Because
of this, Terraform may report a difference in its planning phase because a
modification has not yet taken place. You can use the `ApplyImmediately` flag
to instruct the service to apply the change immediately (see documentation
below).

When upgrading the major version of an engine, `AllowMajorVersionUpgrade`
must be set to `true`.

~> **Note:** using `ApplyImmediately` can result in a brief downtime as the
server reboots. See the AWS Docs on [RDS Maintenance][2] for more information.

~> **Note:** All arguments including the username and password will be stored in
the raw state as plain-text. [Read more about sensitive data in
state](/docs/state/sensitive-data.html).

## Properties

`AllocatedStorage` - (Required unless a `SnapshotIdentifier` or
`ReplicateSourceDb` is provided) The allocated storage in gibibytes.

`AllowMajorVersionUpgrade` - (Optional) Indicates that major version
upgrades are allowed. Changing this parameter does not result in an outage and
the change is asynchronously applied as soon as possible.

`ApplyImmediately` - (Optional) Specifies whether any database modifications
are applied immediately, or during the next maintenance window. Default is
`false`. See [Amazon RDS Documentation for more
information.](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.DBInstance.Modifying.html)
for more information.

`AutoMinorVersionUpgrade` - (Optional) Indicates that minor engine upgrades
will be applied automatically to the DB instance during the maintenance window.
Defaults to true.

`AvailabilityZone` - (Optional) The AZ for the RDS instance.

`BackupRetentionPeriod` - (Optional) The days to retain backups for. Must be
between `0` and `35`. When creating a Read Replica the value must be greater than `0`. [See Read Replica][1].

`BackupWindow` - (Optional) The daily time range (in UTC) during which
automated backups are created if they are enabled. Example: "09:46-10:16". Must
not overlap with `MaintenanceWindow`.

`CharacterSetName` - (Optional) The character set name to use for DB
encoding in Oracle instances. This can't be changed. See [Oracle Character Sets
Supported in Amazon
RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Appendix.OracleCharacterSets.html)
for more information.

`DbSubnetGroupName` - (Optional) Name of [DB subnet group](/docs/providers/aws/r/db_subnet_group.html). DB instance will
be created in the VPC associated with the DB subnet group. If unspecified, will
be created in the `default` VPC, or in EC2 Classic, if available. When working
with read replicas, it needs to be specified only if the source database
specifies an instance in another AWS Region. See [DBSubnetGroupName in API
action CreateDBInstanceReadReplica](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBInstanceReadReplica.html)
for additional read replica contraints.

`DeletionProtection` - (Optional) If the DB instance should have deletion protection enabled. The database can't be deleted when this value is set to `true`. The default is `false`.

`Domain` - (Optional) The ID of the Directory Service Active Directory domain to create the instance in.

`DomainIamRoleName` - (Optional, but required if domain is provided) The name of the IAM role to be used when making API calls to the Directory Service.

`EnabledCloudwatchLogsExports` - (Optional) List of log types to enable for exporting to CloudWatch logs. If omitted, no logs will be exported. Valid values (depending on `Engine`): `alert`, `audit`, `error`, `general`, `listener`, `slowquery`, `trace`, `postgresql` (PostgreSQL), `upgrade` (PostgreSQL).

`Engine` - (Required unless a `SnapshotIdentifier` or `ReplicateSourceDb`
is provided) The database engine to use.  For supported values, see the Engine parameter in [API action CreateDBInstance](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBInstance.html).
Note that for Amazon Aurora instances the engine must match the [DB cluster](/docs/providers/aws/r/rds_cluster.html)'s engine'.
For information on the difference between the available Aurora MySQL engines
see [Comparison between Aurora MySQL 1 and Aurora MySQL 2](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AuroraMySQL.Updates.20180206.html)
in the Amazon RDS User Guide.

`EngineVersion` - (Optional) The engine version to use. If `AutoMinorVersionUpgrade`
is enabled, you can provide a prefix of the version such as `5.7` (for `5.7.10`) and
this attribute will ignore differences in the patch version automatically (e.g. `5.7.17`).
For supported values, see the EngineVersion parameter in [API action CreateDBInstance](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBInstance.html).
Note that for Amazon Aurora instances the engine version must match the [DB cluster](/docs/providers/aws/r/rds_cluster.html)'s engine version'.

`FinalSnapshotIdentifier` - (Optional) The name of your final DB snapshot
when this DB instance is deleted. If omitted, no final snapshot will be made.

`IamDatabaseAuthenticationEnabled` - (Optional) Specifies whether or
mappings of AWS Identity and Access Management (IAM) accounts to database
accounts is enabled.

`Identifier` - (Optional, Forces new resource) The name of the RDS instance,
if omitted, Terraform will assign a random, unique identifier.

`IdentifierPrefix` - (Optional, Forces new resource) Creates a unique
identifier beginning with the specified prefix. Conflicts with `Identifier`.

`InstanceClass` - (Required) The instance type of the RDS instance.

`Iops` - (Optional) The amount of provisioned IOPS. Setting this implies a
storage_type of "io1".

`KmsKeyId` - (Optional) The ARN for the KMS encryption key. If creating an
encrypted replica, set this to the destination KMS ARN.

`LicenseModel` - (Optional, but required for some DB engines, i.e. Oracle
SE1) License model information for this DB instance.

`MaintenanceWindow` - (Optional) The window to perform maintenance in.
Syntax: "ddd:hh24:mi-ddd:hh24:mi". Eg: "Mon:00:00-Mon:03:00". See [RDS
Maintenance Window
docs](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_UpgradeDBInstance.Maintenance.html#AdjustingTheMaintenanceWindow)
for more information.

`MonitoringInterval` - (Optional) The interval, in seconds, between points
when Enhanced Monitoring metrics are collected for the DB instance. To disable
collecting Enhanced Monitoring metrics, specify 0. The default is 0. Valid
Values: 0, 1, 5, 10, 15, 30, 60.

`MonitoringRoleArn` - (Optional) The ARN for the IAM role that permits RDS
to send enhanced monitoring metrics to CloudWatch Logs. You can find more
information on the [AWS
Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.html)
what IAM permissions are needed to allow Enhanced Monitoring for RDS Instances.

`MultiAz` - (Optional) Specifies if the RDS instance is multi-AZ.

`Name` - (Optional) The name of the database to create when the DB instance is created. If this parameter is not specified, no database is created in the DB instance. Note that this does not apply for Oracle or SQL Server engines. See the [AWS documentation](http://docs.aws.amazon.com/cli/latest/reference/rds/create-db-instance.html) for more details on what applies for those engines.

`OptionGroupName` - (Optional) Name of the DB option group to associate.

`ParameterGroupName` - (Optional) Name of the DB parameter group to
associate.

`Password` - (Required unless a `SnapshotIdentifier` or `ReplicateSourceDb`
is provided) Password for the master DB user. Note that this may show up in
logs, and it will be stored in the state file.

`Port` - (Optional) The port on which the DB accepts connections.

`PubliclyAccessible` - (Optional) Bool to control if instance is publicly
accessible. Default is `false`.

`ReplicateSourceDb` - (Optional) Specifies that this resource is a Replicate
database, and to use this value as the source database. This correlates to the
`Identifier` of another Amazon RDS Database to replicate. Note that if you are
creating a cross-region replica of an encrypted database you will also need to
specify a `KmsKeyId`. See [DB Instance Replication][1] and [Working with
PostgreSQL and MySQL Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)
for more information on using Replication.

`SecurityGroupNames` - (Optional/Deprecated) List of DB Security Groups to
associate. Only used for [DB Instances on the _EC2-Classic_
Platform](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html#USER_VPC.FindDefaultVPC).

`SkipFinalSnapshot` - (Optional) Determines whether a final DB snapshot is
created before the DB instance is deleted. If true is specified, no DBSnapshot
is created. If false is specified, a DB snapshot is created before the DB
instance is deleted, using the value from `FinalSnapshotIdentifier`. Default
is `false`.

`SnapshotIdentifier` - (Optional) Specifies whether or not to create this
database from a snapshot. This correlates to the snapshot ID you'd find in the
RDS console, e.g: rds:production-2015-06-26-06-05.

`StorageEncrypted` - (Optional) Specifies whether the DB instance is
encrypted. Note that if you are creating a cross-region read replica this field
is ignored and you should instead declare `KmsKeyId` with a valid ARN. The
default is `false` if not specified.

`StorageType` - (Optional) One of "standard" (magnetic), "gp2" (general
purpose SSD), or "io1" (provisioned IOPS SSD). The default is "io1" if `Iops` is
specified, "standard" if not. Note that this behaviour is different from the AWS
web console, where the default is "gp2".

`Tags` - (Optional) A mapping of tags to assign to the resource.

`Timezone` - (Optional) Time zone of the DB instance. `Timezone` is currently
only supported by Microsoft SQL Server. The `Timezone` can only be set on
creation. See [MSSQL User
Guide](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_SQLServer.html#SQLServer.Concepts.General.TimeZone)
for more information.

`Username` - (Required unless a `SnapshotIdentifier` or `ReplicateSourceDb`
is provided) Username for the master DB user.

`VpcSecurityGroupIds` - (Optional) List of VPC security groups to
associate.

`S3Import` - (Optional) Restore from a Percona Xtrabackup in S3.  See [Importing Data into an Amazon RDS MySQL DB Instance](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MySQL.Procedural.Importing.html).


## Return Values

### Fn::GetAtt

`Address` - The hostname of the RDS instance. See also `endpoint` and `Port`.

`Arn` - The ARN of the RDS instance.

`AllocatedStorage` - The amount of allocated storage.

`AvailabilityZone` - The availability zone of the instance.

`BackupRetentionPeriod` - The backup retention period.

`BackupWindow` - The backup window.

`CaCertIdentifier` - Specifies the identifier of the CA certificate for the.

`Domain` - The ID of the Directory Service Active Directory domain the instance is joined to.

`DomainIamRoleName` - The name of the IAM role to be used when making API calls to the Directory Service.

`Endpoint` - The connection endpoint in `address:port` format.

`Engine` - The database engine.

`EngineVersion` - The database engine version.

`HostedZoneId` - The canonical hosted zone ID of the DB instance (to be used.

`Id` - The RDS instance ID.

`InstanceClass` - The RDS instance class.

`MaintenanceWindow` - The instance maintenance window.

`MultiAz` - If the RDS instance is multi AZ enabled.

`Name` - The database name.

`Port` - The database port.

`ResourceId` - The RDS Resource ID of this instance.

`Status` - The RDS instance status.

`StorageEncrypted` - Specifies whether the DB instance is encrypted.

`Username` - The master username for the database.

`CharacterSetName` - The character set used on Oracle instances.

## See Also

* [aws_db_instance](https://www.terraform.io/docs/providers/aws/r/db_instance.html) in the _Terraform Provider Documentation_