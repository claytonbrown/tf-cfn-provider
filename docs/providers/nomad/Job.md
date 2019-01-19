# Terraform::Nomad::Job

Manages a job registered in Nomad.

This can be used to initialize your cluster with system jobs, common services,
and more. In day to day Nomad use it is common for developers to submit jobs to
Nomad directly, such as for general app deployment. In addition to these apps, a
Nomad cluster often runs core system services that are ideally setup during
infrastructure creation. This resource is ideal for the latter type of job, but
can be used to manage any job within Nomad.

## Properties

TBC

## See Also

* [nomad_job](https://www.terraform.io/docs/providers/nomad/r/job.html) in the _Terraform Provider Documentation_