# Dyn Provider

## Configuration

To configure this resource, you must create an AWS Secrets Manager secret with the name **terraform/dyn** or add [template metadata](https://github.com/iann0036/tf-cfn-provider/blob/master/examples/metadata.yaml). The below arguments may be included as the key/value or JSON properties in the secret or metadata object:

* `customer_name` - (Required) The Dyn customer name.
* `username` - (Required) The Dyn username.
* `password` - (Required) The Dyn password.


## Supported Resources

* [Terraform::Dyn::Record](Record.md)