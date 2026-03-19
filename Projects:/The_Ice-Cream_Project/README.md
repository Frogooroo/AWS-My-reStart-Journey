# 🍦 Static Website — Ice Cream Shop

A step-by-step guide to deploying a static website on **Amazon S3** using the AWS Management Console.

---

## Table of Contents

1. [Start the Sandbox](#1-start-the-sandbox)
2. [Access the AWS Management Console](#2-access-the-aws-management-console)
3. [Create a Bucket](#3-create-a-bucket)
4. [Enable Static Website Hosting](#4-enable-static-website-hosting)
5. [Add a Public Bucket Policy](#5-add-a-public-bucket-policy)
6. [Upload the Index Document](#6-upload-the-index-document)
7. [Run the Website](#7-run-the-website)

---

## 1. Start the Sandbox

Click **Start Lab** to launch the lab environment and wait until you see **"Lab status: ready"**, then close the panel.

---

## 2. Access the AWS Management Console

1. Click **AWS** (next to Start Lab) to open the AWS Management Console in a new tab. You will be signed in automatically.
2. If the tab doesn't open, allow pop-ups in your browser and try again.
3. Arrange the AWS Console and these instructions side by side.

---

## 3. Create a Bucket

1. Open the S3 console: [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/)
2. Click **Create bucket**.
3. Enter the bucket name:
   ```
   static-website-icecream-shop
   ```
4. Select a **Region** — choose one close to you for lower latency and cost.  
   > ⚠️ The region also determines your S3 website endpoint URL.
5. Leave the default settings and click **Create bucket**.

---

## 4. Enable Static Website Hosting

1. Open the S3 console: [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/)
2. Click **General purpose buckets** and select your bucket.
3. Go to the **Properties** tab.
4. Scroll to **Static website hosting** and click **Edit**.
5. Choose **Use this bucket to host a website** and enable static website hosting.
6. Enter `index.html` as the **Index document** (case-sensitive).
7. Click **Save changes**.
8. Copy the **Website endpoint URL** to test your site later.

---

## 5. Add a Public Bucket Policy

This policy makes your bucket content publicly readable.

1. Open the S3 console: [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/)
2. Select your bucket: `static-website-icecream-shop`.
3. Go to the **Permissions** tab.
4. Scroll to **Bucket policy** and click **Edit**.
5. Copy and paste the policy below into the editor.
6. Replace `Bucket-Name` with `static-website-icecream-shop`.
7. Click **Save changes**.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": ["s3:GetObject"],
      "Resource": ["arn:aws:s3:::static-website-icecream-shop/*"]
    }
  ]
}
```

---

## 6. Upload the Index Document

1. Create a file named `index.html` and save it locally.
2. Open the S3 console: [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/)
3. Select your bucket.
4. Confirm that **Static website hosting** is enabled and `index.html` is set as the index document.
5. Upload the file using one of these methods:
   - Drag and drop `index.html` into the bucket, **or**
   - Click **Upload** and select the file.

---

## 7. Run the Website

Open the **Bucket website endpoint** URL in a new browser tab:

[http://static-website-icecream-shop.s3-website-us-west-2.amazonaws.com](http://static-website-icecream-shop.s3-website-us-west-2.amazonaws.com)

Your ice cream shop website should now be live! 🎉

<img width="334" height="191" alt="13 (1)" src="https://github.com/user-attachments/assets/fb81d5a0-b522-4219-be65-d678cbb90e75" />


---

## Resources

- [AWS S3 Static Website Hosting Docs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [S3 Bucket Policy Reference](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-policies.html)
