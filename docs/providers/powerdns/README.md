# PowerDNS Provider

## Configuration

To configure this resource, you must create an AWS Secrets Manager secret with the name **terraform/powerdns** or add [template metadata](https://github.com/iann0036/tf-cfn-provider/blob/master/examples/metadata.yaml). The below arguments may be included as the key/value or JSON properties in the secret or metadata object:

* `api_key` - (Required) The PowerDNS API key.
* `server_url` - (Required) The address of PowerDNS server.


## Supported Resources

* [Terraform::PowerDNS::Record](Record.md)