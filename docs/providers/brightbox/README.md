# Brightbox Provider

## Configuration

To configure this resource, you may optionally create an AWS Secrets Manager secret with the name **terraform/brightbox**. The below arguments may be included as the key/value or JSON properties in the secret:

* `apiclient` - (optional) This is the Brightbox client id for an
account.

* `apisecret` - (optional) This is the Brightbox client secret. This can
also be specified with the `BRIGHTBOX_CLIENT_SECRET` shell environment
variable.

* `username` - (optional) This is the Brightbox user logon. This can
also be specified with the `BRIGHTBOX_USER_NAME` shell environment
variable.

* `password` - (optional) This is the Brightbox user logon password. This
can also be specified with the `BRIGHTBOX_PASSWORD` shell environment
variable.

* `account` - (optional) This is the Brightbox account you wish to
operate upon.

* `apiurl` - (Optional) Use this to override the default endpoint URL
constructed for the region. It's typically used to connect to custom
Brightbox endpoints.

~> **NOTE:** At least one of `username` or `apiclient` must be specified.


## Supported Resources

* [Terraform::Brightbox::Cloudip](docs/providers/brightbox/Cloudip.md)
* [Terraform::Brightbox::Container](docs/providers/brightbox/Container.md)
* [Terraform::Brightbox::DatabaseServer](docs/providers/brightbox/DatabaseServer.md)
* [Terraform::Brightbox::FirewallPolicy](docs/providers/brightbox/FirewallPolicy.md)
* [Terraform::Brightbox::FirewallRule](docs/providers/brightbox/FirewallRule.md)
* [Terraform::Brightbox::LoadBalancer](docs/providers/brightbox/LoadBalancer.md)
* [Terraform::Brightbox::ServerGroup](docs/providers/brightbox/ServerGroup.md)
* [Terraform::Brightbox::Server](docs/providers/brightbox/Server.md)