# Terraform::NSXT::LbPool

Provides a resource to configure lb pool on NSX-T manager

## Properties

`DisplayName` - (Optional) The display name of this resource. Defaults to ID if not set.

`Description` - (Optional) Description of this resource.

`ActiveMonitorId` - (Optional) Active health monitor Id. If one is not set, the active healthchecks will be disabled.

`Algorithm` - (Optional) Load balancing algorithm controls how the incoming connections are distributed among the members. Supported algorithms are: ROUND_ROBIN, WEIGHTED_ROUND_ROBIN, LEAST_CONNECTION, WEIGHTED_LEAST_CONNECTION, IP_HASH.

`Member` - (Optional) Server pool consists of one or more pool members. Each pool member is identified, typically, by an IP address and a port. Each member has the following arguments:
* `AdminState` - (Optional) Pool member admin state. Possible values: ENABLED, DISABLED and GRACEFUL_DISABLED
* `BackupMember` - (Optional) A boolean flag which reflects whether this is a backup pool member. Backup servers are typically configured with a sorry page indicating to the user that the application is currently unavailable. While the pool is active (a specified minimum number of pool members are active) BACKUP members are skipped during server selection. When the pool is inactive, incoming connections are sent to only the BACKUP member(s).
* `DisplayName` - (Optional) The display name of this resource. pool member name.
* `IpAddress` - (Required) Pool member IP address.
* `MaxConcurrentConnections` - (Optional) To ensure members are not overloaded, connections to a member can be capped by the load balancer. When a member reaches this limit, it is skipped during server selection. If it is not specified, it means that connections are unlimited.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`AdminState` - (Optional) Pool member admin state. Possible values: ENABLED, DISABLED and GRACEFUL_DISABLED
* `BackupMember` - (Optional) A boolean flag which reflects whether this is a backup pool member. Backup servers are typically configured with a sorry page indicating to the user that the application is currently unavailable. While the pool is active (a specified minimum number of pool members are active) BACKUP members are skipped during server selection. When the pool is inactive, incoming connections are sent to only the BACKUP member(s).
* `DisplayName` - (Optional) The display name of this resource. pool member name.
* `IpAddress` - (Required) Pool member IP address.
* `MaxConcurrentConnections` - (Optional) To ensure members are not overloaded, connections to a member can be capped by the load balancer. When a member reaches this limit, it is skipped during server selection. If it is not specified, it means that connections are unlimited.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`BackupMember` - (Optional) A boolean flag which reflects whether this is a backup pool member. Backup servers are typically configured with a sorry page indicating to the user that the application is currently unavailable. While the pool is active (a specified minimum number of pool members are active) BACKUP members are skipped during server selection. When the pool is inactive, incoming connections are sent to only the BACKUP member(s).
* `DisplayName` - (Optional) The display name of this resource. pool member name.
* `IpAddress` - (Required) Pool member IP address.
* `MaxConcurrentConnections` - (Optional) To ensure members are not overloaded, connections to a member can be capped by the load balancer. When a member reaches this limit, it is skipped during server selection. If it is not specified, it means that connections are unlimited.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`DisplayName` - (Optional) The display name of this resource. pool member name.
* `IpAddress` - (Required) Pool member IP address.
* `MaxConcurrentConnections` - (Optional) To ensure members are not overloaded, connections to a member can be capped by the load balancer. When a member reaches this limit, it is skipped during server selection. If it is not specified, it means that connections are unlimited.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`IpAddress` - (Required) Pool member IP address.
* `MaxConcurrentConnections` - (Optional) To ensure members are not overloaded, connections to a member can be capped by the load balancer. When a member reaches this limit, it is skipped during server selection. If it is not specified, it means that connections are unlimited.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`MaxConcurrentConnections` - (Optional) To ensure members are not overloaded, connections to a member can be capped by the load balancer. When a member reaches this limit, it is skipped during server selection. If it is not specified, it means that connections are unlimited.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`Port` - (Optional) If port is specified, all connections will be sent to this port. Only single port is supported. If unset, the same port the client connected to will be used, it could be overrode by default_pool_member_port setting in virtual server. The port should not specified for port range case.
* `Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`Weight` - (Optional) Pool member weight is used for WEIGHTED_ROUND_ROBIN balancing algorithm. The weight value would be ignored in other algorithms.

`MemberGroup` - (Optional) Dynamic pool members for the loadbalancing pool. When member group is defined, members setting should not be specified. The member_group has the following arguments:
* `GroupingObject` - (Required) Grouping object of type NSGroup which will be used as dynamic pool members. The IP list of the grouping object would be used as pool member IP setting.
* `IpVersionFilter` - (Optional) Ip version filter is used to filter IPv4 or IPv6 addresses from the grouping object. If the filter is not specified, both IPv4 and IPv6 addresses would be used as server IPs. Supported filtering is "IPV4" and "IPV6" ("IPV4" is the default one)
* `LimitIpListSize` - (Optional) Limits the max number of pool members. If false, allows the dynamic pool to grow up to the load balancer max pool member capacity.
* `MaxIpListSize` - (Optional) Should only be specified if limit_ip_list_size is set to true. Limits the max number of pool members to the specified value.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. If unset, the same port the client connected to will be used, it could be overridden by default_pool_member_ports setting in virtual server. The port should not specified for multiple ports case.

`GroupingObject` - (Required) Grouping object of type NSGroup which will be used as dynamic pool members. The IP list of the grouping object would be used as pool member IP setting.
* `IpVersionFilter` - (Optional) Ip version filter is used to filter IPv4 or IPv6 addresses from the grouping object. If the filter is not specified, both IPv4 and IPv6 addresses would be used as server IPs. Supported filtering is "IPV4" and "IPV6" ("IPV4" is the default one)
* `LimitIpListSize` - (Optional) Limits the max number of pool members. If false, allows the dynamic pool to grow up to the load balancer max pool member capacity.
* `MaxIpListSize` - (Optional) Should only be specified if limit_ip_list_size is set to true. Limits the max number of pool members to the specified value.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. If unset, the same port the client connected to will be used, it could be overridden by default_pool_member_ports setting in virtual server. The port should not specified for multiple ports case.

`IpVersionFilter` - (Optional) Ip version filter is used to filter IPv4 or IPv6 addresses from the grouping object. If the filter is not specified, both IPv4 and IPv6 addresses would be used as server IPs. Supported filtering is "IPV4" and "IPV6" ("IPV4" is the default one)
* `LimitIpListSize` - (Optional) Limits the max number of pool members. If false, allows the dynamic pool to grow up to the load balancer max pool member capacity.
* `MaxIpListSize` - (Optional) Should only be specified if limit_ip_list_size is set to true. Limits the max number of pool members to the specified value.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. If unset, the same port the client connected to will be used, it could be overridden by default_pool_member_ports setting in virtual server. The port should not specified for multiple ports case.

`LimitIpListSize` - (Optional) Limits the max number of pool members. If false, allows the dynamic pool to grow up to the load balancer max pool member capacity.
* `MaxIpListSize` - (Optional) Should only be specified if limit_ip_list_size is set to true. Limits the max number of pool members to the specified value.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. If unset, the same port the client connected to will be used, it could be overridden by default_pool_member_ports setting in virtual server. The port should not specified for multiple ports case.

`MaxIpListSize` - (Optional) Should only be specified if limit_ip_list_size is set to true. Limits the max number of pool members to the specified value.
* `Port` - (Optional) If port is specified, all connections will be sent to this port. If unset, the same port the client connected to will be used, it could be overridden by default_pool_member_ports setting in virtual server. The port should not specified for multiple ports case.

`Port` - (Optional) If port is specified, all connections will be sent to this port. If unset, the same port the client connected to will be used, it could be overridden by default_pool_member_ports setting in virtual server. The port should not specified for multiple ports case.

`MinActiveMembers` - (Optional) The minimum number of members for the pool to be considered active. This value is 1 by default.

`PassiveMonitorId` - (Optional) Passive health monitor Id. If one is not set, the passive healthchecks will be disabled.

`Type` - (Optional) Type of SNAT performed to ensure reverse traffic from the server can be received and processed by the loadbalancer. Supported types are: SNAT_AUTO_MAP, SNAT_IP_POOL and TRANSPARENT
* `Ip` - (Required for snat_translation of type SNAT_IP_POOL) Ip address or Ip range for SNAT of type SNAT_IP_POOL.

`Ip` - (Required for snat_translation of type SNAT_IP_POOL) Ip address or Ip range for SNAT of type SNAT_IP_POOL.

`TcpMultiplexingEnabled` - (Optional) TCP multiplexing allows the same TCP connection between load balancer and the backend server to be used for sending multiple client requests from different client TCP connections. Disabled by default.

`TcpMultiplexingNumber` - (Optional) The maximum number of TCP connections per pool that are idly kept alive for sending future client requests. The default value for this is 6.

`Tag` - (Optional) A list of scope + tag pairs to associate with this lb pool.


## Return Values

### Fn::GetAtt

`Id` - ID of the lb pool.

`Revision` - Indicates current revision number of the object as seen by NSX-T API server. This attribute can be useful for debugging.

## See Also

* [nsxt_lb_pool](https://www.terraform.io/docs/providers/nsxt/r/lb_pool.html) in the _Terraform Provider Documentation_