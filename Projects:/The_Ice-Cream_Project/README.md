# Lab – Introduction to Amazon EC2

In this lab, I explored the fundamentals of **Amazon EC2** by deploying and managing a cloud-based virtual server.

### Project Overview
I launched an EC2 instance using **Amazon Linux 2023** and configured it as a simple web server using a **User Data script** that automatically installed and started the Apache web server. Once the instance was running, I monitored its health and performance through the EC2 dashboard and Amazon CloudWatch.

I then updated the **security group inbound rules** to allow HTTP traffic on port 80 and successfully accessed the web page hosted on the instance using its public IPv4 address.

To practice cloud scalability, I resized the instance from `t3.micro` to `t3.small` and expanded the **Amazon EBS** storage volume from 8 GiB to 10 GiB.

Finally, I tested **termination protection**, confirmed that it prevented accidental deletion, then disabled it and terminated the instance.

---

### Key Skills Practiced
* **Instance Management:** Launching and configuring an EC2 instance.
* **Automation:** Deploying a web server using a User Data script.
* **Network Security:** Managing security groups and inbound/outbound network access.
* **Monitoring:** Tracking instance health and metrics via CloudWatch.
* **Elasticity & Scalability:** Resizing compute and storage resources.
* **Lifecycle Management:** Testing termination protection and instance lifecycle.

---

> [!IMPORTANT]
> **Status:** Exercise successfully completed and validated.

