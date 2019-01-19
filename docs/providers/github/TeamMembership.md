# Terraform::GitHub::TeamMembership

Provides a GitHub team membership resource.

This resource allows you to add/remove users from teams in your organization. When applied,
the user will be added to the team. If the user hasn't accepted their invitation to the
organization, they won't be part of the team until they do. When
destroyed, the user will be removed from the team.

## Properties

`TeamId` - (Required) The GitHub team id.

`Username` - (Required) The user to add to the team.

`Role` - (Optional) The role of the user within the team. Must be one of `member` or `maintainer`. Defaults to `member`.


## See Also

* [github_team_membership](https://www.terraform.io/docs/providers/github/r/team_membership.html) in the _Terraform Provider Documentation_