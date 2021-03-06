# Terraform::AWS::EmrSecurityConfiguration

Provides a resource to manage AWS EMR Security Configurations

## Properties

`Name` - (Optional) The name of the EMR Security Configuration. By default generated by Terraform.

`NamePrefix` - (Optional) Creates a unique name beginning with the specified
prefix. Conflicts with `Name`.

`Configuration` - (Required) A JSON formatted Security Configuration.


## Return Values

### Fn::GetAtt

`Id` - The ID of the EMR Security Configuration (Same as the `Name`).

`Name` - The Name of the EMR Security Configuration.

`Configuration` - The JSON formatted Security Configuration.

`CreationDate` - Date the Security Configuration was created.

## See Also

* [aws_emr_security_configuration](https://www.terraform.io/docs/providers/aws/r/emr_security_configuration.html) in the _Terraform Provider Documentation_