# AWS EC2 Setup and Teardown Guide

This repository provides step-by-step instructions on how to configure an AWS EC2 instance, launch it with a user data script, and safely tear it down when finished.

---

## 🚀 Setup Instructions

1. **Sign in to AWS**
   - Go to the **EC2** service from the AWS Management Console.

2. **Create a Security Group**
   - Navigate to **Security Groups** (under *Network & Security*).
   - Click **Create security group** (orange button).
   - Fill in **Basic details**:
     - Name: Choose a meaningful name.
     - Description: Copy the name for simplicity.
   - Configure **Inbound rules**:
     - Type: `HTTP`
     - Source: `Anywhere-IPv4`
   - Leave **Outbound rules** unchanged.
   - Add tags (optional, but useful later).
   - Click **Create group** and confirm success.

3. **Launch an EC2 Instance**
   - Go to **Instances** > **Launch instances**.
   - Enter a **Name** under *Name and tags*.
   - Verify **Instance type** = `t3.micro` (change if needed).
   - **Key pair (login):**
     - Select **Create key pair**, give it a name, and download the `.pem` file (ignore for now).
   - **Network settings:**
     - Under *Firewall*, choose **Select existing security group**.
     - Select the security group you just created.
   - Skip **Configure storage**.
   - Expand **Advanced details**:
     - Under *User data*, paste the contents of this script:  
       [EC2 Script](https://github.com/balericaclass7/bmc5/blob/main/ec2scrpit)
   - Click **Launch instance**.

4. **Verify the Instance**
   - On the success screen, click the instance ID link in the green box.
   - In the *Instance summary*, copy the **Public DNS** value (do not click it).
   - In a new browser tab, navigate to:
     ```
     http://<your-public-dns>
     ```
   - You should now see:  
     **AWS Instance Details – Samurai Katana**

🎉 Congratulations — your EC2 instance is running!

---

## 🗑️ Teardown Instructions

When you are done testing, **terminate** your instance to avoid charges:

1. Go to **EC2 > Instances**.
2. Check the box next to your running instance.
3. From **Instance state**, select **Terminate instance**.
4. Confirm termination. The instance will shut down permanently.

---

## 📌 Notes
- Always remember to **terminate** your instance when finished to avoid unexpected costs.
- This guide assumes the default AWS region. Adjust networking settings if using custom VPCs or regions.
- Only use the provided script for testing/demo purposes.

---

## 📄 License
This project is for educational purposes only. No license is provided for production use.
