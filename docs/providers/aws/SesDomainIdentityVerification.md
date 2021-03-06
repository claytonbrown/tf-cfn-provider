# Terraform::AWS::SesDomainIdentityVerification

Represents a successful verification of an SES domain identity.

Most commonly, this resource is used together with [`Terraform::AWS::Route53Record`](route53_record.html) and
[`Terraform::AWS::SesDomainIdentity`](ses_domain_identity.html) to request an SES domain identity,
deploy the required DNS verification records, and wait for verification to complete.

~> **WARNING:** This resource implements a part of the verification workflow. It does not represent a real-world entity in AWS, therefore changing or deleting this resource on its own has no immediate effect.

## Properties

`Domain` - (Required) The domain name of the SES domain identity to verify.


## Return Values

### Fn::GetAtt

`Id` - The domain name of the domain identity.

`Arn` - The ARN of the domain identity.

## See Also

* [aws_ses_domain_identity_verification](https://www.terraform.io/docs/providers/aws/r/ses_domain_identity_verification.html) in the _Terraform Provider Documentation_