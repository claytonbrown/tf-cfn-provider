# Terraform::Vault::AwsAuthBackendCert

Manages a certificate to be used with an AWS Auth Backend in Vault.

This resource sets the AWS public key and the type of document that can be
verified against the key that Vault can then use to verify the instance
identity documents making auth requests.

For more information, see the [Vault
docs](https://www.vaultproject.io/api/auth/aws/index.html#configure-client).

~> **Important** All data provided in the resource configuration will be
written in cleartext to state and plan files generated by Terraform, and will
appear in the console output when Terraform runs. Protect these artifacts
accordingly. See [the main provider documentation](../index.html) for more
details.

## Properties

`CertName` - (Required) The name of the certificate.

`AwsPublicCert` - (Required) The  Base64 encoded AWS Public key required to verify PKCS7 signature of the EC2 instance metadata. You can find this key in the [AWS documentation](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-identity-documents.html).

`Type` - (Optional) Either "pkcs7" or "identity", indicating the type of document which can be verified using the given certificate. Defaults to "pkcs7".

`Backend` - (Optional) The path the AWS auth backend being configured was mounted at.  Defaults to `aws`.


## See Also

* [vault_aws_auth_backend_cert](https://www.terraform.io/docs/providers/vault/r/aws_auth_backend_cert.html) in the _Terraform Provider Documentation_