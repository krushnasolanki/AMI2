# Amazon CloudWatch Agent installation on Amazon Linux Image 2 (AMI2)
The Amazon CloudWatch Agent is software developed for the [CloudwatchAgent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)

# Overview
Here we are use x86-64 linux AMI2 architecture. the reason behind installation of CWAGENT are aws are not provided for more real and quick monitoring analysis tools.cloudwach have with some limitation. so we require memory utilization,CPU utilization and Disk utilizations for our EC2 instance. below here some useful stepts to installation steps.

# IAM ROLEs for AMI(CW)
1.Sign in to the AWS Management Console and open the IAM console at [AWS IAM](https://console.aws.amazon.com/iam/)
2.In the navigation pane, choose  **Roles** and then choose  **Create role.**
3.Under **Select type of trusted8 entity**, choose **AWS service.**
