# Prerequisites<a name="appinsights-prereqs"></a>

You must complete the following prerequisites to configure an application with CloudWatch Application Insights:
+ **AWS Systems Manager enablement: **You must install Systems Manager Agent \(SSM Agent\), and your instances must be SSM enabled\. For steps on how to install the SSM Agent, see [Setting Up AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-setting-up.html)\.
+ **EC2 instance role: **You must attach the `AmazonSSMManagedInstanceCore` role to enable Systems Manager \(see [Using Identity\-based Policies \(IAM Policies\) for AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/auth-and-access-control-iam-identity-based-access-control.html)\) and the `CloudWatchAgentServerPolicy` to enable instance metrics and logs to be emitted through CloudWatch\. See [Create IAM Roles and Users for Use With CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create-iam-roles-for-cloudwatch-agent.html) for more information\.
+ **AWS Resource Groups: **To onboard your \.NET and SQL Server applications to CloudWatch Application Insights for \.NET and SQL Server, you must create a resource group that includes all associated AWS resources used by your application stack\. This includes application load balancers, EC2 instances running IIS and web front‐end, \.NET worker tiers, and your SQL Server database\. CloudWatch Application Insights for \.NET and SQL Server automatically includes Auto Scaling groups using the same tags or CloudFormation stacks as your Resource Group, because Auto Scaling groups are not currently supported by Resource Groups\. For more information, see [Getting Started with AWS Resource Groups](https://docs.aws.amazon.com/ARG/latest/userguide/gettingstarted.html)\.
+ **IAM permissions: **For non‐Admin users, you must create an AWS Identity and Access Management \(IAM\) Policy and attach it to your user identity\. See [IAM policy](appinsights-iam.md)\.
+ **Service\-linked role: **CloudWatch Application Insights for \.NET and SQL Server uses AWS Identity and Access Management \(IAM\) service‐linked roles\. You don’t need to manually create a service‐linked role\. Instead, it is created for you when you create your first CloudWatch Application Insights for \.NET and SQL Server application in the AWS Management Console\. For more information, see [Using Service\-Linked Roles for CloudWatch Application Insights for \.NET and SQL Server](CHAP_using-service-linked-roles-appinsights.md)\.
+ **Performance Counter metrics support for EC2 Windows instances:** To monitor Performance Counter metrics on your EC2 Windows instances, Performance Counters must be installed on the instances\. For Performance Counter metrics and corresponding Performance Counter set names, see [Performance Counter metrics](appinsights-logs-and-metrics.md#application-insights-performance-counter)\. For more information about Performance Counters, see [Performance Counters](https://docs.microsoft.com/en-us/windows/win32/perfctrs/performance-counters-portal)\.