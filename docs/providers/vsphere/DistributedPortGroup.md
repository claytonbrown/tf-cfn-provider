# Terraform::VSphere::DistributedPortGroup

The `Terraform::VSphere::DistributedPortGroup` resource can be used to manage vSphere
distributed virtual port groups. These port groups are connected to distributed
virtual switches, which can be managed by the
[`Terraform::VSphere::DistributedVirtualSwitch`][distributed-virtual-switch] resource.

Distributed port groups can be used as networks for virtual machines, allowing
VMs to use the networking supplied by a distributed virtual switch (DVS), with
a set of policies that apply to that individual newtork, if desired.

For an overview on vSphere networking concepts, see [this
page][ref-vsphere-net-concepts]. For more information on vSphere DVS
portgroups, see [this page][ref-vsphere-dvportgroup].

[distributed-virtual-switch]: /docs/providers/vsphere/r/distributed_virtual_switch.html
[ref-vsphere-net-concepts]: https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.networking.doc/GUID-2B11DBB8-CB3C-4AFF-8885-EFEA0FC562F4.html
[ref-vsphere-dvportgroup]: https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.networking.doc/GUID-69933F6E-2442-46CF-AA17-1196CB9A0A09.html

~> **NOTE:** This resource requires vCenter and is not available on direct ESXi
connections.

## Properties

`Name` - (Required) The name of the port group.

`DistributedVirtualSwitchUuid` - (Required) The ID of the DVS to add the
port group to. Forces a new resource if changed.

`Type` - (Optional) The port group type. Can be one of `earlyBinding` (static
binding) or `ephemeral`. Default: `earlyBinding`.

`Description` - (Optional) An optional description for the port group.

`NumberOfPorts` - (Optional) The number of ports available on this port
group. Cannot be decreased below the amount of used ports on the port group.

`AutoExpand` - (Optional) Allows the port group to create additional ports
past the limit specified in `NumberOfPorts` if necessary. Default: `true`.

`PortNameFormat` - (Optional) An optional formatting policy for naming of
the ports in this port group. See the `portNameFormat` attribute listed
[here][ext-vsphere-portname-format] for details on the format syntax.

`NetworkResourcePoolKey` - (Optional) The key of a network resource pool
to associate with this port group. The default is `-1`, which implies no
association.


## See Also

* [vsphere_distributed_port_group](https://www.terraform.io/docs/providers/vsphere/r/distributed_port_group.html) in the _Terraform Provider Documentation_