# Terraform::VCD::FirewallRules

Provides a vCloud Director Firewall resource. This can be used to create,
modify, and delete firewall settings and rules.

## Properties

`EdgeGateway` - (Required) The name of the edge gateway on which to apply the Firewall Rules.

`DefaultAction` - (Required) Either "allow" or "deny". Specifies what to do should none of the rules match.

`Rule` - (Optional) Configures a firewall rule; see [Rules](#rules) below for details.


## See Also

* [vcd_firewall_rules](https://www.terraform.io/docs/providers/vcd/r/firewall_rules.html) in the _Terraform Provider Documentation_