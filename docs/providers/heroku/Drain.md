# Terraform::Heroku::Drain

Provides a Heroku Drain resource. This can be used to
create and manage Log Drains on Heroku.

## Properties

`Url` - (Required) The URL for Heroku to drain your logs to.

`App` - (Required) The Heroku app to link to.


## Return Values

### Fn::GetAtt

`Token` - The unique token for your created drain.

## See Also

* [heroku_drain](https://www.terraform.io/docs/providers/heroku/r/drain.html) in the _Terraform Provider Documentation_