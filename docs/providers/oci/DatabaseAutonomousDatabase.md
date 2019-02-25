# Terraform::OCI::DatabaseAutonomousDatabase

This resource provides the Autonomous Database resource in Oracle Cloud Infrastructure Database service.

Creates a new Autonomous Database.

## Properties

`AdminPassword` - (Required) (Updatable) The password must be between 12 and 30 characters long, and must contain at least 1 uppercase, 1 lowercase, and 1 numeric character. It cannot contain the double quote symbol (") or the username "admin", regardless of casing.

`CompartmentId` - (Required) The [OCID](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/identifiers.htm) of the compartment of the autonomous database.

`CpuCoreCount` - (Required) (Updatable) The number of CPU Cores to be made available to the database.

`DataStorageSizeInTbs` - (Required) (Updatable) The size, in terabytes, of the data volume that will be created and attached to the database. This storage can later be scaled up if needed.

`DbName` - (Required) The database name. The name must begin with an alphabetic character and can contain a maximum of 14 alphanumeric characters. Special characters are not permitted. The database name must be unique in the tenancy.

`DefinedTags` - (Optional) (Updatable) Defined tags for this resource. Each key is predefined and scoped to a namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Operations.CostCenter": "42"}`.

`DisplayName` - (Optional) (Updatable) The user-friendly name for the Autonomous Database. The name does not have to be unique.

`FreeformTags` - (Optional) (Updatable) Free-form tags for this resource. Each tag is a simple key-value pair with no predefined name, type, or namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Department": "Finance"}`.

`LicenseModel` - (Optional) The Oracle license model that applies to the Oracle Autonomous Database. The default is BRING_YOUR_OWN_LICENSE.


## Return Values

### Fn::GetAtt

`CompartmentId` - The [OCID](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/identifiers.htm) of the compartment.

`ConnectionStrings` - The connection string used to connect to the Autonomous Database. The username for the Service Console is ADMIN. Use the password you entered when creating the Autonomous Database for the password value.

`AllConnectionStrings` - Returns all connection strings that can be used to connect to the Autonomous Database. For more information, please see [Predefined Database Service Names for Autonomous Transaction Processing](https://docs.oracle.com/en/cloud/paas/atp-cloud/atpug/connect-predefined.html#GUID-9747539B-FD46-44F1-8FF8-F5AC650F15BE).

`High` - The High database service provides the highest level of resources to each SQL statement resulting in the highest performance, but supports the fewest number of concurrent SQL statements.

`Low` - The Low database service provides the least level of resources to each SQL statement, but supports the most number of concurrent SQL statements.

`Medium` - The Medium database service provides a lower level of resources to each SQL statement potentially resulting a lower level of performance, but supports more concurrent SQL statements.

`CpuCoreCount` - The number of CPU cores to be made available to the database.

`DataStorageSizeInTbs` - The quantity of data in the database, in terabytes.

`DbName` - The database name.

`DbVersion` - A valid Oracle Database version for Autonomous Database.

`DefinedTags` - Defined tags for this resource. Each key is predefined and scoped to a namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Operations.CostCenter": "42"}`.

`DisplayName` - The user-friendly name for the Autonomous Database. The name does not have to be unique.

`FreeformTags` - Free-form tags for this resource. Each tag is a simple key-value pair with no predefined name, type, or namespace. For more information, see [Resource Tags](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/resourcetags.htm).  Example: `{"Department": "Finance"}`.

`Id` - The [OCID](https://docs.cloud.oracle.com/iaas/Content/General/Concepts/identifiers.htm) of the Autonomous Database.

`LicenseModel` - The Oracle license model that applies to the Oracle Autonomous Database. The default is BRING_YOUR_OWN_LICENSE.

`LifecycleDetails` - Information about the current lifecycle state.

`ServiceConsoleUrl` - The URL of the Service Console for the Autonomous Database.

`State` - The current state of the database.

`TimeCreated` - The date and time the database was created.

## See Also

* [oci_database_autonomous_database](https://www.terraform.io/docs/providers/oci/r/database_autonomous_database.html) in the _Terraform Provider Documentation_