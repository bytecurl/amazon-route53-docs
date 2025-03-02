# Amazon Route 53 API permissions: Actions, resources, and conditions reference<a name="r53-api-permissions-ref"></a>

When you set up [Access control](auth-and-access-control.md#access-control) and write a permissions policy that you can attach to an IAM identity \(identity\-based policies\), you can use the following lists as a reference\. The lists include each Amazon Route 53 API action, the actions that you must grant permissions access to, and the AWS resource that you must grant access to\. You specify the actions in the policy's `Action` field, and you specify the resource value in the policy's `Resource` field\. 

You can use AWS\-wide condition keys in your Route 53 policies to express conditions\. For a complete list of AWS\-wide keys, see [Available keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html#AvailableKeys) in the *IAM User Guide*\. 

**Note**  
When granting access, the hosted zone and the Amazon VPC must belong to the same partition\. A partition is a group of AWS Regions\. Each AWS account is scoped to one partition\.  
The following are the supported partitions:  
`aws` \- AWS Regions
`aws-cn` \- China Regions
`aws-us-gov` \- AWS GovCloud \(US\) Region
For more information, see [Access Management](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html) in the *AWS General Reference*\.

**Note**  
To specify an action, use the applicable prefix \(`route53`, `route53domains`, or `route53resolver`\) followed by the API operation name, for example:  
`route53:CreateHostedZone`
`route53domains:RegisterDomain`
`route53resolver:CreateResolverEndpoint`

**Topics**
+ [Required permissions for actions on public hosted zones](#required-permissions-public-hosted-zones)
+ [Required permissions for actions on private hosted zones](#required-permissions-private-hosted-zones)
+ [Required permissions for actions on reusable delegation sets](#required-permissions-reusable-delegation-sets)
+ [Required permissions for actions on records](#required-permissions-resource-record-sets)
+ [Required permissions for actions on traffic policies](#required-permissions-traffic-policies)
+ [Required permissions for actions on traffic policy instances](#required-permissions-traffic-policy-instances)
+ [Required permissions for actions on health checks](#required-permissions-health-checks)
+ [Required permissions for actions on domain registrations](#required-permissions-domain-registrations)
+ [Required permissions for Route 53 Resolver actions](#required-permissions-resolver)
+ [Required permissions for Route 53 Resolver DNS Firewall actions](#required-permissions-resolver-dns-firewall)
+ [Required permissions for actions to get limits for accounts, hosted zones, and reusable delegation sets](#required-permissions-get-limits)
+ [Required permissions for actions on tags for hosted zones and health checks](#required-permissions-tags-hosted-zones)
+ [Required permissions for actions on tags for domains](#required-permissions-tags-domains)
+ [Required permissions for DNSSEC actions](#required-permissions-dnssec-signing)

## Required permissions for actions on public hosted zones<a name="required-permissions-public-hosted-zones"></a><a name="public-hosted-zones-table"></a>

[CreateHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateHostedZone.html)  
Required Permissions \(API Action\): `route53:CreateHostedZone`  
Resources: `*`

[DeleteHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteHostedZone.html)  
Required Permissions \(API Action\): `route53:DeleteHostedZone`  
Resources: `*`

[GetHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHostedZone.html)  
Required Permissions \(API Action\): `route53:GetHostedZone`  
Resources: `*`

[GetHostedZoneCount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHostedZoneCount.html)  
Required Permissions \(API Action\): `route53:GetHostedZoneCount`  
Resources: `*`

[ListHostedZones](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListHostedZones.html)  
Required Permissions \(API Action\): `route53:ListHostedZones`  
Resources: `*`

[ListHostedZonesByName](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListHostedZonesByName.html)  
Required Permissions \(API Action\): `route53:ListHostedZonesByName`  
Resources: `*`

[UpdateHostedZoneComment](https://docs.aws.amazon.com/Route53/latest/APIReference/API_UpdateHostedZoneComment.html)  
Required Permissions \(API Action\): `route53:UpdateHostedZoneComment`  
Resources: `*`

## Required permissions for actions on private hosted zones<a name="required-permissions-private-hosted-zones"></a><a name="private-hosted-zones-table"></a>

[CreateHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateHostedZone.html)  
Required Permissions \(API Action\): `route53:CreateHostedZone`, `ec2:DescribeVpcs`, `ec2:DescribeRegions`  
Resources: `*`, `arn:aws:ec2::optional account id:*`

[DeleteHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteHostedZone.html)  
Required Permissions \(API Action\): `route53:DeleteHostedZone`  
Resources: `*`

[AssociateVPCWithHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_AssociateVPCWithHostedZone.html)  
Required Permissions \(API Action\): `route53:AssociateVPCWithHostedZone`, `ec2:DescribeVpcs`  
Resources: `*`, `arn:aws:ec2::optional account id:*`

[CreateVPCAssociationAuthorization](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateVPCAssociationAuthorization.html)  
Required Permissions \(API Action\): `route53:CreateVPCAssociationAuthorization`  
Resources: `*`

[DeleteVPCAssociationAuthorization](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteVPCAssociationAuthorization.html)  
Required Permissions \(API Action\): `route53:DeleteVPCAssociationAuthorization`  
Resources: `*`

[DisassociateVPCFromHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DisassociateVPCFromHostedZone.html)  
Required Permissions \(API Action\): `route53:DisassociateVPCFromHostedZone`, `ec2:DescribeVpcs`  
Resources: `*`, `arn:aws:ec2::optional account id:*`

[GetHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHostedZone.html)  
Required Permissions \(API Action\): `route53:GetHostedZone`  
Resources: `*`

[GetHostedZoneCount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHostedZoneCount.html)  
Required Permissions \(API Action\): `route53:GetHostedZoneCount`  
Resources: `*`

[ListHostedZones](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListHostedZones.html)  
Required Permissions \(API Action\): `route53:ListHostedZones`  
Resources: `*`

[ListHostedZonesByName](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListHostedZonesByName.html)  
Required Permissions \(API Action\): `route53:ListHostedZonesByName`  
Resources: `*`

[UpdateHostedZoneComment](https://docs.aws.amazon.com/Route53/latest/APIReference/API_UpdateHostedZoneComment.html)  
Required Permissions \(API Action\): `route53:UpdateHostedZoneComment`  
Resources: `*`

## Required permissions for actions on reusable delegation sets<a name="required-permissions-reusable-delegation-sets"></a><a name="reusable-delegation-sets-table"></a>

[CreateReusableDelegationSet](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateReusableDelegationSet.html)  
Required Permissions \(API Action\): `route53:CreateReusableDelegationSet`  
Resources: `*`

[DeleteReusableDelegationSet](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteReusableDelegationSet.html)  
Required Permissions \(API Action\): `route53:DeleteReusableDelegationSet`  
Resources: `*`

[GetReusableDelegationSet](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetReusableDelegationSet.html)  
Required Permissions \(API Action\): `route53:GetReusableDelegationSet`  
Resources: `*`

[ListReusableDelegationSets](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListReusableDelegationSets.html)  
Required Permissions \(API Action\): `route53:ListReusableDelegationSets`  
Resources: `*`

## Required permissions for actions on records<a name="required-permissions-resource-record-sets"></a><a name="resource-record-sets-table"></a>

[ChangeResourceRecordSets](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ChangeResourceRecordSets.html)  
Required Permissions \(API Action\): `route53:ChangeResourceRecordSets`  
Resources: `arn:aws:route53:::hostedzone/hosted zone ID`

[GetChange](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetChange.html)  
Required Permissions \(API Action\): `route53:GetChange`  
Resources: `*`

[GetGeoLocation](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetGeoLocation.html)  
Required Permissions \(API Action\): None  
Resources: None  
Route 53 does not perform authorization for this API because it retrieves information that is already available to the public\.

[ListGeoLocations](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListGeoLocations.html)  
Required Permissions \(API Action\): None  
Resources: None  
Route 53 does not perform authorization for this API because it retrieves information that is already available to the public\.

[ListResourceRecordSets](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListResourceRecordSets.html)  
Required Permissions \(API Action\): `route53:ListResourceRecordSets`  
Resources: `arn:aws:route53:::hostedzone/hosted zone ID`

## Required permissions for actions on traffic policies<a name="required-permissions-traffic-policies"></a><a name="traffic-policies-table"></a>

[CreateTrafficPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateTrafficPolicy.html)  
Required Permissions \(API Action\): `route53:CreateTrafficPolicy`  
Resources: `*`

[CreateTrafficPolicyVersion](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateTrafficPolicyVersion.html)  
Required Permissions \(API Action\): `route53:CreateTrafficPolicyVersion`  
Resources: `*`

[DeleteTrafficPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteTrafficPolicy.html)  
Required Permissions \(API Action\): `route53:DeleteTrafficPolicy`  
Resources: `*`

[GetTrafficPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetTrafficPolicy.html)  
Required Permissions \(API Action\): `route53:GetTrafficPolicy`  
Resources: `*`

[ListTrafficPolicies](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTrafficPolicies.html)  
Required Permissions \(API Action\): `route53:ListTrafficPolicies`  
Resources: `*`

[ListTrafficPolicyVersions](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTrafficPolicyVersions.html)  
Required Permissions \(API Action\): `route53:ListTrafficPolicyVersions`  
Resources: `*`

[UpdateTrafficPolicyComment](https://docs.aws.amazon.com/Route53/latest/APIReference/API_UpdateTrafficPolicyComment.html)  
Required Permissions \(API Action\): `route53:UpdateTrafficPolicyComment`  
Resources: `*`

## Required permissions for actions on traffic policy instances<a name="required-permissions-traffic-policy-instances"></a><a name="traffic-policy-instances-table"></a>

[CreateTrafficPolicyInstance](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateTrafficPolicyInstance.html)  
Required Permissions \(API Action\): `route53:CreateTrafficPolicyInstance`  
Resources: `*`

[DeleteTrafficPolicyInstance](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteTrafficPolicyInstance.html)  
Required Permissions \(API Action\): `route53:DeleteTrafficPolicyInstance`  
Resources: `*`

[GetTrafficPolicyInstance](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetTrafficPolicyInstance.html)  
Required Permissions \(API Action\): `route53:GetTrafficPolicyInstance`  
Resources: `*`

[GetTrafficPolicyInstanceCount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetTrafficPolicyInstanceCount.html)  
Required Permissions \(API Action\): `route53:GetTrafficPolicyInstanceCount`  
Resources: `*`

[ListTrafficPolicyInstances](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTrafficPolicyInstances.html)  
Required Permissions \(API Action\): `route53:ListTrafficPolicyInstances`  
Resources: `*`

[ListTrafficPolicyInstancesByHostedZone](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTrafficPolicyInstancesByHostedZone.html)  
Required Permissions \(API Action\): `route53:ListTrafficPolicyInstancesByHostedZone`  
Resources: `*`

[ListTrafficPolicyInstancesByPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTrafficPolicyInstancesByPolicy.html)  
Required Permissions \(API Action\): `route53:ListTrafficPolicyInstancesByPolicy`  
Resources: `*`

[UpdateTrafficPolicyInstance](https://docs.aws.amazon.com/Route53/latest/APIReference/API_UpdateTrafficPolicyInstance.html)  
Required Permissions \(API Action\): `route53:UpdateTrafficPolicyInstance`  
Resources: `*`

## Required permissions for actions on health checks<a name="required-permissions-health-checks"></a><a name="health-checks-table"></a>

[CreateHealthCheck](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateHealthCheck.html)  
Required Permissions \(API Action\): `route53:CreateHealthCheck`  
Resources: `*`

[DeleteHealthCheck](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteHealthCheck.html)  
Required Permissions \(API Action\): `route53:DeleteHealthCheck`  
Resources: `*`, `arn:aws:route53:::healthcheck/health check ID`

[GetCheckerIpRanges](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetCheckerIpRanges.html)  
Required Permissions \(API Action\): None  
Resources: `*`  
Route 53 does not perform authorization for this API because it retrieves information that is already available to the public\.

[GetHealthCheck](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHealthCheck.html)  
Required Permissions \(API Action\): `route53:GetHealthCheck`  
Resources: `*`, `arn:aws:route53:::healthcheck/health check ID`

[GetHealthCheckCount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHealthCheckCount.html)  
Required Permissions \(API Action\): `route53:GetHealthCheckCount`  
Resources: `*`

[GetHealthCheckLastFailureReason](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHealthCheckLastFailureReason.html)  
Required Permissions \(API Action\): `route53:GetHealthCheckLastFailureReason`  
Resources: `*`, `arn:aws:route53:::healthcheck/health check ID`

[GetHealthCheckStatus](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHealthCheckStatus.html)  
Required Permissions \(API Action\): `route53:GetHealthCheckStatus`  
Resources: `*`, `arn:aws:route53:::healthcheck/health check ID`

[ListHealthChecks](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListHealthChecks.html)  
Required Permissions \(API Action\): `route53:ListHealthChecks`  
Resources: `*`

[UpdateHealthCheck](https://docs.aws.amazon.com/Route53/latest/APIReference/API_UpdateHealthCheck.html)  
Required Permissions \(API Action\): `route53:UpdateHealthCheck`  
Resources: `*`, `arn:aws:route53:::healthcheck/health check ID`

## Required permissions for actions on domain registrations<a name="required-permissions-domain-registrations"></a><a name="domain-registrations-table"></a>

[AcceptDomainTransferFromAnotherAwsAccount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_AcceptDomainTransferFromAnotherAwsAccount.html)  
Required Permissions \(API Action\): `route53domains:AcceptDomainTransferFromAnotherAwsAccount`  
Resources: `*`

[AddDnssec](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-configure-dnssec.html) \(console only\)  
Required Permissions \(API Action\): `route53domains:AddDnssec`  
Resources: `*`

[CancelDomainTransferToAnotherAwsAccount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_CancelDomainTransferToAnotherAwsAccount.html)  
Required Permissions \(API Action\): `route53domains:CancelDomainTransferToAnotherAwsAccount`  
Resources: `*`

[CheckDomainAvailability](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_CheckDomainAvailability.html)  
Required Permissions \(API Action\): `route53domains:CheckDomainAvailability`  
Resources: `*`

[CheckDomainTransferability](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_CheckDomainTransferability.html)  
Required Permissions \(API Action\): `route53domains:CheckDomainTransferability`  
Resources: `*`

[DeleteDomain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-delete.html) \(console only\)  
Required Permissions \(API Action\): `route53domains:DeleteDomain`  
Resources: `*`

[DisableDomainAutoRenew](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_DisableDomainAutoRenew.html)  
Required Permissions \(API Action\): `route53domains:ChangeAutoRenew`  
Resources: `*`

[DisableDomainTransferLock](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_DisableDomainTransferLock.html)  
Required Permissions \(API Action\): `route53domains:DisableDomainTransferLock`  
Resources: `*`

[EnableDomainAutoRenew](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_EnableDomainAutoRenew.html)  
Required Permissions \(API Action\): `route53domains:ChangeAutoRenew`  
Resources: `*`

[EnableDomainTransferLock](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_EnableDomainTransferLock.html)  
Required Permissions \(API Action\): `route53domains:EnableDomainTransferLock`  
Resources: `*`

[GetContactReachabilityStatus](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_GetContactReachabilityStatus.html)  
Required Permissions \(API Action\): `route53domains:ListDomains`  
Resources: `*`

[GetDomainDetail](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_GetDomainDetail.html)  
Required Permissions \(API Action\): `route53domains:GetDomainDetail`  
Resources: `*`

[GetDomainSuggestions](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_GetDomainSuggestions.html)  
Required Permissions \(API Action\): `route53domains:ListDomains`  
Resources: `*`

[GetOperationDetail](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_GetOperationDetail.html)  
Required Permissions \(API Action\): `route53domains:GetOperationDetail`  
Resources: `*`

[ListDnssec](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-configure-dnssec.html) \(console only\)  
Required Permissions \(API Action\): `route53domains:ListDnssec`  
Resources: `*`

[ListDomains](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_ListDomains.html)  
Required Permissions \(API Action\): `route53domains:ListDomains`  
Resources: `*`

[ListOperations](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_ListOperations.html)  
Required Permissions \(API Action\): `route53domains:ListOperations`  
Resources: `*`

[RegisterDomain](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_RegisterDomain.html)  
Required Permissions \(API Action\): `route53domains:RegisterDomain`  
Resources: `*`

[RejectDomainTransferFromAnotherAwsAccount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_RejectDomainTransferFromAnotherAwsAccount.html)  
Required Permissions \(API Action\): `route53domains:RejectDomainTransferFromAnotherAwsAccount`  
Resources: `*`

[RemoveDnssec](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-configure-dnssec.html) \(console only\)  
Required Permissions \(API Action\): `route53domains:RemoveDnssec`  
Resources: `*`

[RenewDomain](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_RenewDomain.html)  
Required Permissions \(API Action\): `route53domains:RegisterDomain`  
Resources: `*`

[ResendContactReachabilityEmail](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_ResendContactReachabilityEmail.html)  
Required Permissions \(API Action\): `route53domains:ListDomains`  
Resources: `*`

[RetrieveDomainAuthCode](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_RetrieveDomainAuthCode.html)  
Required Permissions \(API Action\): `route53domains:RetrieveDomainAuthCode`  
Resources: `*`

[TransferDomain](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_TransferDomain.html)  
Required Permissions \(API Action\): `route53domains:TransferDomain`  
Resources: `*`

[TransferDomainToAnotherAwsAccount](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_TransferDomainToAnotherAwsAccount.html)  
Required Permissions \(API Action\): `route53domains:TransferDomainToAnotherAwsAccount`  
Resources: `*`

[UpdateDomainContact](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_UpdateDomainContact.html)  
Required Permissions \(API Action\): `route53domains:UpdateDomainContact`  
Resources: `*`

[UpdateDomainContactPrivacy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_UpdateDomainContactPrivacy.html)  
Required Permissions \(API Action\): `route53domains:UpdateDomainContactPrivacy`  
Resources: `*`

[UpdateDomainNameservers](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_UpdateDomainNameservers.html)  
Required Permissions \(API Action\): `route53domains:UpdateDomainNameservers`  
Resources: `*`

[ViewBilling](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_ViewBilling.html)  
Required Permissions \(API Action\): `route53domains:ViewBilling`  
Resources: `*`

## Required permissions for Route 53 Resolver actions<a name="required-permissions-resolver"></a><a name="resolver-table"></a>

[AssociateResolverEndpointIpAddress](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_AssociateResolverEndpointIpAddress.html)  
Required Permissions \(API Action\): `route53resolver:AssociateResolverEndpointIpAddress`, `ec2:CreateNetworkInterfacePermission`, `ec2:DescribeAvailabilityZones`, `ec2:DescribeNetworkInterfaces`, `ec2:DescribeSubnets`   
Resources: `*`

[AssociateResolverQueryLogConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_AssociateResolverQueryLogConfig.html)  
Required Permissions \(API Action\): `route53resolver:AssociateResolverQueryLogConfig`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`, `logs:PutResourcePolicy`, `logs:UpdateLogDelivery`   
Resources: `*`

[AssociateResolverRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_AssociateResolverRule.html)  
Required Permissions \(API Action\): `route53resolver:AssociateResolverRule`, `ec2:DescribeVpcs`  
Resources: `*`

[CreateResolverEndpoint](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_CreateResolverEndpoint.html)  
Required Permissions \(API Action\): `route53resolver:CreateResolverEndpoint`, `ec2:DescribeSubnets`, `ec2:CreateNetworkInterface`, `ec2:DescribeNetworkInterfaces`, `ec2:CreateNetworkInterfacePermission`, `ec2:DescribeSecurityGroups`  
See also [Example 4: Allow creation of inbound and outbound Route 53 Resolver endpoints](access-control-managing-permissions.md#access-policy-example-create-resolver-endpoints)\.  
Resources: `*`

[CreateResolverQueryLogConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_CreateResolverQueryLogConfig.html)  
Required Permissions \(API Action\): `route53resolver:CreateResolverQueryLogConfig`, `ec2:DescribeVpcs`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:CreateLogDelivery`, `logs:DeleteLogDelivery`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`, `logs:UpdateLogDelivery`, `logs:PutResourcePolicy`, `iam:CreateServiceLinkedRole`   
Resources: `*`

[CreateResolverRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_CreateResolverRule.html)  
Required Permissions \(API Action\): `route53resolver:CreateResolverRule`  
Resources: `*`

[DeleteResolverEndpoint](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DeleteResolverEndpoint.html)  
Required Permissions \(API Action\): `route53resolver:DeleteResolverEndpoint`, `ec2:DeleteNetworkInterface`, `ec2:DescribeNetworkInterface`  
Resources: `*`

[DeleteResolverQueryLogConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DeleteResolverQueryLogConfig.html)  
Required Permissions \(API Action\): `route53resolver:DeleteResolverQueryLogConfig`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:DeleteLogDelivery` `logs:GetLogDelivery`, `logs:ListLogDeliveries`, `logs:UpdateLogDelivery`   
Resources: `*`

[DeleteResolverRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DeleteResolverRule.html)  
Required Permissions \(API Action\): `route53resolver:DeleteResolverRule`  
Resources: `*`

[DisassociateResolverEndpointIpAddress](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DisassociateResolverEndpointIpAddress.html)  
Required Permissions \(API Action\): `route53resolver:DisassociateResolverEndpointIpAddress`, `ec2:DeleteNetworkInterface`  
Resources: `*`

[DisassociateResolverQueryLogConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DisassociateResolverQueryLogConfig.html)  
Required Permissions \(API Action\): `route53resolver:DisassociateResolverQueryLogConfig`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`, `logs:PutResourcePolicy`, `logs:UpdateLogDelivery`   
Resources: `*`

[DisassociateResolverRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DisassociateResolverRule.html)  
Required Permissions \(API Action\): `route53resolver:DisassociateResolverRule`  
Resources: `*`

[GetResolverEndpoint](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverEndpoint.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverEndpoint`  
Resources: `*`

[GetResolverQueryLogConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverQueryLogConfig.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverQueryLogConfig`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`   
Resources: `*`

[GetResolverQueryLogConfigAssociation](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverQueryLogConfigAssociation.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverQueryLogConfigAssociation`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`   
Resources: `*`

[GetResolverQueryLogConfigPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverQueryLogConfigPolicy.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverQueryLogConfigPolicy`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`   
Resources: `*`

[GetResolverRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverRule.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverRule`  
Resources: `*`

[GetResolverRuleAssociation](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverRuleAssociation.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverRuleAssociation`, `ec2:DescribeVpcs`  
Resources: `*`

[GetResolverRulePolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetResolverRulePolicy.html)  
Required Permissions \(API Action\): `route53resolver:GetResolverRulePolicy`  
Resources: `*`

[ListResolverEndpointIpAddresses](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListResolverEndpointIpAddresses.html)  
Required Permissions \(API Action\): `route53resolver:ListResolverEndpointIpAddresses`  
Resources: `*`

[ListResolverEndpoints](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListResolverEndpoints.html)  
Required Permissions \(API Action\): `route53resolver:ListResolverEndpoints`  
Resources: `*`

[ListResolverQueryLogConfigAssociations](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListResolverQueryLogConfigAssociations.html)  
Required Permissions \(API Action\): `route53resolver:ListResolverQueryLogConfigAssociations`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`   
Resources: `*`

[ListResolverQueryLogConfigs](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListResolverQueryLogConfigs.html)  
Required Permissions \(API Action\): `route53resolver:ListResolverQueryLogConfigs`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`   
Resources: `*`

[ListResolverRuleAssociations](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListResolverRuleAssociations.html)  
Required Permissions \(API Action\): `route53resolver:ListResolverRuleAssociations`, `ec2:DescribeVpcs`  
Resources: `*`

[ListResolverRules](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListResolverRules.html)  
Required Permissions \(API Action\): `route53resolver:ListResolverRules`  
Resources: `*`

[ListTagsForResource](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListTagsForResource.html)  
Required Permissions \(API Action\): `route53resolver:ListTagsForResource`  
Resources: `arn:aws:route53resolver:::resolver-endpoint/*`, `arn:aws:route53resolver:::resolver-rule/`

[PutResolverQueryLogConfigPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_PutResolverQueryLogConfigPolicy.html)  
Required Permissions \(API Action\): `route53resolver:PutResolverQueryLogConfigPolicy`, `logs:DescribeResourcePolicies`, `logs:DescribeLogGroups`, `logs:GetLogDelivery`, `logs:ListLogDeliveries`, `logs:PutResourcePolicy`, `logs:UpdateLogDelivery`   
Resources: `*`

[PutResolverRulePolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_PutResolverRulePolicy.html)  
Required Permissions \(API Action\): `route53resolver:PutResolverRulePolicy`  
Resources: `*`

[TagResource](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_TagResource.html)  
Required Permissions \(API Action\): `route53resolver:TagResource`  
Resources: `arn:aws:route53resolver:::resolver-endpoint/*`, `arn:aws:route53resolver:::resolver-rule/*`

[UntagResource](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UntagResource.html)  
Required Permissions \(API Action\): `route53resolver:UntagResource`  
Resources: `arn:aws:route53resolver:::resolver-endpoint/*`, `arn:aws:route53resolver:::resolver-rule/*`

[UpdateResolverEndpoint](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UpdateResolverEndpoint.html)  
Required Permissions \(API Action\): `route53resolver:UpdateResolverEndpoint`  
Resources: `*`

[UpdateResolverRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UpdateResolverRule.html)  
Required Permissions \(API Action\): `route53resolver:UpdateResolverRule`  
Resources: `*`

## Required permissions for Route 53 Resolver DNS Firewall actions<a name="required-permissions-resolver-dns-firewall"></a><a name="resolver-dns-firewall-table"></a>

[AssociateFirewallRuleGroup](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_AssociateFirewallRuleGroup.html)  
Required Permissions \(API Action\): `route53resolver:AssociateFirewallRuleGroup`, `ec2:DescribeVpcs`  
Optional Permissions: `route53resolver:TagResource` \(Required if you provide a tagging parameter\)   
Resources: `*`

[CreateFirewallDomainList](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_CreateFirewallDomainList.html)  
Required Permissions \(API Action\): `route53resolver:CreateFirewallDomainList`  
Optional Permissions: `route53resolver:TagResource` \(Required if you provide a tagging parameter\)   
Resources: `*`

[CreateFirewallRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_CreateFirewallRule.html)  
Required Permissions \(API Action\): `route53resolver:CreateFirewallRule`  
Resources: `*`

[CreateFirewallRuleGroup](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_CreateFirewallRuleGroup.html)  
Required Permissions \(API Action\): `route53resolver:CreateFirewallRuleGroup`  
Optional Permissions: `route53resolver:TagResource` \(Required if you provide a tagging parameter\)   
Resources: `*`

[DeleteFirewallDomainList](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DeleteFirewallDomainList.html)  
Required Permissions \(API Action\): `route53resolver:DeleteFirewallDomainList`  
Resources: `*`

[DeleteFirewallRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DeleteFirewallRule.html)  
Required Permissions \(API Action\): `route53resolver:DeleteFirewallRule`  
Resources: `*`

[DeleteFirewallRuleGroup](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DeleteFirewallRuleGroup.html)  
Required Permissions \(API Action\): `route53resolver:DeleteFirewallRuleGroup`  
Resources: `*`

[DisassociateFirewallRuleGroup](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_DisassociateFirewallRuleGroup.html)  
Required Permissions \(API Action\): `route53resolver:DisassociateFirewallRuleGroup`  
Resources: `*`

[GetFirewallConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetFirewallConfig.html)  
Required Permissions \(API Action\): `route53resolver:GetFirewallConfig` `ec2:DescribeVpcs`  
Resources: `*`

[GetFirewallDomainList](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetFirewallDomainList.html)  
Required Permissions \(API Action\): `route53resolver:GetFirewallDomainList`  
Resources: `*`

[GetFirewallRuleGroup](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetFirewallRuleGroup.html)  
Required Permissions \(API Action\): `route53resolver:GetFirewallRuleGroup`  
Resources: `*`

[GetFirewallRuleGroupAssociation](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetFirewallRuleGroupAssociation.html)  
Required Permissions \(API Action\): `route53resolver:GetFirewallRuleGroupAssociation`  
Resources: `*`

[GetFirewallRuleGroupPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_GetFirewallRuleGroupPolicy.html)  
Required Permissions \(API Action\): `route53resolver:GetFirewallRuleGroupPolicy`  
Resources: `*`

[ImportFirewallDomains](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ImportFirewallDomains.html)  
Required Permissions \(API Action\): `route53resolver:ImportFirewallRuleDomains`  
Resources: `*`

[ListFirewallConfigs](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListFirewallConfigs.html)  
Required Permissions \(API Action\): `route53resolver:ListFirewallConfigs` `ec2:DescribeVpcs`  
Resources: `*`

[ListFirewallDomainLists](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListFirewallDomainLists.html)  
Required Permissions \(API Action\): `route53resolver:ListFirewallDomainLists`  
Resources: `*`

[ListFirewallDomains](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListFirewallDomains.html)  
Required Permissions \(API Action\): `route53resolver:ListFirewallDomains`  
Resources: `*`

[ListFirewallRuleGroupAssociations](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListFirewallRuleGroupAssociations.html)  
Required Permissions \(API Action\): `route53resolver:ListFirewallRuleGroupAssociations`  
Resources: `*`

[ListFirewallRuleGroups](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListFirewallRuleGroups.html)  
Required Permissions \(API Action\): `route53resolver:ListFirewallRuleGroups`  
Resources: `*`

[ListFirewallRules](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_ListFirewallRules.html)  
Required Permissions \(API Action\): `route53resolver:ListFirewallRules`  
Resources: `*`

[PutFirewallRuleGroupPolicy](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_PutFirewallRuleGroupPolicy.html)  
Required Permissions \(API Action\): `route53resolver:PutFirewallRuleGroupPolicy`  
Resources: `*`

[UpdateFirewallConfig](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UpdateFirewallConfig.html)  
Required Permissions \(API Action\): `route53resolver:UpdateFirewallConfig` `ec2:DescribeVpcs`  
Resources: `*`

[UpdateFirewallDomains](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UpdateFirewallDomains.html)  
Required Permissions \(API Action\): `route53resolver:UpdateFirewallDomains`  
Resources: `*`

[UpdateFirewallRule](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UpdateFirewallRule.html)  
Required Permissions \(API Action\): `route53resolver:UpdateFirewallRule`  
Resources: `*`

[UpdateFirewallRuleGroupAssociation](https://docs.aws.amazon.com/Route53/latest/APIReference/API_route53resolver_UpdateFirewallRuleGroupAssociation.html)  
Required Permissions \(API Action\): `route53resolver:UpdateFirewallRuleGroupAssociation`  
Resources: `*`

## Required permissions for actions to get limits for accounts, hosted zones, and reusable delegation sets<a name="required-permissions-get-limits"></a><a name="tags-hosted-zones-table"></a>

[GetAccountLimit](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetAccountLimit.html)  
Required Permissions \(API Action\): `route53:GetAccountLimit`  
Resources: `*`

[GetHostedZoneLimit](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetHostedZoneLimit.html)  
Required Permissions \(API Action\): `route53:GetHostedZoneLimit`  
Resources: `*`

[GetReusableDelegationSetLimit](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetReusableDelegationSetLimit.html)  
Required Permissions \(API Action\): `route53:GetReusableDelegationSetLimit`  
Resources: `*`

## Required permissions for actions on tags for hosted zones and health checks<a name="required-permissions-tags-hosted-zones"></a><a name="tags-hosted-zones-table"></a>

[ChangeTagsForResource](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ChangeTagsForResource.html)  
Required Permissions \(API Action\): `route53:ChangeTagsForResource`  
Resources:  
+ `arn:aws:route53:::healthcheck/*`
+ `arn:aws:route53:::hostedzone/*`

[ListTagsForResource](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTagsForResource.html)  
Required Permissions \(API Action\): `route53:ListTagsForResource`  
Resources:  
+ `arn:aws:route53:::healthcheck/*`
+ `arn:aws:route53:::hostedzone/*`

[ListTagsForResources](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ListTagsForResources.html)  
Required Permissions \(API Action\): `route53:ListTagsForResources`  
Resources:  
+ `arn:aws:route53:::healthcheck/*`
+ `arn:aws:route53:::hostedzone/*`

## Required permissions for actions on tags for domains<a name="required-permissions-tags-domains"></a><a name="tags-domains-table"></a>

[DeleteTagsForDomain](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_DeleteTagsForDomain.html)  
Required Permissions \(API Action\): `route53domains:DeleteTagsForDomain`  
Resources: `*`

[ListTagsForDomain](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_ListTagsForDomain.html)  
Required Permissions \(API Action\): `route53domains:ListTagsForDomain`  
Resources: `*`

[UpdateTagsForDomain](https://docs.aws.amazon.com/Route53/latest/APIReference/API_domains_UpdateTagsForDomain.html)  
Required Permissions \(API Action\): `route53domains:UpdateTagsForDomain`  
Resources: `*`

## Required permissions for DNSSEC actions<a name="required-permissions-dnssec-signing"></a><a name="tags-domains-table"></a>

[GetDNSSEC](https://docs.aws.amazon.com/Route53/latest/APIReference/API_GetDNSSEC.html)  
Required Permissions \(API Action\): `route53domains:DeleteTagsForDomain`  
Resources: `*`

[CreateKeySigningKey](https://docs.aws.amazon.com/Route53/latest/APIReference/API_CreateKeySigningKey.html)  
Required Permissions \(API Action\): `route53:CreateKeySigningKey`, `kms:DescribeKey`, `kms:GetPublicKey`, `kms:Sign`  
Resources: `*`

[DeleteKeySigningKey](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeleteKeySigningKey.html)  
Required Permissions \(API Action\): `route53:DeleteKeySigningKey`, `kms:DescribeKey`, `kms:GetPublicKey`, `kms:Sign`  
Resources: `*`

[ActivateKeySigningKey](https://docs.aws.amazon.com/Route53/latest/APIReference/API_ActivateKeySigningKey.html)  
Required Permissions \(API Action\): `route53:ActivateKeySigningKey`, `kms:DescribeKey`, `kms:GetPublicKey`, `kms:Sign`  
Resources: `*`

[DeactivateKeySigningKey](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DeactivateKeySigningKey.html)  
Required Permissions \(API Action\): `route53:DeactivateKeySigningKey`, `kms:DescribeKey`, `kms:GetPublicKey`, `kms:Sign`  
Resources: `*`

[EnableHostedZoneDNSSEC](https://docs.aws.amazon.com/Route53/latest/APIReference/API_EnableHostedZoneDNSSEC.html)  
Required Permissions \(API Action\): `route53:EnableHostedZoneDNSSEC`, `kms:DescribeKey`, `kms:GetPublicKey`, `kms:Sign`  
Resources: `*`

[DisableHostedZoneDNSSEC](https://docs.aws.amazon.com/Route53/latest/APIReference/API_DisableHostedZoneDNSSEC.html)  
Required Permissions \(API Action\): `route53:DisableHostedZoneDNSSEC`, `kms:DescribeKey`, `kms:GetPublicKey`, `kms:Sign`  
Resources: `*`