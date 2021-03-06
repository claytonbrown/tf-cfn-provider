# Terraform::AWS::LightsailInstance

Provides a Lightsail Instance. Amazon Lightsail is a service to provide easy virtual private servers
with custom software already setup. See [What is Amazon Lightsail?](https://lightsail.aws.amazon.com/ls/docs/getting-started/article/what-is-amazon-lightsail)
for more information.

~> **Note:** Lightsail is currently only supported in a limited number of AWS Regions, please see ["Regions and Availability Zones in Amazon Lightsail"](https://lightsail.aws.amazon.com/ls/docs/overview/article/understanding-regions-and-availability-zones-in-amazon-lightsail) for more details

## Properties

`Name` - (Required) The name of the Lightsail Instance.

`AvailabilityZone` - (Required) The Availability Zone in which to create your
instance (see list below).

`BlueprintId` - (Required) The ID for a virtual private server image
(see list below).

`BundleId` - (Required) The bundle of specification information (see list below).

`KeyPairName` - (Required) The name of your key pair. Created in the
Lightsail console (cannot use `Terraform::AWS::KeyPair` at this time).

`UserData` - (Optional) launch script to configure server with additional user data.


## Return Values

### Fn::GetAtt

`Id` - The ARN of the Lightsail instance (matches `arn`).

`Arn` - The ARN of the Lightsail instance (matches `id`).

## See Also

* [aws_lightsail_instance](https://www.terraform.io/docs/providers/aws/r/lightsail_instance.html) in the _Terraform Provider Documentation_