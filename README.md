# Amazon CloudWatch Agent installation on Amazon Linux Image 2 (AMI2)
The Amazon CloudWatch Agent is software developed for the [CloudwatchAgent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html)

# Overview
Here we are use **x86-64 linux AMI2** architecture. the reason behind installation of **CWAGENT** are aws are not provided for more **real** and **quick** monitoring analysis tools.cloudwach have with some limitation. so we require **memory utilization**,**CPU utilization** and **Disk utilizations** for our EC2 instance. below here some useful stepts to **installation steps.**

# IAM ROLEs for AMI(CW)
1.Sign in to the AWS Management Console and open the IAM console at [AWS IAM](https://console.aws.amazon.com/iam/)</br>
2.In the navigation pane, choose  **Roles** and then choose  **Create role.**</br>
3.Under **Select type of trusted entity**, choose **AWS service.**</br>
4.Immediately under **Common use cases**, choose **EC2**,and then choose **Next: Permissions.**</br>
5.In the list of policies, select the check box next to **CloudWatchAgentServerPolicy.** If necessary, use the search box to find the policy.</br>
6.To use Systems Manager to install or configure the CloudWatch agent, select the box next to **AmazonSSMManagedInstanceCore**. This AWS managed policy enables an instance to use Systems Manager service core functionality. If necessary, use the search box to find the policy. This policy isn't necessary if you start and configure the agent only through the command line.</br>
7.Choose **Next: Tags.**</br>
8.(Optional) Add one or more tag-key value pairs to organize, track, or control access for this role, and then choose **Next: Review.**</br>
9.For **Role name**, enter a name for your new role, such as **CloudWatchAgentServerRole** or another name that you prefer.</br>
10.(Optional) For **Role description**, enter a description.</br>
11.Confirm that **CloudWatchAgentServerPolicy** and optionally **AmazonSSMManagedInstanceCore** appear next to **Policies.**</br>
12.Choose **Create role.**

**The role is now created.**

# Create EC2 Instance steps

1.Sign in to the AWS Management Console and open the EC2 console at [AWS EC2](https://console.aws.amazon.com/ec2/)</br>
2.From the EC2 console dashboard, in the **Launch instance box**, choose **Launch instance**, and then choose **Launch instance** from the options that appear.</br>
3.Under **Name and tags**, for **Name**, enter a descriptive name for your instance.</br>
4.Under **Application and OS Images (Amazon Machine Image)**, do the following:</br>
  ***a)***.Choose **Quick Start**, and then choose Amazon Linux. This is the operating system (OS) for your instance.</br>
 ***b)***.From **Amazon Machine Image (AMI)**, select an HVM version of Amazon Linux 2. Notice that these AMIs are marked **Free tier** eligible. An </br>Amazon Machine Image (AMI) is a basic configuration that serves as a template for your instance.</br>
5.Under **Instance type**, from the **Instance type** list, you can select the hardware configuration for your instance. Choose the ***t2.micro*** instance</br> type, which is selected by default. The ***t2.micro*** instance type is eligible for the free tier. In Regions where ***t2.micro*** is unavailable, you can use</br> a ***t3.micro*** instance under the free tier.</br>
6.Under **Key pair (login)**, for **Key pair name**, choose the key pair that you created when getting set up.</br>
7.Next to **Network settings**, choose **Edit**. For **Security group name**, you'll see that the wizard created and selected a security group for you. You can use this security group, or alternatively you can select the security group that you created when getting set up using the following steps:</br>
<ln>a)Choose Select existing security group.</ln></br>
<ln>b)From Common **security groups**, choose your security group from the list of **existing security groups**.</ln>
    
8.Keep the **default** selections for the other **configuration settings** for your instance.</br>
9.select IAM Role **CloudWatchAgentServerRole**</br>
