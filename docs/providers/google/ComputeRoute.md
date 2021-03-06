# Terraform::Google::ComputeRoute

Represents a Route resource.

A route is a rule that specifies how certain packets should be handled by
the virtual network. Routes are associated with virtual machines by tag,
and the set of routes for a particular virtual machine is called its
routing table. For each packet leaving a virtual machine, the system
searches that virtual machine's routing table for a single best matching
route.

Routes match packets by destination IP address, preferring smaller or more
specific ranges over larger ones. If there is a tie, the system selects
the route with the smallest priority value. If there is still a tie, it
uses the layer three and four packet headers to select just one of the
remaining matching routes. The packet is then forwarded as specified by
the next_hop field of the winning route -- either to another virtual
machine destination, a virtual machine gateway or a Compute
Engine-operated gateway. Packets that do not match any route in the
sending virtual machine's routing table will be dropped.

A Route resource must have exactly one specification of either
nextHopGateway, nextHopInstance, nextHopIp, or nextHopVpnTunnel.


To get more information about Route, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/rest/v1/routes)
* How-to Guides
    * [Using Routes](https://cloud.google.com/vpc/docs/using-routes)

<div class = "oics-button" style="float: right; margin: 0 0 -15px">
  <a href="https://console.cloud.google.com/cloudshell/open?cloudshell_git_repo=https%3A%2F%2Fgithub.com%2Fterraform-google-modules%2Fdocs-examples.git&cloudshell_working_dir=route_basic&cloudshell_image=gcr.io%2Fgraphite-cloud-shell-images%2Fterraform%3Alatest&open_in_editor=main.tf&cloudshell_print=.%2Fmotd&cloudshell_tutorial=.%2Ftutorial.md" target="_blank">
    <img alt="Open in Cloud Shell" src="//gstatic.com/cloudssh/images/open-btn.svg" style="max-height: 44px; margin: 32px auto; max-width: 100%;">
  </a>
</div>

## Properties

`Project` - (Optional) The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.

`NextHopInstanceZone` - (Optional when `NextHopInstance` is
specified)  The zone of the instance specified in
`NextHopInstance`.  Omit if `NextHopInstance` is specified as
a URL.


## Return Values

### Fn::GetAtt

`SelfLink` - The URI of the created resource.

## See Also

* [google_compute_route](https://www.terraform.io/docs/providers/google/r/compute_route.html) in the _Terraform Provider Documentation_