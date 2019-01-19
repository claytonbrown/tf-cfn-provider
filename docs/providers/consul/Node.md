# Terraform::Consul::Node

Provides access to Node data in Consul. This can be used to define a
node. Currently, defining health checks is not supported.

## Properties

`Address` - (Required) The address of the node being added to, or referenced in the catalog.

`Name` - (Required) The name of the node being added to, or referenced in the catalog.

`Meta` - (Optional, map) Key/value pairs that are associated with the node.


## Return Values

### Fn::GetAtt

`Address` - The address of the service.

`Name` - The name of the service.

`Meta` - (Optional, map) Key/value pairs that are associated with the node.

## See Also

* [consul_node](https://www.terraform.io/docs/providers/consul/r/node.html) in the _Terraform Provider Documentation_