# Terraform::Consul::KeyPrefix

Allows Terraform to manage a "namespace" of Consul keys that share a common
name prefix.

Like `Terraform::Consul::Keys`, this resource can write values into the Consul key/value
store, but *unlike* `Terraform::Consul::Keys` this resource can detect and remove extra
keys that have been added some other way, thus ensuring that rogue data
added outside of Terraform will be removed on the next run.

This resource is thus useful in the case where Terraform is exclusively
managing a set of related keys.

To avoid accidentally clobbering matching data that existed in Consul before
a `Terraform::Consul::KeyPrefix` resource was created, creation of a key prefix instance
will fail if any matching keys are already present in the key/value store.
If any conflicting data is present, you must first delete it manually.

~> **Warning** After this resource is instantiated, Terraform takes control
over *all* keys with the given path prefix, and will remove any matching keys
that are not present in the configuration. It will also delete *all* keys under
the given prefix when a `Terraform::Consul::KeyPrefix` resource is destroyed, even if
those keys were created outside of Terraform.

## Properties

`Datacenter` - (Optional) The datacenter to use. This overrides the
datacenter in the provider setup and the agent's default datacenter.

`Token` - (Optional) The ACL token to use. This overrides the
token that the agent provides by default.

`PathPrefix` - (Required) Specifies the common prefix shared by all keys
that will be managed by this resource instance. In most cases this will
end with a slash, to manage a "folder" of keys.

`Subkeys` - (Required) A mapping from subkey name (which will be appended
to the given `PathPrefix`) to the value that should be stored at that key.
Use slashes, as shown in the above example, to create "sub-folders" under
the given path prefix.


## Return Values

### Fn::GetAtt

`Datacenter` - The datacenter the keys are being read/written to.

## See Also

* [consul_key_prefix](https://www.terraform.io/docs/providers/consul/r/key_prefix.html) in the _Terraform Provider Documentation_