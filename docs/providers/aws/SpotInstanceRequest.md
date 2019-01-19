# Terraform::AWS::SpotInstanceRequest

Provides an EC2 Spot Instance Request resource. This allows instances to be
requested on the spot market.

By default Terraform creates Spot Instance Requests with a `persistent` type,
which means that for the duration of their lifetime, AWS will launch an
instance with the configured details if and when the spot market will accept
the requested price.

On destruction, Terraform will make an attempt to terminate the associated Spot
Instance if there is one present.

Spot Instances requests with a `one-time` type will close the spot request
when the instance is terminated either by the request being below the current spot
price availability or by a user.

~> **NOTE:** Because their behavior depends on the live status of the spot
market, Spot Instance Requests have a unique lifecycle that makes them behave
differently than other Terraform resources. Most importantly: there is __no
guarantee__ that a Spot Instance exists to fulfill the request at any given
point in time. See the [AWS Spot Instance
documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html)
for more information.

## Properties

`SpotPrice` - (Optional; Default: On-demand price) The maximum price to request on the spot market.

`WaitForFulfillment` - (Optional; Default: false) If set, Terraform will wait for the Spot Request to be fulfilled, and will throw an error if the timeout of 10m is reached.

`SpotType` - (Optional; Default: `persistent`) If set to `one-time`, after the instance is terminated, the spot request will be closed.

`LaunchGroup` - (Optional) A launch group is a group of spot instances that launch together and terminate together. If left empty instances are launched and terminated individually.

`BlockDurationMinutes` - (Optional) The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360). The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates. Note that you can't specify an Availability Zone group or a launch group if you specify a duration.

`InstanceInterruptionBehaviour` - (Optional) Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.

`ValidUntil` - (Optional) The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.

`ValidFrom` - (Optional) The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.

`Tags` - (Optional) A mapping of tags to assign to the resource.


## Return Values

### Fn::GetAtt

`Id` - The Spot Instance Request ID.

`SpotBidStatus` - The current [bid.

`SpotInstanceId` - The Instance ID (if any) that is currently fulfilling.

`PublicDns` - The public DNS name assigned to the instance. For EC2-VPC, this.

`PublicIp` - The public IP address assigned to the instance, if applicable.

`PrivateDns` - The private DNS name assigned to the instance. Can only be.

`PrivateIp` - The private IP address assigned to the instance.

## See Also

* [aws_spot_instance_request](https://www.terraform.io/docs/providers/aws/r/spot_instance_request.html) in the _Terraform Provider Documentation_