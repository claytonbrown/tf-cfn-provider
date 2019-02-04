# Terraform::Panos::PanoramaTemplateEntry

This resource allows you to add/update/delete a specific device in a Panorama
template.

This resource has some overlap with the `Terraform::Panos::PanoramaTemplate`
resource.  If you want to use this resource with the other one, then make
sure that your `Terraform::Panos::PanoramaTemplate` spec does not define any
`device` blocks, and just stays as "computed".

This is the appropriate resource to use if you have a pre-existing template
in Panorama and don't want Terraform to delete it on `terraform destroy`.

An interesting side effect of the underlying XML API - if the template does
not already exist, then this resource can actually create it.  However, since
only the single entry for the specific serial number is deleted, then a
`terraform destroy` would not remove the template itself in this situation.

## Properties

`Template` - (Required) The template name.

`Serial` - (Required) The serial number of the firewall.

`VsysList` - (Optional) A subset of all available vsys on the firewall
that should be in this template.  If the firewall is a virtual firewall,
then this parameter should just be omitted.


## See Also

* [panos_panorama_template_entry](https://www.terraform.io/docs/providers/panos/r/panorama_template_entry.html) in the _Terraform Provider Documentation_