# Terraform::CloudStack::VpnConnection

Creates a site to site VPN connection.

## Properties

`CustomerGatewayId` - (Required) The Customer Gateway ID to connect.
Changing this forces a new resource to be created.

`VpnGatewayId` - (Required) The VPN Gateway ID to connect. Changing
this forces a new resource to be created.


## Return Values

### Fn::GetAtt

`Id` - The ID of the VPN Connection.

## See Also

* [cloudstack_vpn_connection](https://www.terraform.io/docs/providers/cloudstack/r/vpn_connection.html) in the _Terraform Provider Documentation_