                                                                      EC2 Health Monitoring Script

Project Overview

The EC2 Health Monitoring Script is a Bash automation tool designed to monitor the health of a Linux server or Amazon EC2 instance. It checks critical system metrics such as CPU usage, memory utilization, disk space, and system load average. When any metric exceeds a predefined threshold, the script generates an email alert and logs the event for further analysis.

This project is useful for DevOps engineers, Linux administrators, and cloud engineers who want a lightweight monitoring solution without relying on third-party monitoring tools.

Features

* Monitors CPU utilization
* Checks memory usage
* Monitors disk usage for all mounted partitions
* Tracks system load average
* Generates timestamped health reports
* Sends email alerts when thresholds are exceeded
* Logs all monitoring activities
* Displays system information including hostname, kernel version, uptime, and current date
* Easy to schedule using Cron

Technologies Used

* Bash Shell Scripting
* Linux
* Amazon EC2
* Cron
* Mail Utility (`mail`)
* AWK
* BC Calculator
* GREP
* SED

Health Checks Performed

The script performs the following health checks:

* CPU Usage
* Memory Usage
* Disk Usage
* System Load Average
* Hostname Information
* Kernel Version
* System Uptime
* Current Date and Time

Threshold Configuration

The default monitoring thresholds are:

| Metric       | Threshold |
| ------------ | --------- |
| CPU Usage    | 80%       |
| Memory Usage | 80%       |
| Disk Usage   | 80%       |
| Load Average | 2.0       |

These values can be modified in the script according to your requirements.

Prerequisites

Before running the script, ensure the following packages are installed:

* Bash
* mailutils (or mailx)
* bc
* awk
* grep
* sed

Ubuntu/Debian:
sudo apt update
sudo apt install mailutils bc -y

Amazon Linux / RHEL / CentOS:
sudo yum install mailx bc -y

How to Run

Make the script executable:
chmod +x ec2_health_monitor.sh

Run the script:
./ec2_health_monitor.sh

Email Alerts
Whenever a monitored resource exceeds its configured threshold, the script automatically sends an email notification.

Update the recipient email address in the script:
ALERT_EMAIL="your_email@example.com"
Configure your mail server (SMTP/Postfix/Sendmail) before using the alert feature.

Each report includes:

* System information
* CPU usage
* Memory usage
* Disk usage
* Load average
* Warning messages
* Email alert status

Automating with Cron

Run the script every 10 minutes:
crontab -e

Add:
*/10 * * * * /home/ec2-user/ec2_health_monitor.sh

Monitoring Workflow

              Start
                │
                ▼
     Collect System Information
                │
                ▼
        Check CPU Usage
                │
                ▼
      Check Memory Usage
                │
                ▼
       Check Disk Usage
                │
                ▼
     Check Load Average
                │
                ▼
 Threshold Exceeded?
        │              │
      Yes              No
        │              │
        ▼              ▼
 Send Email Alert   Continue
        │
        ▼
 Generate Health Report
        │
        ▼
       Finish

Benefits

* Lightweight monitoring solution
* Automated health checks
* Early detection of resource issues
* Timestamped logging
* Email-based notifications
* Easy deployment on Linux and EC2 instances
* Cron integration for scheduled monitoring

Future Enhancements

* Slack or Microsoft Teams notifications
* AWS SNS integration
* CloudWatch metric publishing
* HTML email reports
* Log rotation
* CSV or JSON report export
* Multiple email recipients
* Automatic cleanup of old reports

Learning Outcomes

This project demonstrates:

* Bash scripting fundamentals
* Linux system administration
* EC2 instance monitoring
* Process automation
* Log management
* Shell functions
* Conditional statements
* Email notifications
* Cron scheduling
* DevOps scripting best practices

Author:
Padmavathi M
DevOps Engineer


