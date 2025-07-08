# 🛰️ Amazon MSK (Managed Streaming for Apache Kafka)

## 📘 Overview

**Amazon MSK** is a fully managed, highly available, and secure service for **Apache Kafka** on AWS. It makes it easy to build and run real-time streaming applications and data pipelines using Apache Kafka without managing the infrastructure yourself.

> With Amazon MSK, you get **Kafka without the operational burden** — AWS handles provisioning, maintenance, patching, and scaling.

---

## 🚀 Why Use Amazon MSK?

| Feature                   | Benefit                                           |
| ------------------------- | ------------------------------------------------- |
| Fully Managed             | AWS manages the Kafka cluster and Zookeeper       |
| Highly Available          | Multi-AZ deployments with automatic recovery      |
| Secure                    | Encryption in transit & at rest, IAM, VPC support |
| Integrated Monitoring     | CloudWatch metrics and logs                       |
| Open Source Compatibility | 100% compatible with Apache Kafka APIs            |
| Scalability               | Scale brokers and storage independently           |

---

## 🧩 Core Components

| Component                      | Description                                         |
| ------------------------------ | --------------------------------------------------- |
| **Kafka Cluster**              | The core Kafka brokers managed by AWS               |
| **Zookeeper Nodes**            | Used for cluster coordination (also managed by AWS) |
| **Client Producers/Consumers** | Apps that send/read data from topics                |

---

## ⚙️ How It Works

Producer App → MSK Broker (Kafka Topic) → Consumer App
↓
Stores messages for configured retention

- Producers publish messages to **Kafka topics**
- MSK brokers replicate and persist messages
- Consumers read from topics (real-time or delayed)

---

## 🧰 Use Cases

| Use Case                    | Description                                     |
| --------------------------- | ----------------------------------------------- |
| Real-time analytics         | Clickstream, logs, IoT data                     |
| Event-driven microservices  | Decoupled producer/consumer services            |
| Stream processing pipelines | With Apache Flink, Spark, or Kinesis            |
| Data lake ingestion         | MSK → S3 (via Lambda, Firehose, or Glue)        |
| ML & AI data pipelines      | Stream data into SageMaker or training datasets |

---

## 📦 Kafka Features Supported

| Feature                    | Amazon MSK Support    |
| -------------------------- | --------------------- |
| Kafka APIs                 | ✅ Yes                |
| Kafka Streams              | ✅ Yes                |
| Kafka Connect              | ✅ Yes (self-managed) |
| Kafka Security (SASL, TLS) | ✅ Yes                |
| Custom configurations      | ✅ Partial            |
| Zookeeper                  | ✅ Managed by AWS     |

---

## 🔐 Security Features

- Encryption **at rest** using AWS KMS
- Encryption **in transit** via TLS
- IAM integration for MSK Connect & permissions
- VPC-only access (no public internet access)
- Supports **SASL/SCRAM authentication**

---

## 📊 Monitoring & Metrics

- **CloudWatch metrics** for:
  - `BytesInPerSec`, `BytesOutPerSec`
  - `CPUUtilization`, `DiskUsed`, `BrokerCount`
- **AWS CloudTrail** for auditing
- **Open Monitoring** with **Prometheus** & **Grafana**

---

## 🛠️ Creating a Cluster (Console/CLI)

### 1. **Choose Kafka Version**

Select a supported version of Apache Kafka (e.g., 2.8.1, 3.x).

### 2. **Configure Brokers**

- Number of brokers
- Instance type
- Storage size

### 3. **Set Networking**

- VPC + Subnets (multi-AZ recommended)
- Security groups
- Access control (IAM, TLS, SASL)

### 4. **Launch Cluster**

---

## 🧠 MSK Connect

- Run **Kafka Connect** plugins (e.g., JDBC, S3 sink)
- Fully managed **serverless connector infrastructure**
- Integrates with **Secrets Manager**, **IAM**, and **KMS**

---

## 📁 MSK Integration Options

| Integration Target             | Method                                             |
| ------------------------------ | -------------------------------------------------- |
| **S3 / Redshift / OpenSearch** | MSK Connect, Lambda, Firehose                      |
| **Lambda**                     | Trigger Lambda from Kafka via Event Source Mapping |
| **Glue / Athena**              | Use Kafka as source for ETL/query                  |
| **Flink / Spark**              | Use Amazon EMR, Kinesis Data Analytics             |

---

## 🧱 Example ArchitectureWeb

App → MSK Topic ← Mobile App

↓

MSK Connect (Sink)

↓

Amazon S3 / Redshift

Or:

IoT Devices → MSK → Lambda (Transform) → DynamoDB / S3 / SageMaker

---

## 💵 Pricing Overview

- **Broker instances** (per hour, based on type)
- **Storage (EBS)** for broker volumes (per GB/month)
- **Data transfer** across AZs or to consumers (standard VPC pricing)
- **MSK Connect** is billed separately (vCPU/hour + memory usage)

📌 Pricing details: [MSK Pricing](https://aws.amazon.com/msk/pricing/)

---

## 📚 References

- [MSK Official Documentation](https://docs.aws.amazon.com/msk/)
- [Apache Kafka](https://kafka.apache.org/)
- [MSK Connect](https://docs.aws.amazon.com/msk/latest/developerguide/msk-connect.html)
- [Monitoring MSK](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)

---

## ✅ Summary

| Feature       | Amazon MSK                           |
| ------------- | ------------------------------------ |
| Managed Kafka | ✅ Yes                               |
| Kafka Connect | ✅ (via MSK Connect or self-managed) |
| Zookeeper     | ✅ Managed by AWS                    |
| Security      | TLS, IAM, KMS, SASL                  |
| Integration   | Firehose, Lambda, Glue, Redshift     |
| Monitoring    | CloudWatch + Prometheus              |

---
