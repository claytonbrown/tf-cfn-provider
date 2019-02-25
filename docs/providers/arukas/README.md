# Arukas Provider

## Configuration

To configure this resource, you must create an AWS Secrets Manager secret with the name **terraform/arukas** or add [template metadata](https://github.com/iann0036/tf-cfn-provider/blob/master/examples/metadata.yaml). The below arguments may be included as the key/value or JSON properties in the secret or metadata object:

* `token` - (Required) This is the Arukas API token.

* `secret` - (Required) This is the Arukas API secret.

* `api_url` - (Optional) Override Arukas API Root URL.

* `trace` - (Optional) The flag of Arukas API trace log.

* `timeout` - (Optional) Override Arukas API timeout seconds.


## Supported Resources

* [Terraform::Arukas::Container](Container.md)