# Terraform::AWS::GuarddutyMember

Provides a resource to manage a GuardDuty member.

~> **NOTE:** Currently after using this resource, you must manually accept member account invitations before GuardDuty will begin sending cross-account events. More information for how to accomplish this via the AWS Console or API can be found in the [GuardDuty User Guide](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_accounts.html). Terraform implementation of the member acceptance resource can be tracked in [Github](https://github.com/terraform-providers/terraform-provider-aws/issues/2489).

## Properties

`AccountId` - (Required) AWS account ID for member account.

`DetectorId` - (Required) The detector ID of the GuardDuty account where you want to create member accounts.

`Email` - (Required) Email address for member account.

`Invite` - (Optional) Boolean whether to invite the account to GuardDuty as a member. Defaults to `false`. To detect if an invitation needs to be (re-)sent, the Terraform state value is `true` based on a `relationship_status` of `Disabled`, `Enabled`, `Invited`, or `EmailVerificationInProgress`.

`InvitationMessage` - (Optional) Message for invitation.

`DisableEmailNotification` - (Optional) Boolean whether an email notification is sent to the accounts. Defaults to `false`.


## Return Values

### Fn::GetAtt

`Id` - The ID of the GuardDuty member.

`RelationshipStatus` - The status of the relationship between the member account and its master account. More information can be found in [Amazon GuardDuty API Reference](https://docs.aws.amazon.com/guardduty/latest/ug/get-members.html).

## See Also

* [aws_guardduty_member](https://www.terraform.io/docs/providers/aws/r/guardduty_member.html) in the _Terraform Provider Documentation_