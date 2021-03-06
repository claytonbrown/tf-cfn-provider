# Terraform::HuaweiCloud::DcsInstanceV1

Manages a DCS instance in the huaweicloud DCS Service.

## Properties

`Name` - (Required) Indicates the name of an instance. An instance name starts with a letter,
consists of 4 to 64 characters, and supports only letters, digits, and hyphens (-).

`Description` - (Optional) Indicates the description of an instance. It is a character
string containing not more than 1024 characters.

`Engine` - (Optional) Indicates a message engine. Options: rabbitmq and kafka. Changing this
creates a new instance.

`EngineVersion` - (Optional) Indicates the version of a message engine.
Changing this creates a new instance.

`Capacity` - (Required) Indicates the Cache capacity. Unit: GB.
For a DCS Redis or Memcached instance in single-node or master/standby mode, the cache
capacity can be 2 GB, 4 GB, 8 GB, 16 GB, 32 GB, or 64 GB.
For a DCS Redis instance in cluster mode, the cache capacity can be 64, 128, 256, 512,
or 1024 GB.
Changing this creates a new instance.

`PartitionNum` - (Optional) This parameter is mandatory when a Kafka instance is created.
Indicates the maximum number of topics in a Kafka instance.
When specification is 300 MB: 900
When specification is 600 MB: 1800
When specification is 1200 MB: 1800.

`AccessUser` - (Optional) Username used for accessing a DCS instance after password
authentication. A username starts with a letter, consists of 1 to 64 characters,
and supports only letters, digits, and hyphens (-).
Changing this creates a new instance.

`Password` - (Optional) Password of a DCS instance.
The password of a DCS Redis instance must meet the following complexity requirements:
Changing this creates a new instance.

`VpcId` - (Required) Tenant's VPC ID. For details on how to create VPCs, see the
Virtual Private Cloud API Reference.
Changing this creates a new instance.

`SecurityGroupId` - (Required) Tenant's security group ID. For details on how to
create security groups, see the Virtual Private Cloud API Reference.

`SubnetId` - (Required) Subnet ID. For details on how to create subnets, see the
Virtual Private Cloud API Reference.
Changing this creates a new instance.

`AvailableZones` - (Required) IDs of the AZs where cache nodes reside. For details
on how to query AZs, see Querying AZ Information.
Changing this creates a new instance.

`ProductId` - (Required) Product ID used to differentiate DCS instance types.
Changing this creates a new instance.

`MaintainBegin` - (Optional) Indicates the time at which a maintenance time window starts.
Format: HH:mm:ss.
The start time and end time of a maintenance time window must indicate the time segment of
a supported maintenance time window. For details, see section Querying Maintenance Time Windows.
The start time must be set to 22:00, 02:00, 06:00, 10:00, 14:00, or 18:00.
Parameters maintain_begin and maintain_end must be set in pairs. If parameter maintain_begin
is left blank, parameter maintain_end is also blank. In this case, the system automatically
allocates the default start time 02:00.

`MaintainEnd` - (Optional) Indicates the time at which a maintenance time window ends.
Format: HH:mm:ss.
The start time and end time of a maintenance time window must indicate the time segment of
a supported maintenance time window. For details, see section Querying Maintenance Time Windows.
The end time is four hours later than the start time. For example, if the start time is 22:00,
the end time is 02:00.
Parameters maintain_begin and maintain_end must be set in pairs. If parameter maintain_end is left
blank, parameter maintain_begin is also blank. In this case, the system automatically allocates
the default end time 06:00.

`SaveDays` - (Optional) Retention time. Unit: day. Range: 1–7. Changing this creates a new instance.

`BackupType` - (Optional) Backup type. Options:
auto: automatic backup.
manual: manual backup.
Changing this creates a new instance.

`BeginAt` - (Optional) Time at which backup starts. "00:00-01:00" indicates that backup
starts at 00:00:00. Changing this creates a new instance.

`PeriodType` - (Optional) Interval at which backup is performed. Currently, only weekly
backup is supported. Changing this creates a new instance.

`BackupAt` - (Optional) Day in a week on which backup starts. Range: 1–7. Where: 1
indicates Monday; 7 indicates Sunday. Changing this creates a new instance.


## Return Values

### Fn::GetAtt

`Name` - See Properties above.

`Description` - See Properties above.

`Engine` - See Properties above.

`EngineVersion` - See Properties above.

`Capacity` - See Properties above.

`AccessUser` - See Properties above.

`Password` - See Properties above.

`VpcId` - See Properties above.

`VpcName` - Indicates the name of a vpc.

`SecurityGroupId` - See Properties above.

`SecurityGroupName` - Indicates the name of a security group.

`SubnetId` - See Properties above.

`SubnetName` - Indicates the name of a subnet.

`AvailableZones` - See Properties above.

`ProductId` - See Properties above.

`MaintainBegin` - See Properties above.

`MaintainEnd` - See Properties above.

`SaveDays` - See Properties above.

`BackupType` - See Properties above.

`BeginAt` - See Properties above.

`PeriodType` - See Properties above.

`BackupAt` - See Properties above.

`OrderId` - An order ID is generated only in the monthly or yearly billing mode.

`Port` - Port of the cache node.

`ResourceSpecCode` - Resource specifications.

`UsedMemory` - Size of the used memory. Unit: MB.

`InternalVersion` - Internal DCS version.

`MaxMemory` - Overall memory size. Unit: MB.

`UserId` - Indicates a user ID.

`Ip` - Cache node's IP address in tenant's VPC.

## See Also

* [huaweicloud_dcs_instance_v1](https://www.terraform.io/docs/providers/huaweicloud/r/dcs_instance_v1.html) in the _Terraform Provider Documentation_