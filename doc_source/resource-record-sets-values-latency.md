# Values specific for latency records<a name="resource-record-sets-values-latency"></a>

When you create latency records, you specify the following values\.

**Topics**
+ [Routing policy](#rrsets-values-latency-routing-policy)
+ [Record name](#rrsets-values-latency-name)
+ [Record type](#rrsets-values-latency-type)
+ [TTL \(seconds\)](#rrsets-values-latency-ttl)
+ [Value/Route traffic to](#rrsets-values-latency-value)
+ [Region](#rrsets-values-latency-region)
+ [Health check](#rrsets-values-latency-associate-with-health-check)
+ [Record ID](#rrsets-values-latency-set-id)

## Routing policy<a name="rrsets-values-latency-routing-policy"></a>

Choose **Latency**\. 

## Record name<a name="rrsets-values-latency-name"></a>

Enter the name of the domain or subdomain that you want to route traffic for\. The default value is the name of the hosted zone\. 

**Note**  
If you're creating a record that has the same name as the hosted zone, don't enter a value \(for example, an @ symbol\) in the **Record name** field\. 

Enter the same name for all of the records in the group of latency records\. 

For more information about record names, see [Record name](resource-record-sets-values-shared.md#rrsets-values-common-name)\.

## Record type<a name="rrsets-values-latency-type"></a>

The DNS record type\. For more information, see [Supported DNS record types](ResourceRecordTypes.md)\.

Select the value for **Type** based on how you want Route 53 to respond to DNS queries\. 

Select the same value for all of the records in the group of latency records\.

## TTL \(seconds\)<a name="rrsets-values-latency-ttl"></a>

The amount of time, in seconds, that you want DNS recursive resolvers to cache information about this record\. If you specify a longer value \(for example, 172800 seconds, or two days\), you reduce the number of calls that DNS recursive resolvers must make to Route 53 to get the latest information in this record\. This has the effect of reducing latency and reducing your bill for Route 53 service\. For more information, see [How Amazon Route 53 routes traffic for your domain](welcome-dns-service.md#welcome-dns-service-how-route-53-routes-traffic)\.

However, if you specify a longer value for TTL, it takes longer for changes to the record \(for example, a new IP address\) to take effect because recursive resolvers use the values in their cache for longer periods before they ask Route 53 for the latest information\. If you're changing settings for a domain or subdomain that's already in use, we recommend that you initially specify a shorter value, such as 300 seconds, and increase the value after you confirm that the new settings are correct\.

If you're associating this record with a health check, we recommend that you specify a TTL of 60 seconds or less so clients respond quickly to changes in health status\.

## Value/Route traffic to<a name="rrsets-values-latency-value"></a>

Choose **IP address or another value depending on the record type**\. Enter a value that is appropriate for the value of **Record type**\. For all types except **CNAME**, you can enter more than one value\. Enter each value on a separate line\.

You can route traffic to, or specify the following values:
+ **A — IPv4 address**
+ **AAAA — IPv6 address**
+ **CAA — Certificate Authority Authorization**
+ **CNAME — Canonical name**
+ **MX — Mail exchange**
+ **NAPTR — Name Authority Pointer**
+ **PTR — Pointer**
+ **SPF — Sender Policy Framework**
+ **SRV — Service locator**
+ **TXT — Text**

For more information about the above values, see [Value/Route traffic to](resource-record-sets-values-shared.md#rrsets-values-common-value)\.

## Region<a name="rrsets-values-latency-region"></a>

The Amazon EC2 Region where the resource that you specified in this record resides\. Route 53 recommends an Amazon EC2 Region based on other values that you've specified\. We recommend that you not change this value\.

Note the following:
+ You can only create one latency record for each Amazon EC2 Region\.
+ You aren't required to create latency records for all Amazon EC2 Regions\. Route 53 chooses the Region with the best latency from among the Regions that you create latency records for\.
+ You can't create non\-latency records that have the same values for **Record name** and **Record type** as latency records\.
+ If you create a record tagged with the Region **cn\-north\-1**, Route 53 always responds to queries from within China using this record, regardless of the latency\.

For more information about using latency records, see [Latency\-based routing](routing-policy.md#routing-policy-latency)\. 

## Health check<a name="rrsets-values-latency-associate-with-health-check"></a>

Select a health check if you want Route 53 to check the health of a specified endpoint and to respond to DNS queries using this record only when the endpoint is healthy\. 

Route 53 doesn't check the health of the endpoint specified in the record, for example, the endpoint specified by the IP address in the **Value** field\. When you select a health check for a record, Route 53 checks the health of the endpoint that you specified in the health check\. For information about how Route 53 determines whether an endpoint is healthy, see [How Amazon Route 53 determines whether a health check is healthyHow Route 53 determines whether a health check is healthy](dns-failover-determining-health-of-endpoints.md)\.

Associating a health check with a record is useful only when Route 53 is choosing between two or more records to respond to a DNS query, and you want Route 53 to base the choice in part on the status of a health check\. Use health checks only in the following configurations:
+ You're checking the health of all of the records in a group of records that have the same name, type, and routing policy \(such as failover or weighted records\), and you specify health check IDs for all the records\. If the health check for a record specifies an endpoint that is not healthy, Route 53 stops responding to queries using the value for that record\.
+ You select **Yes** for **Evaluate target health** for an alias record or the records in a group of failover alias, geolocation alias, latency alias, or weighted alias record\. If the alias records reference non\-alias records in the same hosted zone, you must also specify health checks for the referenced records\. 

If your health checks specify the endpoint only by domain name, we recommend that you create a separate health check for each endpoint\. For example, create a health check for each HTTP server that is serving content for www\.example\.com\. For the value of **Domain name**, specify the domain name of the server \(such as us\-east\-2\-www\.example\.com\), not the name of the records \(example\.com\)\.

**Important**  
In this configuration, if you create a health check for which the value of **Domain name** matches the name of the records and then associate the health check with those records, health check results will be unpredictable\.

## Record ID<a name="rrsets-values-latency-set-id"></a>

Enter a value that uniquely identifies this record in the group of latency records\.