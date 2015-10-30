---
permalink: /NIST-800-53/AC-2/
title: AC-2 - Account Management
parent: NIST-800-53 Documentation
---

## Amazon Elastic Block Store
a. - Elastic Block Storage access is managed through the use of IAM Roles which grant IAM permissions to create, access, and manage block level storage using the following interfaces AWS Management Console and the AWS CLI.
 
 g. - 18F has implemented AWS CloudWatch for its system account monitoring. It allows 18F to monitor AWS resources in near real-time, including Amazon EC2 instances, Amazon EBS volumes, Elastic Load Balancers, and Amazon RDS DB instances. Metrics such as CPU utilization, latency, and request counts are provided automatically for these AWS resources. It allows 18F to supply logs or custom application and system metrics, such as memory usage, transaction volumes, or error rates.
 
 
### References

* [Amazon Elastic Block Store](https://aws.amazon.com/ebs/)

--------

## Amazon Elastic Compute Cloud
a. - Access to Amazon EC2 Linux instances are managed by the use of EC2 key pairs and using SSH to access the local instance on the individual Linux, or appliance instance. Account types include individual user and system/application user accounts. Shared or group accounts are not permitted outside of default accounts such as local Administrators or root. There are no guest/anonymous or temporary user accounts.
- Operating System user groups are documented in section 9.1 Types of Users.
- Initial Linux local root access is provided to AWS administrator account users only if they provide the key pair assigned to the Linux EC2 instance and login using SSH.
 
 f. - Local system user account establishment, activation, modification, disablement or removal requires approval by the managing 18F project lead and Cloud Foundry Information System Technical Point of Contact (Operating Environment).
 
 g. - 18F has implemented AWS CloudWatch for basic monitoring of Amazon EC2 instances. Basic Monitoring for Amazon EC2 instances: Seven pre-selected metrics at five-minute frequency and three status check metrics at one-minute frequency.
- 18F has implemented Detailed Monitoring for Amazon EC2 instances: All metrics available to Basic Monitoring at one-minute frequency. Instances with Detailed Monitoring enabled allow data aggregation by Amazon EC2 AMI ID and instance type.
- 18F has implemented the use of Auto Scaling and Elastic Load Balancing where Amazon CloudWatch provides Amazon EC2 instance metrics aggregated by Auto Scaling groups and Elastic Load Balancers.
- Monitoring data is retained for two weeks, even if AWS resources have been terminated. This enables 18F to quickly look back at the metrics preceding an event of interest.
- Metrics are accessed in either the Amazon EC2 tab or the Amazon CloudWatch tab of the AWS Management Console, or by using the Amazon CloudWatch API.
 
 h. - Local system user accounts will be deactivated immediately on receipt of notification of an email from the managing 18F project lead or at a future date as directed.
- User accounts will be monitored monthly and accounts will be disabled after 90 days of inactivity.
 
 i. - System access to local EC2 instance accounts is provided only to those with an established need to manage servers in the Cloud Foundry environment. User group membership is restricted to the least privilege necessary for the user to accomplish their assigned duties
 
 j. - User accounts will be monitored monthly and accounts will be disabled after 90 days of inactivity.
- Linux accounts will be monitored via scripts which query the last logon date/time of each user account and provide the results in the form of a CSV file which an authorized administrator will use for the basis of disablement.
- Application accounts will be monitored monthly and accounts will be disabled after 90 days of inactivity; this will be a manual review process, but the disablement will be automatic.
 
 
### References

* [Amazon Elastic Compute Cloud](https://aws.amazon.com/ec2/)

--------

## Identity and Access Management
a. - AWS accounts are managed through AWS Identity and Access Management (IAM). Only users with a need to operate the AWS management console are provided individual AWS user accounts. The following types are used
  - User – Individual IAM accounts
  - System – system and application account not used for interactive access
  - There are no guest/anonymous, groups, or temporary user accounts in 18F’s AWS account.
- 18F users must sign in to the account's sign in URL by using their IAM user name and password. This sign in URL is located in the Dashboard of the IAM console and must be communicated by the 18F AWS account's system administrator to the IAM user.
- To allow an IAM user to access resources and perform tasks, 18F creates IAM policies that grant IAM users permission to use the specific resources and API actions they'll need, then attach the policy to the IAM user or the group the IAM user belongs to. When you attach a policy to a user or group of users, it allows or denies the users permission to perform the specified tasks on the specified resources.
- AWS user accounts and roles are documented in section 9.1 Types of Users.
- AWS accounts are managed through AWS Identity and Access Management (IAM).
 
 b. - AWS user accounts are issued only to those with an established need to manage the AWS environment based on job function.
- Linux and/or local system user accounts are issued only to those with an established need to manage servers in the 18F AWS environment. User group membership is restricted to the least privilege necessary for the user to accomplish his or her assigned duties.
- 18F and GSA identify authorized users of the information system and specify access rights/privileges. 18F grants access to the information system based on:
  - (i) a valid need-to-know/need-to-share that is determined by assigned official duties and satisfying all personnel security criteria;
  - (ii) Intended system usage. 18F and GSA require proper identification for requests to establish information system accounts and approves all such requests; and
  - (iii) Organizational or mission/business function attributes.
 
 c. - Conditions for groups and roles membership in AWS groups are based on an established need to manage the AWS environment.  The user must meet the following the conditions on order for the system owner to approve membership request
- The user’s assigned role is required to access a particular group
- The user has the requirements and understanding to assume permissions associated with the group
- The user has completed the security role-based training
- The user complies with any other group-specific conditions created by the system owner
 
 d. - AWS user account creation requires approval by the managing 18F project lead and Cloud Foundry Information System Technical Point of Contact (Operating Environment). Prior to account creation users must have at least begun the GSA background investigative process.
 
 e. - AWS user account creation requires approval by the managing 18F project lead and Cloud Foundry Information System Technical Point of Contact (Operating Environment). Prior to account creation users must have at least begun the GSA background investigative process and basic security training.
 
 k. - 18F does not allow shared/group account credentials within the AWS environment. All users have individual accounts to access the AWS environment. 18F has created specific policies that allow individual users to assume a role within the AWS environment listed in Table 9-1. AWS User Roles, Groups and Privileges.
 
 
### References

* [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/)

### Governors

* [Roles Used by 18F](Find artifact)

* [Access Control Policy Section 3](Find artifact)

* [Account Management Flow](Find artifact)

--------

## S3
a. All Amazon S3 resources including buckets, objects, and related sub-resources (for example, lifecycle configuration and website configuration) are private, only the resource owner, an AWS account that created it, can access the resource through IAM policies granted to it. 
 
### References

* [Amazon S3](https://aws.amazon.com/s3/)

--------

## Application Security Groups
a. - Cloud Foundry uses Application security groups (ASGs) to act as virtual firewalls to control outbound traffic from the applications in the deployment. A security group consists of a list of network egress access rules.
- An administrator can assign one or more security groups to a Cloud Foundry deployment or to a specific space in an org within a deployment.
- Cloud Foundry user, organization, and application roles and security groups are documented in section 9.3 Types of Users. 
 
 
### References

* [Application Security Groups](http://docs.cloudfoundry.org/adminguide/app-sec-groups.html)

--------

## Loggregator
g. - 18F uses Steno for Cloud Foundry account logging. Steno is a shared logging service between the DEA, Cloud Controller and Cloud Foundry components that share a common interface for configuring logs. 
- Loggregator also referred to as Doppler in newer versions of cf, is the Cloud Foundry component responsible for logging, and provides a stream of log output from 18F applications and from Cloud Foundry system components that interact with applications during updates and execution. Loggregator allows users to:
  - Tail their application logs.
  - Dump a recent set of application logs (where recent is a configurable number of log packets).
  - Continually drain their application logs to 3rd party log archive and analysis services (i.e Splunk, Syslog, Alien Vault USM).
  - (Operators and administrators only) Access the firehose, which includes the combined stream of logs from all apps, plus metrics data from CF components
- Syslog and Syslog_aggregator are used for system logging and provide a mechanism to forward system logs via syslog to a syslog server.
- /healthz and /varz are HTTP endpoints provided by Cloud Foundry components used for system monitoring. The endpoints can be polled to obtain information on a job’s health and state. 
  - /healthz is a basic check that returns an ‘ok’ message if the job’s running happily.
  - /varz provides more detailed information about the running job. For example, polling /varz on the uaa server returns data about java memory usage (amongst other things).
- The Collector is used for monitoring and metrics by collecting data from the /health and /var endpoints. It dynamically learns about Cloud Foundry components and polls them for monitoring data and provides options to send monitoring data to AWS CloudWatch, Datadog, graphite and TSDB.
- New components have been added to the most recent version of Cloud Foundry 
  - CF components emit metrics (e.g. the router emits HTTP metrics, such as the time taken to service a request).
  - These metrics are sent to agents running on the VMs called ‘metron’.
  - The metron agents forward these metrics, along with application logs, to ‘doppler’ servers.
  - The doppler servers collect and buffer the data.
  - The loggregator traffic controllers expose a new websocket endpoint ‘/firehose’.
  - When you connect to /firehose, a connection is opened up to all doppler servers.
  - All logs and metrics for all apps and components are then streamed down the connection.
 
 
### References

* [Loggregator code](https://github.com/cloudfoundry/loggregator)

* [Cloud Foundry Logging](https://docs.cloudfoundry.org/running/managing-cf/logging.html)

### Governors

* [Loggregator Diagram](https://raw.githubusercontent.com/cloudfoundry/loggregator/develop/docs/loggregator.png)

--------

## User Account and Authentication (UAA) Server
a. - Cloud Foundry user and role accounts are managed and maintained through the UAA Command Line Interface (UAAC). Cloud Foundry uses role-based access control with each role granting permissions in either an organization or an application space.
- 18F uses Cloud Foundry’s user accounts for individuals within the context of a Cloud Foundry. A user can have different roles in different spaces within an org, governing what level and type of access they have within that space. The combination of these roles defines the user’s overall permissions in the org and within specific spaces in that org.  A list of standard cloud foundry user account types can be found in Table 9-2. Cloud Foundry User Roles and Privileges.
- Cloud Foundry uses Application security groups (ASGs) to act as virtual firewalls to control outbound traffic from the applications in the deployment. A security group consists of a list of network egress access rules.
- An administrator can assign one or more security groups to a Cloud Foundry deployment or to a specific space in an org within a deployment.
- Cloud Foundry user, organization, and application roles and security groups are documented in section 9.3 Types of Users. 
 
 k. - The Cloud Foundry platform utilizes role based access controls (RBAC) for group membership within the platform and does not issue shared/group account credentials. 
- 18F adds and removes individual users from defined user roles listed in Table 9-2. Cloud Foundry User Roles and Privileges.
 
 
### References

* [User Account and Authentication (UAA) Server](http://docs.pivotal.io/pivotalcf/concepts/architecture/uaa.html)

* [Creating and Managing Users with the UAA CLI (UAAC)](http://docs.pivotal.io/pivotalcf/adminguide/uaa-user-management.html)

* [UAA Roles](https://cf-p1-docs-prod.cfapps.io/pivotalcf/concepts/roles.html)

* [Cloud Foundry Org Access](https://github.com/cloudfoundry/cloud_controller_ng/blob/master/spec/unit/access/organization_access_spec.rb)

* [Cloud Foundry Space Access](https://github.com/cloudfoundry/cloud_controller_ng/blob/master/spec/unit/access/space_access_spec.rb)

### Governors

* [Access Control Policy Section 3](Find artifact)

* [Acccount Managment Flow](Find artifact)

--------