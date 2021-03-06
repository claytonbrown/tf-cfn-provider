# Terraform::OCI::CoreInstancePool

This resource provides the Instance Pool resource in Oracle Cloud Infrastructure Core service.

Create an instance pool.

## Properties

`CompartmentId` - (Required) The OCID of the compartment containing the instance pool.

`DefinedTags` - (Optional) (Updatable) Defined tags for this resource. Each key is predefined and scoped to a namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Operations.CostCenter": "42"}`.

`DisplayName` - (Optional) (Updatable) The user-friendly name.  Does not have to be unique.

`FreeformTags` - (Optional) (Updatable) Free-form tags for this resource. Each tag is a simple key-value pair with no predefined name, type, or namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Department": "Finance"}`.

`InstanceConfigurationId` - (Required) (Updatable) The OCID of the instance configuration associated to the instance pool.

`PlacementConfigurations` - (Required) (Updatable) The placement configurations for the instance pool. There should be 1 placement configuration for each desired AD.
* `AvailabilityDomain` - (Required) (Updatable) The availability domain to place instances. Example: `Uocm:PHX-AD-1`
* `PrimarySubnetId` - (Required) (Updatable) The OCID of the primary subnet to place instances.
* `SecondaryVnicSubnets` - (Optional) (Updatable) The set of secondary VNIC data for instances in the pool.
* `DisplayName` - (Optional) (Updatable) The displayName of the vnic. This is also use to match against the Instance Configuration defined secondary vnic.
* `SubnetId` - (Required) (Updatable) The subnet OCID for the secondary vnic.

`AvailabilityDomain` - (Required) (Updatable) The availability domain to place instances. Example: `Uocm:PHX-AD-1`
* `PrimarySubnetId` - (Required) (Updatable) The OCID of the primary subnet to place instances.
* `SecondaryVnicSubnets` - (Optional) (Updatable) The set of secondary VNIC data for instances in the pool.
* `DisplayName` - (Optional) (Updatable) The displayName of the vnic. This is also use to match against the Instance Configuration defined secondary vnic.
* `SubnetId` - (Required) (Updatable) The subnet OCID for the secondary vnic.

`PrimarySubnetId` - (Required) (Updatable) The OCID of the primary subnet to place instances.
* `SecondaryVnicSubnets` - (Optional) (Updatable) The set of secondary VNIC data for instances in the pool.
* `DisplayName` - (Optional) (Updatable) The displayName of the vnic. This is also use to match against the Instance Configuration defined secondary vnic.
* `SubnetId` - (Required) (Updatable) The subnet OCID for the secondary vnic.

`SecondaryVnicSubnets` - (Optional) (Updatable) The set of secondary VNIC data for instances in the pool.
* `DisplayName` - (Optional) (Updatable) The displayName of the vnic. This is also use to match against the Instance Configuration defined secondary vnic.
* `SubnetId` - (Required) (Updatable) The subnet OCID for the secondary vnic.

`DisplayName` - (Optional) (Updatable) The displayName of the vnic. This is also use to match against the Instance Configuration defined secondary vnic.
* `SubnetId` - (Required) (Updatable) The subnet OCID for the secondary vnic.

`SubnetId` - (Required) (Updatable) The subnet OCID for the secondary vnic.

`Size` - (Required) (Updatable) The number of instances that should be in the instance pool.


## Return Values

### Fn::GetAtt

`CompartmentId` - The OCID of the compartment containing the instance pool.

`DefinedTags` - Defined tags for this resource. Each key is predefined and scoped to a namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Operations.CostCenter": "42"}`.

`DisplayName` - The displayName of the vnic. This is also use to match against the Instance Configuration defined secondary vnic.

`FreeformTags` - Free-form tags for this resource. Each tag is a simple key-value pair with no predefined name, type, or namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Department": "Finance"}`.

`Id` - The OCID of the instance pool.

`InstanceConfigurationId` - The OCID of the instance configuration associated to the intance pool.

`PlacementConfigurations` - The placement configurations for the instance pool.

`AvailabilityDomain` - The availability domain to place instances. Example: `Uocm:PHX-AD-1`.

`PrimarySubnetId` - The OCID of the primary subnet to place instances.

`SecondaryVnicSubnets` - The set of secondary VNIC data for instances in the pool.

`SubnetId` - The subnet OCID for the secondary vnic.

`Size` - The number of instances that should be in the instance pool.

`State` - The current state of the instance pool.

`TimeCreated` - The date and time the instance pool was created, in the format defined by RFC3339. Example: `2016-08-25T21:10:29.600Z`.

## See Also

* [oci_core_instance_pool](https://www.terraform.io/docs/providers/oci/r/core_instance_pool.html) in the _Terraform Provider Documentation_