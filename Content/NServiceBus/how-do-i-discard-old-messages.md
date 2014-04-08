---
title: How to Discard Old Messages?
summary: Automatically discard messages if they have not been processed within a given period of time.
tags:
- Message Expiration
- TimeToBeReceived
---


If a message cannot be received by the target process in the given time frame, including all time in queues and in transit, you may want to discard the message.

To discard a message when a specific time interval has elapsed:

```C#
[TimeToBeReceived("00:01:00")] // Discard after one minute
[Recoverable]
public class MyMessage { }
```

The message expiration can also be configured as an overall override for Audit trail messages by using the tweaking the OverrideTimeToBeReceived over the configuration file

For example, discarding message from the audit trail after 60 min :

```C#
<AuditConfig QueueName="audit" OverrideTimeToBeReceived="0:60:0"/>
```
