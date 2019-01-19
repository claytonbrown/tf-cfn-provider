# Terraform::OCI::IdentityDynamicGroup

This resource provides the Dynamic Group resource in Oracle Cloud Infrastructure Identity service.

Creates a new dynamic group in your tenancy.

You must specify your tenancy's OCID as the compartment ID in the request object (remember that the tenancy
is simply the root compartment). Notice that IAM resources (users, groups, compartments, and some policies)
reside within the tenancy itself, unlike cloud resources such as compute instances, which typically
reside within compartments inside the tenancy. For information about OCIDs, see
[Resource Identifiers](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/identifiers.htm).

You must also specify a *name* for the dynamic group, which must be unique across all dynamic groups in your
tenancy, and cannot be changed. Note that this name has to be also unique accross all groups in your tenancy.
You can use this name or the OCID when writing policies that apply to the dynamic group. For more information
about policies, see [How Policies Work](https://docs.cloud.oracle.com/iaas/Content/Identity/Concepts/policies.htm).

You must also specify a *description* for the dynamic group (although it can be an empty string). It does not
have to be unique, and you can change it anytime with [UpdateDynamicGroup](https://docs.cloud.oracle.com/iaas/api/#/en/identity/20160918/DynamicGroup/UpdateDynamicGroup).

## Properties

`CompartmentId` - (Required) The OCID of the tenancy containing the group.

`Description` - (Required) (Updatable) The description you assign to the group during creation. Does not have to be unique, and it's changeable.

`MatchingRule` - (Required) (Updatable) The matching rule to dynamically match an instance certificate to this dynamic group. For rule syntax, see [Managing Dynamic Groups](https://docs.cloud.oracle.com/iaas/Content/Identity/Tasks/managingdynamicgroups.htm).

`Name` - (Required) The name you assign to the group during creation. The name must be unique across all groups in the tenancy and cannot be changed.


## Return Values

### Fn::GetAtt

`CompartmentId` - The OCID of the tenancy containing the group.

`Description` - The description you assign to the group. Does not have to be unique, and it's changeable.

`Id` - The OCID of the group.

`InactiveState` - The detailed status of INACTIVE lifecycleState.

`MatchingRule` - A rule string that defines which instance certificates will be matched. For syntax, see [Managing Dynamic Groups](https://docs.cloud.oracle.com/iaas/Content/Identity/Tasks/managingdynamicgroups.htm).

`Name` - The name you assign to the group during creation. The name must be unique across all groups in the tenancy and cannot be changed.

`State` - The group's current state.

`TimeCreated` - Date and time the group was created, in the format defined by RFC3339.  Example: `2016-08-25T21:10:29.600Z`.

## See Also

* [oci_identity_dynamic_group](https://www.terraform.io/docs/providers/oci/r/identity_dynamic_group.html) in the _Terraform Provider Documentation_