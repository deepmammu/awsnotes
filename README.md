# 🔐 Amazon Cognito Integration Guide

## Overview

**Amazon Cognito** is a fully managed authentication and user management service from AWS. It enables you to add user sign-up, sign-in, and access control to web and mobile apps quickly and securely.

---

## 🧠 What Is Amazon Cognito?

Amazon Cognito provides:

- **User authentication** and **authorization**
- **User directory management**
- **Secure token-based access**
- Integration with **third-party identity providers** (Google, Facebook, Apple, SAML)
- **Scalable authentication for millions of users**

---

## 🛠️ Core Components

### 1. **User Pools**

A **user directory** used to manage sign-up and sign-in functionality. It handles user registration, account recovery, and authentication.

### 2. **Identity Pools (Federated Identities)**

Used to **authorize access to AWS services** by granting temporary AWS credentials to authenticated (or guest) users.

---

## 🚀 Use Cases

| Use Case                       | Cognito Feature             |
| ------------------------------ | --------------------------- |
| User Sign-up/Login             | User Pools                  |
| Federated Social Login         | Identity Pools + User Pools |
| Anonymous Guest Access         | Identity Pools              |
| Secure REST API Access         | JWT Access Tokens           |
| Mobile App Auth (iOS/Android)  | AWS Mobile SDK              |
| Access AWS Services (S3, etc.) | Identity Pools + IAM Roles  |

---

## 🔐 Token Types (User Pools)

| Token Type        | Description                                           |
| ----------------- | ----------------------------------------------------- |
| **ID Token**      | Contains user identity info (name, email, etc.)       |
| **Access Token**  | Authorizes access to APIs (with user groups/roles)    |
| **Refresh Token** | Used to get new ID and access tokens when they expire |

Tokens are **JWTs (JSON Web Tokens)** and can be verified using AWS’s public keys.

---

## 🤝 Integration Options

| Platform/Framework    | Integration Tool/Library                     |
| --------------------- | -------------------------------------------- |
| React / Vue / Angular | [AWS Amplify](https://docs.amplify.aws/)     |
| Node.js               | `amazon-cognito-identity-js`, JWT middleware |
| Python (Flask/Django) | JWT decoding libraries + Cognito JWTs        |
| Android / iOS         | AWS Mobile SDK                               |
| API Gateway / Lambda  | Cognito Authorizers                          |

---

## 🧾 Example: Sign In User (JavaScript - Amplify)

```js
import { Auth } from "aws-amplify";

Auth.signIn("username", "password")
  .then((user) => console.log("Logged in:", user))
  .catch((error) => console.error("Login error:", error));
```
