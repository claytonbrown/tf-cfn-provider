# Terraform::OPC::ComputeIpNetwork

The ``Terraform::OPC::ComputeIpNetwork`` resource creates and manages an IP Network in an Oracle Cloud Infrastructure Compute Classic identity domain.

## Properties

`Name` - (Required) The name of the IP Network. Changing this name forces a new resource to be created.

`IpAddressPrefix` - (Required) The IPv4 address prefix, in CIDR format.

`Description` - (Optional) The description of the IP Network.

`IpNetworkExchange` - (Optional) Specify the IP Network exchange to which the IP Network belongs to.

`PublicNaptEnabled` - (Optional) If true, enable public internet access using NAPT for VNICs without any public IP Reservation. Defaults to `false`.


## Return Values

### Fn::GetAtt

`Name` - The name of the IP Network.

`IpAddressPrefix` - The IPv4 address prefix, in CIDR format.

`Description` - The description of the IP Network.

`IpNetworkExchange` - The IP Network Exchange for the IP Network.

`PublicNaptEnabled` - Whether public internet access using NAPT for VNICs without any public IP Reservation or not.

`Uri` - Uniform Resource Identifier for the IP Network.

## See Also

* [opc_compute_ip_network](https://www.terraform.io/docs/providers/opc/r/compute_ip_network.html) in the _Terraform Provider Documentation_