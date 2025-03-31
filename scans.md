# Scanning Guide for Cloud Security Compliance Audit – Nessus Scanning

This guide explains how to use **Nessus** to scan your **AWS** cloud environment for security vulnerabilities and misconfigurations. The goal of these scans is to identify potential risks and ensure your infrastructure adheres to security best practices.

---

## **Prerequisites**

Before starting the scan, ensure the following:

- **Nessus Installed**: You have successfully installed Nessus. If not, refer to the [Installation Guide](INSTALLATION.md).
- **Configured AWS Environment**: Your AWS environment is configured with Nessus. If not, follow the [Configuration Guide](CONFIGURATION.md).
- **Compliance Policy**: Ensure you have selected your compliance standards (e.g., **CIS**, **NIST**, **PCI-DSS**) as outlined in the [Compliance Guide](COMPLIANCE.md).

---

## **Step 1: Creating a New Scan**

1. **Log into Nessus**:
   - Open your Nessus interface by navigating to `https://<your-nessus-ip>:8834` in a web browser.
   - Log in with your Nessus credentials.

2. **Create a New Scan**:
   - In the Nessus dashboard, click on the **Scans** tab in the top menu.
   - Click on the **New Scan** button to create a new scan.

3. **Select Scan Type**:
   - Choose a scan type based on your security needs:
     - **Basic Network Scan**: For general vulnerability assessment.
     - **Advanced Scan**: For customized scan settings (including compliance checks, specific plugins, etc.).
     - **Compliance Scan**: To run compliance audits (e.g., **CIS**, **NIST**, **PCI-DSS**).

4. **Scan Configuration**:
   - Name your scan (e.g., **AWS Compliance Scan**).
   - Under **Targets**, specify the IP address ranges or domain names of your AWS environment that you want to scan.
   
---

## **Step 2: Configuring Scan Settings**

1. **Select Scan Plugins**:
   - You can enable specific plugins for your scan. Some recommended plugins for cloud security are:
     - **AWS Configuration Compliance**: For auditing your AWS configuration against CIS and NIST standards.
     - **Vulnerability Detection**: For scanning known vulnerabilities in AWS services like EC2, S3, IAM, etc.

2. **Configure Credentials** (Optional):
   - For deeper scanning, you may provide AWS credentials (access keys or IAM roles) to allow Nessus to access your AWS environment securely. This enables Nessus to detect vulnerabilities that are not visible from the outside (e.g., IAM misconfigurations).
   
   - To configure credentials:
     - Under the **Credentials** section, enter your **AWS Access Key** and **Secret Key** (or use an IAM role).
   
3. **Set Scan Schedule** (Optional):
   - Nessus allows you to schedule scans to run at regular intervals. You can set your scans to run daily, weekly, or monthly depending on your needs.

---

## **Step 3: Running the Scan**

1. **Launch the Scan**:
   - After configuring the scan, click on **Save** to save the scan configuration.
   - Then, click on **Launch** to begin scanning your AWS environment.
   
2. **Monitoring the Scan**:
   - Once the scan starts, you can monitor the progress in real-time. Nessus will display the number of hosts scanned and the vulnerabilities detected during the process.

---

## **Step 4: Reviewing the Scan Results**

1. **Access Scan Results**:
   - After the scan completes, go to the **Scans** tab.
   - Click on the scan you just launched to view the results.

2. **Scan Result Overview**:
   - Nessus provides a detailed report with the following information:
     - **Vulnerabilities Detected**: A list of vulnerabilities found in the scanned environment.
     - **Compliance Results**: Whether the scanned environment meets compliance requirements for frameworks like **CIS**, **NIST**, or **PCI-DSS**.
     - **Severity Levels**: Vulnerabilities are categorized by severity: **Critical**, **High**, **Medium**, and **Low**.

3. **Detailed Findings**:
   - Each finding provides:
     - **Description**: A detailed explanation of the vulnerability or misconfiguration.
     - **Risk Level**: Severity of the issue (Critical, High, Medium, Low).
     - **Affected Resources**: AWS services or resources impacted by the vulnerability.
     - **Recommendations**: Suggested remediation actions to fix the issue.

---

## **Step 5: Remediation and Re-scanning**

1. **Remediate Vulnerabilities**:
   - Based on the findings from the scan, address the identified vulnerabilities. Some common remediations include:
     - **Open Ports**: Close unnecessary open ports in your security group settings.
     - **Misconfigured IAM Roles**: Restrict permissions to follow the principle of least privilege.
     - **Unencrypted Resources**: Enable encryption for EBS volumes, S3 buckets, etc.

2. **Re-scan the Environment**:
   - Once the vulnerabilities are remediated, run another scan to verify that the issues have been resolved.
   - Ensure that the environment now meets the compliance standards.

---

## **Step 6: Automating Future Scans**

1. **Schedule Periodic Scans**:
   - To maintain security and compliance, schedule regular scans for your AWS environment. You can configure Nessus to automatically scan your environment at specific intervals (e.g., daily, weekly, or monthly).
   
2. **Track Vulnerability Trends**:
   - By scheduling scans periodically, you can track trends in vulnerability remediation and ensure continuous improvement in your cloud security posture.

---

## **Scan Types and Use Cases**

### 1. **Port Scanning**:
   - Identifies open ports and services on cloud resources (e.g., EC2 instances).
   - Useful for detecting exposed services that could be vulnerable to attacks.

### 2. **Configuration Audits**:
   - Validates cloud resources against security best practices.
   - Examples include ensuring EC2 instances are not publicly accessible, IAM roles follow the principle of least privilege, and S3 buckets are properly secured.

### 3. **Vulnerability Scanning**:
   - Identifies known vulnerabilities in cloud services (e.g., unpatched software or services with known CVEs).
   - Helps prevent attacks leveraging unpatched vulnerabilities.

---

## **Additional Resources**

- **[Nessus Documentation](https://docs.tenable.com/nessus/)**: Official documentation for using Nessus.
- **[AWS Security Best Practices](https://aws.amazon.com/security/)**: AWS's security best practices for cloud environments.
- **[CIS AWS Foundations Benchmark](https://www.cisecurity.org/benchmark/amazon-web-services/)**: Security guidelines for AWS environments based on the CIS benchmarks.

---

