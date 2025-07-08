# ⚡ Amazon Kinesis – README

## 📘 Overview

**Amazon Kinesis** is a fully managed, scalable, and real-time data streaming service provided by AWS. It enables you to **collect, process, and analyze streaming data** from various sources (IoT devices, apps, logs, social feeds) in real-time.

It supports **low-latency data streaming** use cases such as analytics, monitoring, machine learning pipelines, and event-driven applications.

---

## 🧩 Kinesis Services Breakdown

### 1. 📥 **Amazon Kinesis Data Streams (KDS)**

> Real-time, low-latency streaming platform for custom applications.

- Build custom applications for processing high-throughput streams.
- Works with **KCL (Kinesis Client Library)**, AWS Lambda, or other consumer apps.
- Allows **shard-based parallel processing**.

### 2. 📊 **Amazon Kinesis Data Firehose**

> Easiest way to **load streaming data into AWS services** like S3, Redshift, or OpenSearch.

- **Fully managed ETL** (transform, batch, compress, encrypt).
- Supports **Lambda functions** for data transformation.
- Near real-time delivery with automatic scaling.

### 3. 🧠 **Amazon Kinesis Data Analytics**

> Real-time **SQL-based stream processing** on Kinesis or Kafka streams.

- Use **SQL queries** to analyze data directly from streams.
- Detect patterns, anomalies, or create real-time dashboards.

### 4. 🌐 **Amazon Kinesis Video Streams**

> Stream and analyze **live video, audio, or images**.

- Used in ML, security surveillance, and computer vision.
- Integrates with **Amazon Rekognition** and **SageMaker**.

---

## ⚙️ Architecture (Example: Real-Time Logs)

App/Web Logs → Kinesis Data Streams → Lambda (transform) → S3 / Redshift / OpenSearch

Or using Firehose:

IoT Sensor → Kinesis Firehose → S3 + Athena + QuickSight

---

## 🔁 Use Cases

| Use Case                | Kinesis Component                   |
| ----------------------- | ----------------------------------- |
| Real-time log analytics | KDS + Lambda or Firehose            |
| Metrics and monitoring  | KDS + CloudWatch or Analytics       |
| Streaming ETL pipelines | Kinesis Firehose + S3/Redshift      |
| Real-time dashboards    | Kinesis Analytics + QuickSight      |
| Video streaming & ML    | Kinesis Video Streams + Rekognition |

---

## 📦 Feature Comparison

| Feature                    | KDS             | Firehose          | Analytics     | Video Streams   |
| -------------------------- | --------------- | ----------------- | ------------- | --------------- |
| Custom application support | ✅ Yes          | ❌ No             | ✅ (SQL apps) | ❌ (video only) |
| Built-in delivery to AWS   | ❌ No           | ✅ Yes            | ✅ Yes        | ❌ No           |
| Latency                    | Low (ms)        | Near real-time    | Seconds       | Seconds         |
| Data retention             | 24h–365d        | 24h               | 7 days        | 10 years max    |
| Data transformation        | Lambda (custom) | Lambda (built-in) | SQL functions | ❌ No           |

---

## 🔐 Security

- **KMS Encryption** (at rest and in transit)
- IAM policies for access control
- VPC support for private network delivery
- Logging and monitoring with **CloudWatch**

---

## 🧠 Best Practices

- Use **multiple shards** in KDS for higher parallelism
- Enable **compression & buffering** in Firehose to reduce storage cost
- Use **Athena or OpenSearch** for downstream analytics
- Apply **schema validation** before transformation
- Monitor with **CloudWatch metrics** like:
  - `IncomingBytes`, `IncomingRecords`
  - `GetRecords.IteratorAgeMilliseconds`

---

## 📊 Monitoring

| Metric                            | Description                      |
| --------------------------------- | -------------------------------- |
| `PutRecord.Success`               | Successful record put count      |
| `IncomingBytes` / `Records`       | Throughput entering the stream   |
| `IteratorAgeMilliseconds`         | Lag behind latest record         |
| `DeliveryToS3.Records` (Firehose) | Records delivered to destination |

---

## 🛠️ Getting Started

1. **Create a Stream** (KDS or Firehose) via AWS Console or CLI
2. **Write data** using AWS SDK, CLI, or API
3. **Set up consumer**:
   - KDS → Lambda / KCL
   - Firehose → Destination (S3, Redshift, OpenSearch)
   - Analytics → SQL App
4. **Monitor** the stream with CloudWatch

---

## 💡 Example: Put Record into Kinesis Stream (CLI)

```bash
aws kinesis put-record \
  --stream-name my-data-stream \
  --partition-key user123 \
  --data "SGVsbG8gV29ybGQ="  # (base64 encoded)

```

## 📚 References

Kinesis Data Streams

Kinesis Firehose

Kinesis Data Analytics

Kinesis Video Streams

## Summary

| Component            | Purpose                          | Real-Time | Serverless | Destinations                  |
| -------------------- | -------------------------------- | --------- | ---------- | ----------------------------- |
| Kinesis Data Streams | Custom real-time data processing | ✅ Yes    | ❌ No      | Custom consumers (Lambda etc) |
| Kinesis Firehose     | Load data to AWS services        | ✅ Near   | ✅ Yes     | S3, Redshift, OpenSearch      |
| Kinesis Analytics    | SQL processing of streams        | ✅ Yes    | ✅ Yes     | S3, Firehose, Redshift        |
| Kinesis Video        | Video/audio stream ingestion     | ✅ Yes    | ✅ Yes     | Rekognition, ML, playback     |
