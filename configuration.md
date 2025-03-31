# Configuration Guide for Cloud Security Compliance Audit – Nessus Scanning

This guide provides detailed instructions for configuring **Nessus** to scan **AWS** cloud environments for security compliance audits. Follow the steps below to set up and configure Nessus to interact with your AWS environment.

---

## **Prerequisites**

Before configuring Nessus, ensure you have:

- **Nessus Installed**: Ensure you have successfully installed Nessus on your machine. If not, follow the [Installation Guide](INSTALLATION.md).
- **AWS Account**: You must have an active **AWS** account with the necessary permissions to perform security scanning.
- **AWS Access Keys**: You will need your **AWS Access Key ID** and **AWS Secret Access Key** to configure Nessus to connect with your AWS environment.

---

## **Step 1: Configure AWS IAM User for Nessus**

1. **Log in to AWS Management Console**:
   - Go to the [AWS Management Console](https://aws.amazon.com/console/) and log in with your account credentials.

2. **Create an IAM User** for Nessus:
   - Navigate to **IAM (Identity and Access Management)** in the AWS Console.
   - Click **Users** in the left sidebar, then click **Add User**.
   - Provide a **User Name** (e.g., `nessus-user`).
   - Select **Programmatic access** to enable access via the AWS API.

3. **Attach Permissions to the IAM User**:
   - Under **Set permissions**, choose **Attach policies directly**.
   - Attach the following policies:
     - **AmazonEC2ReadOnlyAccess**: Grants read-only access to EC2 resources.
     - **IAMReadOnlyAccess**: Grants read-only access to IAM resources.
     - **CloudWatchReadOnlyAccess**: Grants read-only access to CloudWatch resources.
   - Click **Next: Tags**, then click **Next: Review**, and finally **Create user**.

4. **Save the Access Keys**:
   - After creating the user, you will be shown the **Access Key ID** and **Secret Access Key**.
   - Copy and save these keys in a secure place, as you will need them to configure Nessus.

---

## **Step 2: Configure Nessus with AWS Credentials**

1. **Open Nessus Web Interface**:
   - Navigate to your Nessus web interface by going to [http://localhost:8834](http://localhost:8834) in your browser.
   - Log in with your Nessus account credentials.

2. **Navigate to Settings**:
   - In the top-right corner, click on the **Settings** icon (gear icon).
   - Under **Configuration**, click **Cloud Configuration**.

3. **Enter AWS Credentials**:
   - In the **Cloud Configuration** section, you will see fields for **AWS Access Key ID** and **AWS Secret Access Key**.
   - Enter the **Access Key ID** and **Secret Access Key** you saved when creating the IAM user.

4. **Select AWS Region**:
   - Choose the AWS region you want to scan (e.g., `us-east-1` or `us-west-2`).
   - Ensure the selected region matches the one where your AWS resources are located.

5. **Save Configuration**:
   - After entering the required information, click **Save** to apply the configuration.

---

## **Step 3: Test AWS Connection**

1. **Test Connection**:
   - Once the configuration is saved, you can test the connection to AWS by clicking the **Test Connection** button in the Nessus **Cloud Configuration** section.
   - If the test is successful, it will indicate that Nessus has connected to your AWS environment correctly.

2. **Troubleshooting**:
   - If the test fails, ensure that:
     - The **Access Key ID** and **Secret Access Key** are correct.
     - The IAM user has the necessary permissions (refer to Step 1).
     - The selected AWS region is correct.
   - For additional troubleshooting, consult the **[Troubleshooting Guide](TROUBLESHOOTING.md)**.

---

## **Step 4: Configure Nessus Scan Policies for AWS**

1. **Create a New Scan**:
   - In the Nessus web interface, click on **Scans** in the left sidebar.
   - Click **New Scan**.

2. **Select Scan Template**:
   - From the **Scan Templates** list, select the appropriate scan template for AWS, such as **AWS EC2** or **AWS Security Configuration**.

3. **Configure Scan Settings**:
   - Name your scan (e.g., `AWS Security Audit`).
   - Configure any additional settings like scan schedule, scan targets (IP ranges or specific AWS instances), and other scan parameters.
   - Under **Credentials**, make sure to use the **AWS credentials** you configured earlier.

4. **Save and Launch the Scan**:
   - Once the scan is configured, click **Save**.
   - You can then click **Launch** to start the scan or schedule it for later.

---

## **Step 5: Configure Cloud-Specific Security Checks**

1. **AWS Security Checks**:
   - Ensure that Nessus is set to check the relevant security configurations for AWS services, such as:
     - **EC2 Instance Security Group Rules**: Verify that security groups are correctly configured to prevent unauthorized access.
     - **IAM Role Permissions**: Check for overly permissive IAM policies.
     - **S3 Bucket Permissions**: Ensure that S3 buckets are not publicly accessible.

2. **Custom Security Configurations**:
   - Depending on your organization's security policies, you can configure Nessus to check for additional custom security configurations, such as encryption settings, VPC configurations, etc.

---

## **Step 6: Review Cloud Compliance**

1. **Configure Compliance Frameworks**:
   - Nessus supports various compliance frameworks for AWS, including **CIS AWS Foundations** and **PCI-DSS**.
   - You can enable the desired compliance checks in the scan policy under the **Compliance** section.

2. **Start the Compliance Audit**:
   - Once the scan is configured with the relevant compliance settings, launch the scan to audit your AWS environment for compliance with industry standards.

---

## **Step 7: Monitor and Update Configuration**

1. **Monitor Scan Progress**:
   - You can monitor the progress of your scan from the **Scans** page in Nessus.
   - Once the scan completes, Nessus will provide a report with findings and recommendations.

2. **Regular Updates**:
   - Regularly update Nessus plugins to ensure that you have the latest security checks for AWS. This can be done from the **Settings** page under **Plugin Updates**.

---

## **Additional Resources**

- **[Nessus Documentation](https://docs.tenable.com/nessus/)**: Detailed documentation for configuring Nessus.
- **[AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/)**: AWS IAM user and policy setup.
- **[AWS Security Best Practices](https://aws.amazon.com/architecture/well-architected/)**: Best practices for securing AWS environments.

---


