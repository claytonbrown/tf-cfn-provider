# Terraform::Google::ComputeProjectMetadata

Authoritatively manages metadata common to all instances for a project in GCE. For more information see
[the official documentation](https://cloud.google.com/compute/docs/storing-retrieving-metadata)
and
[API](https://cloud.google.com/compute/docs/reference/latest/projects/setCommonInstanceMetadata).

~> **Note:**  This resource manages all project-level metadata including project-level ssh keys.
Keys unset in config but set on the server will be removed. If you want to manage only single
key/value pairs within the project metadata rather than the entire set, then use
[google_compute_project_metadata_item](compute_project_metadata_item.html).

## Properties

`Metadata` - (Required) A series of key value pairs.

`Project` - (Optional) The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.


## See Also

* [google_compute_project_metadata](https://www.terraform.io/docs/providers/google/r/compute_project_metadata.html) in the _Terraform Provider Documentation_