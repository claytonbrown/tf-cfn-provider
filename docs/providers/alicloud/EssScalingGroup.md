# Terraform::Alicloud::EssScalingGroup

Provides a ESS scaling group resource which is a collection of ECS instances with the same application scenarios.

It defines the maximum and minimum numbers of ECS instances in the group, and their associated Server Load Balancer instances, RDS instances, and other attributes.

~> **NOTE:** You can launch an ESS scaling group for a VPC network via specifying parameter `VswitchIds`.

## Properties

`MinSize` - (Required) Minimum number of ECS instances in the scaling group. Value range: [0, 1000].

`MaxSize` - (Required) Maximum number of ECS instances in the scaling group. Value range: [0, 1000].

`ScalingGroupName` - (Optional) Name shown for the scaling group, which must contain 2-40 characters (English or Chinese). If this parameter is not specified, the default value is ScalingGroupId.

`DefaultCooldown` - (Optional) Default cool-down time (in seconds) of the scaling group. Value range: [0, 86400]. The default value is 300s.

`VswitchId` - (Deprecated) It has been deprecated from version 1.7.1 and new field 'vswitch_ids' replaces it.

`VswitchIds` - (Optional) List of virtual switch IDs in which the ecs instances to be launched.

`RemovalPolicies` - (Optional) RemovalPolicy is used to select the ECS instances you want to remove from the scaling group when multiple candidates for removal exist. Optional values: - OldestInstance: removes the first ECS instance attached to the scaling group. - NewestInstance: removes the first ECS instance attached to the scaling group. - OldestScalingConfiguration: removes the ECS instance with the oldest scaling configuration. - Default values: OldestScalingConfiguration and OldestInstance. You can enter up to two removal policies.

`DbInstanceIds` - (Optional) If an RDS instance is specified in the scaling group, the scaling group automatically attaches the Intranet IP addresses of its ECS instances to the RDS access whitelist. - The specified RDS instance must be in running status. - The specified RDS instance’s whitelist must have room for more IP addresses.

`LoadbalancerIds` - (Optional) If a Server Load Balancer instance is specified in the scaling group, the scaling group automatically attaches its ECS instances to the Server Load Balancer instance. - The Server Load Balancer instance must be enabled. - At least one listener must be configured for each Server Load Balancer and it HealthCheck must be on. Otherwise, creation will fail (it may be useful to add a `DependsOn` argument targeting your `Terraform::Alicloud::SlbListener` in order to make sure the listener with its HealthCheck configuration is ready before creating your scaling group). - The Server Load Balancer instance attached with VPC-type ECS instances cannot be attached to the scaling group. - The default weight of an ECS instance attached to the Server Load Balancer instance is 50.

`MultiAzPolicy` - (Optional) Multi-AZ scaling group ECS instance expansion and contraction strategy. PRIORITY or BALANCE.


## Return Values

### Fn::GetAtt

`Id` - The scaling group ID.

`MinSize` - The minimum number of ECS instances.

`MaxSize` - The maximum number of ECS instances.

`ScalingGroupName` - The name of the scaling group.

`DefaultCooldown` - The default cool-down of the scaling group.

`RemovalPolicies` - The removal policy used to select the ECS instance to remove from the scaling group.

`DbInstanceIds` - The db instances id which the ECS instance attached to.

`LoadbalancerIds` - The slb instances id which the ECS instance attached to.

`VswitchIds` - The vswitches id in which the ECS instance launched.

## See Also

* [alicloud_ess_scaling_group](https://www.terraform.io/docs/providers/alicloud/r/ess_scaling_group.html) in the _Terraform Provider Documentation_