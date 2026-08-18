# Attack-Proof Web Server with Automated Backups

This project demonstrates how core AWS services can be combined to deploy and manage a PHP-based web server that can handle changing traffic, continuously back up important data, monitor infrastructure activity, and provide multiple recovery options.

## Project Overview

The application runs on *Amazon EC2 with PHP and Apache* and uses *Amazon RDS MySQL* as its database layer. An *Application Load Balancer* distributes incoming traffic across EC2 instances managed by an *Auto Scaling Group*.

To strengthen reliability and recovery, website files and logs are automatically synchronized to *Amazon S3, while **EBS snapshots* provide an additional backup mechanism. *CloudWatch and SNS* are used for monitoring and notifications, and *SSM Session Manager* provides secure administrative access without relying on direct SSH access.

## Objectives

* Build a reliable AWS-based web server infrastructure
* Automate website and log backups to Amazon S3
* Handle increased traffic using Load Balancing and Auto Scaling
* Monitor infrastructure health and scaling events
* Configure automated monitoring alerts
* Implement multiple backup and recovery mechanisms
* Reduce dependency on direct SSH access using SSM Session Manager

## AWS Services Used

*EC2 | RDS | S3 | Application Load Balancer | Auto Scaling | IAM | SSM | CloudWatch | SNS | EBS | VPC*

## Why This Project?

Real-world web infrastructure needs more than simply running a website on a server. It should be able to *handle traffic, recover from failures, protect access, monitor important events, and maintain backups*.

This project focuses on those practical cloud infrastructure requirements using AWS-native services.

## Key Features

* PHP website hosted on Amazon EC2 with RDS MySQL
* Application Load Balancer for traffic distribution
* Auto Scaling configured for *1–3 EC2 instances*
* Automated S3 backup every *5 minutes*
* Separate S3 prefixes for webpages and logs
* CloudWatch monitoring for infrastructure events
* SNS email notifications for monitoring and scaling events
* EBS snapshots created every *12 hours*
* Latest *2 EBS snapshots* retained
* S3 Lifecycle rules for older log versions
* Secure EC2 administration using *SSM Session Manager*
* IAM roles used for AWS resource permissions

### Architecture Flow

*Users → Application Load Balancer → Auto Scaling EC2 → RDS MySQL*

*EC2 → Amazon S3 → Automated Website & Log Backups*

*EC2 → EBS Snapshots → Recovery*

*CloudWatch → SNS → Email Notifications*

*SSM Session Manager → Secure EC2 Administration*

## Backup Configuration

### Amazon S3 Backup

* Website files and logs are synchronized to Amazon S3 every *5 minutes*.
* Separate S3 prefixes are used for:

  * webpages/
  * logs/
* S3 Lifecycle rules automatically manage older log versions.
* Older log versions are removed after *2 days*.

### EBS Snapshot Backup

* EBS snapshots are created automatically every *12 hours*.
* Only the latest *2 snapshots* are retained.
* Snapshots provide an additional recovery mechanism for EC2 storage.

## Monitoring & Alerts

Amazon CloudWatch is used to monitor the AWS infrastructure and application environment.

Amazon SNS is configured to send email notifications for important infrastructure events, including Auto Scaling activity.

This monitoring setup helps identify infrastructure changes, scaling activity, and potential availability issues so that the environment can be observed and managed more effectively.

## Security

* IAM roles are used to provide required AWS permissions.
* EC2 administration is performed using *SSM Session Manager* instead of direct SSH access.
* Application traffic is handled through an Application Load Balancer.
* EC2 instances are managed through an Auto Scaling Group.
* RDS MySQL is used as the application database layer.
* VPC networking provides network isolation.
* Automated S3 backups and EBS snapshots provide recovery options.

## Technologies

*PHP | Apache | Linux | MySQL | AWS*

## Deployment Flow

1. User sends a request to the web application.
2. The request reaches the Application Load Balancer.
3. The load balancer forwards traffic to healthy EC2 instances.
4. Auto Scaling maintains the required number of application instances.
5. EC2 instances communicate with the RDS MySQL database.
6. Website files and logs are synchronized to Amazon S3 every 5 minutes.
7. EBS snapshots are created every 12 hours.
8. CloudWatch monitors infrastructure events.
9. SNS sends email notifications for configured alerts.
10. SSM Session Manager provides secure administrative access to EC2.


## Future Enhancements

* Implement *Amazon CloudFront* for faster content delivery.
* Add *AWS WAF* for web application protection.
* Enable *HTTPS* using AWS Certificate Manager (ACM).
* Configure *Amazon Route 53* for domain and DNS management.
* Implement centralized log analysis using *CloudWatch Logs*.
* Configure advanced *RDS backup and point-in-time recovery*.
* Introduce *AWS Backup* for centralized backup management.
* Add vulnerability scanning and security monitoring.
* Implement *CI/CD automation* for application deployment.
* Add *cross-region backup replication* for improved disaster recovery.
* Create centralized *CloudWatch dashboards* for infrastructure visibility.

## Outcome

Successfully implemented a *scalable and resilient AWS web server infrastructure* with:

* High availability
* Auto Scaling
* Load balancing
* Automated S3 backups
* EBS snapshot recovery
* CloudWatch monitoring
* SNS alerting
* IAM-based access control
* Secure SSM administration

The project demonstrates practical experience in designing and managing an AWS-based web infrastructure with *scalability, security, monitoring, backup, and recovery capabilities*.

## Skills Demonstrated

* AWS cloud infrastructure design
* EC2 and Apache web server management
* Application Load Balancer configuration
* Auto Scaling configuration
* Amazon RDS MySQL integration
* Amazon S3 backup automation
* IAM permission management
* SSM Session Manager administration
* CloudWatch monitoring and SNS alerting
* EBS snapshot and recovery planning
* AWS networking and VPC fundamentals

## Repository Structure

> Attack-Proof-Web-Server/  
> ├── screenshots/  
> │   ├── architecture-diagram.png     
> │   ├── final-website-alb.png  
> │   ├── alb-target-group.png  
> │   ├── auto-scaling-group.png  
> │   └── s3-backup.png  
> └── README.md

## Conclusion
- Successfully built a *scalable and resilient AWS web server architecture* with high availability
- Implemented *automated backups, monitoring, alerting, and recovery mechanisms*
- Designed infrastructure to *handle traffic changes* and improve application availability  
- Provided *reliable backup and recovery options* for disaster management
  
