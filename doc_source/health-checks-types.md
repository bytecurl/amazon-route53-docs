# Types of Amazon Route 53 health checks<a name="health-checks-types"></a>

You can create the following types of Amazon Route 53 health checks:

**Health checks that monitor an endpoint**  
You can configure a health check that monitors an endpoint that you specify either by IP address or by domain name\. At regular intervals that you specify, Route 53 submits automated requests over the internet to your application, server, or other resource to verify that it's reachable, available, and functional\. Optionally, you can configure the health check to make requests similar to those that your users make, such as requesting a web page from a specific URL\.

**Health checks that monitor other health checks \(calculated health checks\)**  
You can create a health check that monitors whether Route 53 considers other health checks healthy or unhealthy\. One situation where this might be useful is when you have multiple resources that perform the same function, such as multiple web servers, and your chief concern is whether some minimum number of your resources are healthy\. You can create a health check for each resource without configuring notification for those health checks\. Then you can create a health check that monitors the status of the other health checks and that notifies you only when the number of available web resources drops below a specified threshold\.

**Health checks that monitor CloudWatch alarms**  
You can create CloudWatch alarms that monitor the status of CloudWatch metrics, such as the number of throttled read events for an Amazon DynamoDB database or the number of Elastic Load Balancing hosts that are considered healthy\. After you create an alarm, you can create a health check that monitors the same data stream that CloudWatch monitors for the alarm\.  
To improve resiliency and availability, Route 53 doesn't wait for the CloudWatch alarm to go into the `ALARM` state\. The status of a health check changes from healthy to unhealthy based on the data stream and on the criteria in the CloudWatch alarm\. 

**Amazon Route 53 Application Recovery Controller**  
Amazon Route 53 Application Recovery Controller gives you insights into whether your applications and resources are ready for recovery, and helps you manage and coordinate failover\. Health checks in Route 53 ARC are associated with routing controls, which are simple on/off switches\. You configure each routing control health check with a failover DNS record\. Then you can simply update your routing controls in Route 53 ARC to reroute traffic and fail over your applications, for example, across Availability Zones or AWS\-Regions\. For more information, see [Amazon Route 53 Application Recovery Controller Developer Guide](https://docs.aws.amazon.com/r53recovery/latest/dg/what-is-route-53-recovery.html)\.  
To learn more about readiness checks, see [Readiness check in Route 53 ARC](https://docs.aws.amazon.com/r53recovery/latest/dg/recovery-readiness.html), and to learn more about routing controls, see [Routing control in Route 53 ARC](https://docs.aws.amazon.com/r53recovery/latest/dg/routing-control.html) in the Route 53 ARC developer guide\.