# Terraform::HuaweiCloud::DmsQueueV1

Manages a DMS queue in the huaweicloud DMS Service.

## Properties

`Name` - (Required) Indicates the unique name of a queue. A string of 1 to 64
characters that contain a-z, A-Z, 0-9, hyphens (-), and underscores (_).
The name cannot be modified once specified.

`QueueMode` - (Optional) Indicates the queue type. It only support 'NORMAL' and 'FIFO'.
NORMAL: Standard queue. Best-effort ordering. Messages might be retrieved in an order
different from which they were sent. Select standard queues when throughput is important.
FIFO: First-ln-First-out (FIFO) queue. FIFO delivery. Messages are retrieved in the
order they were sent. Select FIFO queues when the order of messages is important.
Default value: NORMAL.

`Description` - (Optional) Indicates the basic information about a queue. The queue
description must be 0 to 160 characters in length, and does not contain angle
brackets (<) and (>).

`RedrivePolicy` - (Optional) Indicates whether to enable dead letter messages.
Dead letter messages indicate messages that cannot be normally consumed.
The redrive_policy should be set to 'enable' or 'disable'. The default value is 'disable'.

`MaxConsumeCount` - (Optional) This parameter is mandatory only when redrive_policy is
set to enable. This parameter indicates the maximum number of allowed message consumption
failures. When a message fails to be consumed after the number of consumption attempts of
this message reaches this value, DMS stores this message into the dead letter queue.
The max_consume_count value range is 1–100.


## Return Values

### Fn::GetAtt

`Name` - See Properties above.

`QueueMode` - See Properties above.

`Description` - See Properties above.

`RedrivePolicy` - See Properties above.

`MaxConsumeCount` - See Properties above.

`Created` - Indicates the time when a queue is created.

`Reservation` - Indicates the retention period (unit: min) of a message in a queue.

`MaxMsgSizeByte` - Indicates the maximum message size (unit: byte) that is allowed in queue.

`ProducedMessages` - Indicates the total number of messages (not including the messages that have expired and been deleted) in a queue.

`GroupCount` - Indicates the total number of consumer groups in a queue.

## See Also

* [huaweicloud_dms_queue_v1](https://www.terraform.io/docs/providers/huaweicloud/r/dms_queue_v1.html) in the _Terraform Provider Documentation_