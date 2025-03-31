# Compliance Guide for Cloud Security Compliance Audit – Nessus Scanning

This guide explains how to use **Nessus** to perform compliance checks on **AWS** cloud environments, ensuring that your infrastructure meets industry-standard security frameworks such as **CIS**, **NIST**, and **PCI-DSS**.

---

## **Prerequisites**

Before performing compliance checks, ensure the following:

- **Nessus Installed**: You have successfully installed Nessus on your system. If not, refer to the [Installation Guide](INSTALLATION.md).
- **Configured AWS Environment**: You have configured Nessus to scan your **AWS** environment. If not, follow the [Configuration Guide](CONFIGURATION.md).
- **Compliance Standards**: Identify the compliance frameworks you need to adhere to (e.g., **CIS**, **NIST**, **PCI-DSS**).

---

## **Step 1: Selecting Compliance Standards**

1. **Choose Your Compliance Framework**:
   - Nessus supports a variety of compliance frameworks. The most common frameworks for cloud security audits are:
     - **CIS AWS Foundations Benchmark**: A comprehensive set of best practices for securing AWS environments.
     - **NIST 800-53**: A standard for managing risk and safeguarding information in federal information systems.
     - **PCI-DSS**: Standards for securing payment card data and preventing fraud.

2. **Enable Compliance Plugins**:
   - In the **Nessus** web interface, go to the **Policies** section and create a new **Compliance Policy** or modify an existing one.
   - Under **Plugins**, enable the relevant compliance frameworks. The most common options include:
     - **CIS AWS Foundations**: Checkboxes for CIS-specific AWS security best practices.
     - **NIST 800-53**: Enable checks for controls that align with NIST standards.
     - **PCI-DSS**: Enable compliance checks for systems handling payment card data.

3. **Customize Compliance Checks** (Optional):
   - Nessus allows customization of compliance checks. You can enable or disable specific compliance checks according to your organization's needs.
   - This is useful when you are following a subset of the compliance framework or have specific internal security policies.

---

## **Step 2: Running a Compliance Scan**

1. **Create or Edit a Scan**:
   - Go to the **Scans** section in the **Nessus** interface.
   - Click on **New Scan** or edit an existing scan to include compliance checks.
   
2. **Select Compliance Policy**:
   - In the **Scan Configuration** section, select the **Compliance Policy** you configured in Step 1 (e.g., **CIS AWS Foundations**, **NIST 800-53**, or **PCI-DSS**).
   
3. **Configure Scan Targets**:
   - Choose the appropriate scan targets. You can specify:
     - **IP ranges** for your cloud instances.
     - **AWS services** (e.g., EC2, S3, IAM).
   
4. **Run the Scan**:
   - After configuring the scan, click **Save** and then **Launch** to start the scan.
   - Nessus will automatically assess the selected AWS environment against the compliance frameworks you’ve chosen.

---

## **Step 3: Analyzing Compliance Results**

1. **Review Compliance Findings**:
   - After the scan completes, navigate to the **Scan Results** page.
   - The compliance findings will be categorized based on severity levels:
     - **Passed**: The resource complies with the compliance requirement.
     - **Failed**: The resource does not comply and may need remediation.
     - **Not Applicable (N/A)**: The resource is not relevant to that specific compliance check.

2. **Understanding the Findings**:
   - Each finding will provide detailed information about the compliance control being assessed, the result of the scan, and potential risks associated with non-compliance.
   - Example:
     - **CIS Benchmark - EC2 Instance Encryption**: **Failed** – Your EC2 instance is not using encrypted volumes, which is a violation of the CIS benchmark.

3. **Actionable Recommendations**:
   - Nessus will often provide specific recommendations for how to resolve any failed compliance checks. These may include:
     - Changing security group settings in AWS.
     - Enabling encryption for S3 buckets.
     - Updating IAM role permissions.

---

## **Step 4: Remediation and Re-scanning**

1. **Implement Remediations**:
   - After reviewing the results, implement the necessary changes to your AWS environment to resolve compliance issues. Some examples of remediation actions are:
     - Enabling encryption for EBS volumes and S3 buckets.
     - Restricting IAM roles to the principle of least privilege.
     - Configuring EC2 instances with proper security group settings.

2. **Re-scan Your Environment**:
   - Once you have implemented the required changes, re-run the compliance scan to verify that the issues have been resolved and that your environment is now compliant.

---

## **Step 5: Generate Compliance Reports**

1. **Generate a Compliance Report**:
   - Nessus allows you to generate detailed reports summarizing the compliance scan results. These reports can be customized to include:
     - **Pass/Fail Status**: Overview of all compliance checks.
     - **Vulnerability Details**: Information on any findings, including recommended fixes.
   
2. **Export the Report**:
   - Export the compliance report in various formats, such as **PDF**, **HTML**, or **CSV**. This can be useful for auditing and reporting purposes.

---

## **Common Compliance Issues**

Here are some common compliance issues found in AWS environments:

1. **Unencrypted EBS Volumes**:
   - Ensure that all **EBS volumes** are encrypted at rest to meet security standards.
   
2. **Excessive IAM Permissions**:
   - Restrict IAM roles to the minimum permissions required for each task. Follow the principle of least privilege.

3. **Publicly Accessible S3 Buckets**:
   - Ensure that S3 buckets are not publicly accessible, as this can lead to data leaks or breaches.

4. **Open Security Groups**:
   - Avoid overly permissive security group settings, such as allowing SSH or RDP access from any IP address.

---

## **Step 6: Monitor Compliance Over Time**

1. **Schedule Regular Scans**:
   - To maintain compliance over time, schedule periodic scans of your AWS environment.
   - Nessus allows you to schedule scans at regular intervals, ensuring continuous monitoring of your security posture.

2. **Track Compliance Trends**:
   - Nessus provides trends over time, allowing you to track improvements or regressions in your compliance status. This can be helpful for continuous improvement efforts.

---

## **Additional Resources**

- **[Nessus Documentation](https://docs.tenable.com/nessus/)**: Comprehensive documentation for using Nessus for compliance auditing.
- **[CIS AWS Foundations Benchmark](https://www.cisecurity.org/benchmark/amazon-web-services/)**: Detailed guidelines for AWS security based on the CIS benchmark.
- **[NIST 800-53 Security Controls](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)**: NIST's security control framework for federal systems.
- **[PCI-DSS Documentation](https://www.pcisecuritystandards.org/)**: Official PCI-DSS standards for securing payment card data.

---