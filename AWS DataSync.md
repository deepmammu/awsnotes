# ⚡ AWS DataSync – README

## 📘 Overview

**AWS DataSync** is a **secure, fast, online data transfer service** that simplifies, automates, and accelerates moving large amounts of data between:

- On-premises storage (NFS, SMB)
- AWS storage services like **Amazon S3**, **EFS**, and **FSx**

> Ideal for **migrating**, **backing up**, or **replicating** data with minimal manual intervention.

---

## 🚀 Key Benefits

- 🔄 Automates **incremental and full data transfers**
- ⚡ Up to **10× faster** than traditional transfer tools
- 🔐 Supports **encryption**, **compression**, **data integrity validation**
- 🧠 **Built-in scheduling and filtering**
- 💰 Pay only for **data copied** – no upfront costs

---

## 🧱 Supported Sources & Destinations

| Source / Destination               | Protocol / Type       |
| ---------------------------------- | --------------------- |
| On-prem NFS                        | NFSv3, NFSv4.1        |
| On-prem SMB                        | SMB 2.1, 3.0, 3.1.1   |
| Amazon S3                          | Object storage        |
| Amazon EFS                         | File storage          |
| Amazon FSx for Windows File Server | SMB-based file system |
| Amazon FSx for Lustre              | Parallel file system  |
| AWS Snowcone                       | Edge device transfer  |
| AWS Outposts                       | Hybrid environments   |

---

## 🔁 Use Cases

| Use Case                  | Why Use DataSync?                    |
| ------------------------- | ------------------------------------ |
| On-prem to AWS migration  | Fast, secure, incremental            |
| Hybrid cloud backup       | Scheduled sync from local to S3/EFS  |
| File server to Amazon FSx | Lift-and-shift for Windows workloads |
| AWS-to-AWS transfer       | Region-to-region or S3 to FSx        |
| One-time or ongoing sync  | Flexible scheduling support          |

---

## ⚙️ How It Works

Source (On-prem or AWS)

↓

DataSync Agent (on-prem VM or AWS-managed)

↓

Destination (S3, EFS, FSx)

- Install and activate **DataSync agent** (only for NFS/SMB on-prem)
- Define **source** and **destination**
- Configure **task options** (schedule, filters, logging)
- Monitor **task execution** in console

---

## 🛠️ Components

| Component          | Description                                    |
| ------------------ | ---------------------------------------------- |
| **Agent**          | Software appliance that connects local storage |
| **Task**           | DataSync job definition                        |
| **Task Execution** | Specific run of a task                         |
| **Location**       | Source/destination location definition         |

---

## 🔐 Security Features

- **Data encryption in transit** (TLS)
- **Data encryption at rest** (KMS)
- **VPC-only traffic** (no public IPs required)
- **IAM policies** for fine-grained access control
- **CloudWatch Logs** and **CloudTrail** integration

---

## ⚙️ Task Settings (Examples)

| Option                      | Description                                        |
| --------------------------- | -------------------------------------------------- |
| **Preserve Timestamps**     | Keep original file times                           |
| **Overwrite Mode**          | Replace, skip, or verify files                     |
| **Delete Option**           | Remove files from destination if missing at source |
| **Include/Exclude Filters** | Select specific files/folders                      |
| **Bandwidth Throttling**    | Limit transfer rate                                |

---

## 📈 Monitoring & Logging

- **Amazon CloudWatch** for task metrics
- **CloudWatch Logs** for execution logs
- **CloudTrail** for API usage auditing
- Console shows **status**, **bytes transferred**, **files scanned**, etc.

---

## 💵 Pricing Summary

| Item                        | Pricing                                  |
| --------------------------- | ---------------------------------------- |
| **Data transfer**           | \$0.0125 per GB copied (as of July 2025) |
| **Agent deployment**        | Free (on-premises VM)                    |
| **No cost for idle agents** | Billed only when data is transferred     |

## ✅ Best Practices

Use filters to reduce unnecessary data

Schedule during low-traffic windows

Enable task logging for debugging and audits

Monitor task status and errors in CloudWatch

For large jobs, break into smaller directory batches

## 🧩 Comparison with Similar Services

| Service                      | Use Case                                |
| ---------------------------- | --------------------------------------- |
| **AWS DataSync**             | Automated, repeated file sync/migration |
| **AWS Snowball**             | Petabyte-scale offline transfer         |
| **AWS Transfer Family**      | Managed FTP/SFTP service                |
| **S3 Transfer Acceleration** | High-speed uploads over internet        |

## ✅ Summary

| Feature                  | Supported                    |
| ------------------------ | ---------------------------- |
| Transfer type            | NFS, SMB, S3, EFS, FSx       |
| Agent required (on-prem) | ✅ Yes                       |
| Scheduling               | ✅ Yes (hourly, daily, etc.) |
| Filters                  | ✅ Include/Exclude patterns  |
| Bandwidth control        | ✅ Yes                       |
| Cloud-native integration | ✅ CloudWatch, IAM, KMS      |
