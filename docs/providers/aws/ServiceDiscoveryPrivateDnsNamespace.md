# Terraform::AWS::ServiceDiscoveryPrivateDnsNamespace

Provides a Service Discovery Private DNS Namespace resource.

## Properties

`Name` - (Required) The name of the namespace.

`Vpc` - (Required) The ID of VPC that you want to associate the namespace with.

`Description` - (Optional) The description that you specify for the namespace when you create it.


## Return Values

### Fn::GetAtt

`Id` - The ID of a namespace.

`Arn` - The ARN that Amazon Route 53 assigns to the namespace when you create it.

`HostedZone` - The ID for the hosted zone that Amazon Route 53 creates when you create a namespace.

## See Also

* [aws_service_discovery_private_dns_namespace](https://www.terraform.io/docs/providers/aws/r/service_discovery_private_dns_namespace.html) in the _Terraform Provider Documentation_