# Multi-region traffic management with AWS Global Accelerator

## Overview

This workshop will introduce you to the core concepts of AWS Global Accelerator, a service that improves the availability and performance of your applications with local or global users. It provides static IP addresses that act as a fixed entry point to your application endpoints in a single or multiple AWS Regions, such as your Application Load Balancers, Network Load Balancers or Amazon EC2 instances. AWS Global Accelerator uses the AWS global network to optimize the path from your users to your applications, improving the performance of your traffic by as much as 60%.

In this workshop, we will use four clients in different regions to show how AWS Global Accelerator routes requests based on users locations and the Accelerator settings (traffic dials, endpoint weights, failover, etc.). To test a website performance, it's recommended to use real clients, we will use some commands to see the difference between accessing our application via the ALBs directly vs accessing it via AWS Global Accelerator.

### Requirements

* AWS account - if you're doing this workshop as a part of an AWS event, you will be provided an account through a platform called Event Engine. The workshop administrator will provide instructions. If the event specifies you'll need your own account or if you're doing this workshop on your own, it's easy and free to [create an account](https://aws.amazon.com/) if you do not have one already.
* If using your own AWS account, create and use an IAM account with elevated privileges. Easiest option is to create an IAM user with admin privileges.

### What you'll do

The labs in the workshop are designed to be completed in sequence, and the full set of instructions are documented in each lab. Read and follow the instructions to complete each of the labs. Don't worry if you get stuck, we provide hints along the way.

* **[Lab 0: Deploy the CloudFormation stack](lab-0-init)**
* **[Lab 1: Create your first Accelerator with AWS Global Accelerator](lab-1-create-aws-global-accelerator)**
* **[Lab 2: Implement Intelligent Traffic Distribution](lab-2-traffic-distribution)**
* **[Lab 3: Implement Fine-grained traffic control](lab-3-fine-grained-control)**
* **[Lab 4: Implement Client Affinity](lab-4-client-affinity)**
* **[Lab 5: Implement Failover](lab-5-observability)**
* **[Lab 6: Implement Origin Cloaking](lab-6-origin-cloaking)**
* **[Lab 7: AWS Global Accelerator Performance](lab-7-aga-performance)**
* **[Bonus Lab: Enable flow logs and monitor with CloudWatch metrics](bonus-lab)**
* **[Workshop Cleanup](clean-up)**

### Workshop Cleanup

If you're attending an AWS event and are provided an account to use, you can ignore this section because we'll destroy the account once the workshop concludes. Feel free to proceed to [Lab-0 to get started](lab-0-init).

**If you are using your own account**, it is **VERY** important you clean up resources created during the workshop. Follow these steps to delete the main workshop CloudFormation stack once you're done going through the workshop:

1. Navigate to the [CloudFormation dashboard](https://console.aws.amazon.com/cloudformation/home#/stacks) and click on your workshop stack name to load stack details
2. Click **Delete** to delete the stack

There are helper Lambda functions that should clean things up when you delete the main stack. However, if there's a stack deletion failure due to a race condition, follow these steps:

1. In the CloudFormation dashboard, click on the **Events** section, and review the event stream to see what failed to delete
2. Manually delete those resources by visiting the respective service's dashboard in the management console
3. Once you've manually deleted the resources, try to delete the main workshop CloudFormation stack again. Repeat steps 1-3 if you still see deletion failures

* * *

## Let's Begin!

[Go to Lab-0 to set up your environment](lab-0-init)

## Participation

We encourage participation; if you find anything, please submit an [issue](https://github.com/aws-samples/aws-global-accelerator-workshop/issues). However, if you want to help raise the bar, submit a [PR](https://github.com/aws-samples/aws-global-accelerator-workshop/pulls)!
