# 📦 AWS Snowball – README

## 📘 Overview

**AWS Snowball** is a part of the **AWS Snow Family**, offering secure and rugged devices to move **large volumes of data** into and out of AWS. It is ideal for scenarios where **network transfer is too slow or impractical** due to scale or connectivity.

> "Physically ship your data to AWS instead of uploading it over the internet."

---

## 📦 Snowball Device Types

| Device                              | Use Case                          | Capacity      | Notes                                       |
| ----------------------------------- | --------------------------------- | ------------- | ------------------------------------------- |
| **Snowball Edge Storage Optimized** | Large-scale data transfer         | ~80 TB usable | Can run EC2 and Lambda functions            |
| **Snowball Edge Compute Optimized** | Edge computing + GPU processing   | ~42 TB usable | Supports ML, analytics on-site              |
| **Snowcone**                        | Lightweight, portable edge device | 8 TB          | USB-C powered, ideal for harsh environments |

---

## 🔁 Use Cases

| Scenario                             | Solution with Snowball               |
| ------------------------------------ | ------------------------------------ |
| Large-scale cloud data migration     | Use Snowball Edge Storage Optimized  |
| Edge computing in remote areas       | Use Snowball Edge Compute Optimized  |
| Disaster recovery backups            | Use Snowball for backup and restore  |
| AI/ML in disconnected regions        | Use Snowball with GPU for processing |
| Data collection from ships, oil rigs | Snowcone/Snowball in rugged cases    |

---

## 🔐 Security Features

- **Data encryption (AES-256)** by default
- Managed encryption keys with **AWS KMS**
- **Tamper-resistant** hardware
- Secure Erase: auto-deletion after successful import
- Enforced IAM roles for usage control

---

## ⚙️ How It Works

AWS Console → Create Snowball job

AWS ships encrypted device to your site

You connect via Snowball client or AWS OpsHub

Transfer data to/from the device

Ship device back to AWS

AWS imports data into your S3 bucket

## 🖥️ You can also run:

- EC2 instances on Snowball Edge
- AWS Lambda functions
- Custom applications at the edge

---

## 🚚 Transfer Methods

| Method           | Description                                   |
| ---------------- | --------------------------------------------- |
| **AWS OpsHub**   | GUI-based local Snowball management           |
| **Snowball CLI** | Command-line access to device                 |
| **S3 SDK**       | Interact with Snowball as a local S3 endpoint |
| **NFS Adapter**  | Mount Snowball as a network drive             |

---

## 📈 Monitoring & Tracking

Track job progress in the AWS Console

Get shipment updates and notifications

Audit logs via AWS CloudTrail

## 📊 Cost Components

| Item                   | Pricing Notes                              |
| ---------------------- | ------------------------------------------ |
| Job Fee (device usage) | Per job (flat rate based on region/device) |
| Data Transfer          | Typically **free into AWS**, out is billed |
| Extra Days On-site     | Charged after first 10 days                |
| Shipping Fees          | Included in most regions                   |

## 🌐 Edge Computing Support (Snowball Edge)

- Run EC2 AMIs (up to 52 vCPUs, 208 GB RAM)

- Deploy Lambda functions

- Use NVIDIA GPUs (on Compute Optimized model)

Perform:

Video processing

Machine learning inference

Local analytics (SQL, stream)

## 🔍 Comparison: Snowball vs Snowcone vs Transfer

| Method           | Best For                              | Data Volume    | Transfer Speed        |
| ---------------- | ------------------------------------- | -------------- | --------------------- |
| **Snowball**     | Large offline transfers               | 10s–100s TB    | \~1 GB/sec locally    |
| **Snowcone**     | Small-scale/remote/off-grid transfers | \~8 TB         | USB-C, Wi-Fi/Ethernet |
| **AWS DataSync** | Online sync from NFS/SMB              | 100s of TB     | Over internet/VPN     |
| **AWS Transfer** | SFTP, FTP, FTPS file-based access     | Live file sync | Internet              |

## ✅ Summary

| Feature                    | Supported         |
| -------------------------- | ----------------- |
| Petabyte-scale transfer    | ✅ Yes            |
| Edge compute (EC2, Lambda) | ✅ Snowball Edge  |
| Offline data import/export | ✅ Yes            |
| Secure encrypted data      | ✅ AES-256 + KMS  |
| Rugged portable devices    | ✅ Yes (Snowcone) |
| Monitoring and tracking    | ✅ CloudTrail     |
