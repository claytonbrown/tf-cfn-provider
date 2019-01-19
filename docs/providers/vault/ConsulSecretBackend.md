# Terraform::Vault::ConsulSecretBackend

Creates a Consul Secret Backend for Vault. Consul secret backends can then issue Consul tokens, once a role has been added to the backend.

~> **Important** All data provided in the resource configuration will be
written in cleartext to state and plan files generated by Terraform, and
will appear in the console output when Terraform runs. Protect these
artifacts accordingly. See
[the main provider documentation](../index.html)
for more details.

## Properties

`Token` - (Required) The Consul management token this backend should use to issue new tokens.

`Backend` - (Optional) The unique location this backend should be mounted at. Must not begin or end with a `/`. Defaults to `consul`.

`Description` - (Optional) A human-friendly description for this backend.

`Address` - (Required) Specifies the address of the Consul instance, provided as "host:port" like "127.0.0.1:8500".

`Scheme` - (Optional) Specifies the URL scheme to use. Defaults to `http`.

`DefaultLeaseTtlSeconds` - (Optional) The default TTL for credentials issued by this backend.

`MaxLeaseTtlSeconds` - (Optional) The maximum TTL that can be requested for credentials issued by this backend.


## See Also

* [vault_consul_secret_backend](https://www.terraform.io/docs/providers/vault/r/consul_secret_backend.html) in the _Terraform Provider Documentation_