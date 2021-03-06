# Create a Target Group<a name="create-target-group"></a>

You register your targets with a target group\. By default, the load balancer sends requests to registered targets using the port and protocol that you specified for the target group\. You can override this port when you register each target with the target group\.

After you create a target group, you can add tags\.

To route traffic to the targets in a target group, specify the target group in an action when you create a listener or create a rule for your listener\. For more information, see [Listener Rules](load-balancer-listeners.md#listener-rules)\.

You can add or remove targets from your target group at any time\. For more information, see [Register Targets with Your Target Group](target-group-register-targets.md)\. You can also modify the health check settings for your target group\. For more information, see [Modify the Health Check Settings of a Target Group](target-group-health-checks.md#modify-health-check-settings)\.

**To create a target group using the console**

1. Open the Amazon EC2 console at [https://console\.aws\.amazon\.com/ec2/](https://console.aws.amazon.com/ec2/)\.

1. On the navigation pane, under **LOAD BALANCING**, choose **Target Groups**\.

1. Choose **Create target group**\.

1. For **Target group name**, type a name for the target group\. This name must be unique per region per account, can have a maximum of 32 characters, must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen\.

1. For **Target type**, select **Instance** to register targets by instance ID, **IP** to register IP addresses, and **Lambda function** to register a Lambda function\.

1. If the target type is **Instance** or **IP**, do the following:

   1. \(Optional\) For **Protocol** and **Port**, modify the default values as needed\.

   1. For **VPC**, select a virtual private cloud \(VPC\)\.  
![\[The Create target group dialog box if the target type is Instance or IP.\]](http://docs.aws.amazon.com/elasticloadbalancing/latest/application/images/create_target_group.png)

1. If the target type is **Lambda function**, do the following:

   1. For **Lambda function**, do one of the following:
      + Select the Lambda function
      + Create a new Lambda function and select it
      + Register the Lambda function after you create the target group

   1. \(Optional\) To enable health checks, choose **Health check**, **Enable**\.  
![\[The Create target group dialog box if the target type is Lambda.\]](http://docs.aws.amazon.com/elasticloadbalancing/latest/application/images/create_target_group_lambda.png)

1. \(Optional\) For **Health check settings** and **Advanced health check settings**, modify the default settings as needed\.

1. Choose **Create**\.

1. \(Optional\) Add one or more tags as follows:

   1. Select the newly created target group\.

   1. On the **Tags** tab, choose **Add/Edit Tags**\.

   1. On the **Add/Edit Tags** page, for each tag you add, choose **Create Tag** and then specify the tag key and tag value\. When you have finished adding tags, choose **Save**\.

1. \(Optional\) To add targets to the target group, see [Register Targets with Your Target Group](target-group-register-targets.md)\.

1. \(Optional\) You can specify the target group in a listener rule\. For more information, see [Listener Rules](listener-update-rules.md)\.

**To create a target group using the AWS CLI**  
Use the [create\-target\-group](https://docs.aws.amazon.com/cli/latest/reference/elbv2/create-target-group.html) command to create the target group, the [add\-tags](https://docs.aws.amazon.com/cli/latest/reference/elbv2/add-tags.html) command to tag your target group, and the [register\-targets](https://docs.aws.amazon.com/cli/latest/reference/elbv2/register-targets.html) command to add targets\.