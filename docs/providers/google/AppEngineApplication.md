# Terraform::Google::AppEngineApplication

Allows creation and management of an App Engine application.

~> App Engine applications cannot be deleted once they're created; you have to delete the
   entire project to delete the application. Terraform will report the application has been
   successfully deleted; this is a limitation of Terraform, and will go away in the future.
   Terraform is not able to delete App Engine applications.

## Properties

`LocationId` - (Required) The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.

`AuthDomain` - (Optional) The domain to authenticate users with when using App Engine's User API.

`ServingStatus` - (Optional) The serving status of the app.

`FeatureSettings` - (Optional) A block of optional settings to configure specific App Engine features:.

### FeatureSettings Properties

`SplitHealthChecks` - (Optional) Set to false to use the legacy health check instead of the readiness
and liveness checks.


## Return Values

### Fn::GetAtt

`Name` - Unique name of the app, usually `apps/{PROJECT_ID}`.

`UrlDispatchRule` - A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.

`CodeBucket` - The GCS bucket code is being stored in for this app.

`DefaultHostname` - The default hostname for this app.

`DefaultBucket` - The GCS bucket content is being stored in for this app.

`GcrDomain` - The GCR domain used for storing managed Docker images for this app.

## See Also

* [google_app_engine_application](https://www.terraform.io/docs/providers/google/r/app_engine_application.html) in the _Terraform Provider Documentation_