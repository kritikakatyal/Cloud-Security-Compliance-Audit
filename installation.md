# Installation Guide for Cloud Security Compliance Audit – Nessus Scanning

This guide provides detailed instructions on how to install and set up **Nessus** for performing a Cloud Security Compliance Audit on **AWS** environments. Follow the steps below to get started with Nessus installation and preparation for cloud security scans.

---

## **Prerequisites**

Before proceeding with the installation, ensure you have the following:

- **Operating System**: Linux (Ubuntu 20.04+), Windows, or macOS
- **System Requirements**: At least 2 GB of RAM and 10 GB of disk space
- **Cloud Provider Account**: An active **AWS** account with the necessary permissions to perform security scanning
- **Network Configuration**: Ensure that your machine can communicate with **AWS** for scanning purposes

---

## **Step 1: Download Nessus**

1. Visit the official **[Nessus Downloads Page](https://www.tenable.com/downloads/nessus)**.
2. Select the appropriate version of Nessus based on your operating system:
   - **Linux**: Choose the distribution (e.g., Ubuntu, CentOS, etc.)
   - **Windows**: Select the Windows installer package
   - **macOS**: Choose the macOS installer
3. Click **Download** to begin the installation package download.

---

## **Step 2: Install Nessus**

### **For Linux (Ubuntu 20.04+)**:

1. **Install Nessus**:
   - First, update your system:
     ```bash
     sudo apt-get update
     sudo apt-get upgrade
     ```
   - Install Nessus by running the following command:
     ```bash
     sudo dpkg -i Nessus-<version>-ubuntu1110_amd64.deb
     ```
     Replace `<version>` with the specific version you downloaded.

2. **Start Nessus**:
   - Start the Nessus service:
     ```bash
     sudo systemctl start nessusd
     ```

3. **Enable Nessus to Start on Boot**:
   - Run this command to ensure Nessus starts automatically on boot:
     ```bash
     sudo systemctl enable nessusd
     ```

### **For Windows**:

1. Run the **Nessus installer** you downloaded.
2. Follow the on-screen instructions to complete the installation.
3. Once installed, Nessus will automatically start.

### **For macOS**:

1. Open the **Nessus installer** `.dmg` file you downloaded.
2. Drag the **Nessus** application to the **Applications** folder.
3. Open **Nessus** from the **Applications** folder and follow the setup instructions.

---

## **Step 3: Access Nessus Web Interface**

1. After installation, access the Nessus web interface:
   - Open your browser and navigate to: [http://localhost:8834](http://localhost:8834)
2. The first time you access Nessus, you will be prompted to create an account. Follow the instructions to complete the setup.

---

## **Step 4: Activate Nessus**

1. After setting up your account, Nessus will require activation.
2. **Enter the Activation Code**:
   - If you have purchased Nessus, you will have received an activation code. Enter this code when prompted.
   - If you're using Nessus Essentials (free version), you can register for an activation code on the **[Nessus Registration Page](https://www.tenable.com/products/nessus/nessus-essentials)**.

---

## **Step 5: Set up AWS Integration in Nessus**

1. To connect Nessus with your AWS environment, navigate to **Settings** in the Nessus web interface.
2. Select **Cloud Configuration** and enter the following AWS details:
   - **AWS Access Key ID**: Your AWS access key.
   - **AWS Secret Access Key**: Your AWS secret key.
   - **Region**: Select the AWS region for scanning (e.g., `us-east-1`).
3. Save the settings and verify that Nessus can successfully communicate with your AWS environment.

---

## **Step 6: Update Nessus Plugins**

Nessus regularly releases updates to security plugins. To ensure that your Nessus installation has the latest vulnerability checks:

1. In the Nessus web interface, navigate to **Settings**.
2. Under **Advanced**, click **Update Plugins**.
3. Wait for the update process to complete. This may take a few minutes depending on your internet connection.

---

## **Step 7: Verify Installation**

To verify that Nessus has been successfully installed and is running correctly:

1. In the Nessus web interface, navigate to **Dashboard**.
2. You should see that Nessus is active and ready to start scanning your AWS environment.
3. Optionally, run a test scan using one of the predefined templates to ensure that the installation is functioning properly.

---

## **Step 8: Troubleshooting**

If you encounter any issues during installation, refer to the **[Troubleshooting Guide](TROUBLESHOOTING.md)** for common solutions and fixes.

---

## **Additional Resources**

- **[Nessus Documentation](https://docs.tenable.com/nessus/)**: Detailed documentation on Nessus installation and usage.
- **[AWS Setup Guide](https://aws.amazon.com/training/)**: Official AWS documentation and setup guides.

---