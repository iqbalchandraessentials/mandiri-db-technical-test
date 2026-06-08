<p align="center">
  <img src="diagram/ERD.png" width="1000">
</p>

# Mandiri DB Technical Test

## Overview

Technical Test untuk perancangan aplikasi Pinjaman Online (Fintech Lending Platform) menggunakan pendekatan **Microservices Architecture**.

Dokumen ini mencakup:

* High Level Architecture
* Screen Flow Design
* Entity Relationship Diagram (ERD)
* API Design
* UML Sequence Diagram
* Flowchart Business Process
* Mobile App Screen Behavior

---

## Business Requirements

Aplikasi memungkinkan pengguna untuk:

* Registrasi menggunakan email dan nomor telepon
* Verifikasi OTP
* Upload KTP dan Selfie untuk proses KYC
* Login menggunakan Password atau Biometric
* Mengajukan pinjaman hingga Rp12.000.000
* Melihat status pengajuan pinjaman
* Melihat sisa hutang dan tagihan
* Melakukan pembayaran cicilan
* Menerima notifikasi Email, SMS, dan Push Notification

---

# Architecture Design

## Technology Stack

| Layer             | Technology                           |
| ----------------- | ------------------------------------ |
| Mobile App        | Flutter                              |
| API Gateway       | Kong Gateway / Spring Cloud Gateway  |
| Backend Service   | Spring Boot                          |
| Database          | PostgreSQL                           |
| Cache             | Redis                                |
| Message Broker    | RabbitMQ                             |
| Authentication    | JWT                                  |
| Password Security | BCrypt                               |
| Notification      | Email, SMS, Firebase Cloud Messaging |
| KYC Verification  | OCR, Face Recognition, SLIK OJK      |

---

# Entity Relationship Diagram (ERD)

<p align="center">
  <img src="diagram/ERD.png" width="1000">
</p>

---

# Screen Flow

## Authentication & Registration Flow

<p align="center">
  <img src="diagram/Screen Flow Authentication & Registration Flow.png" width="700">
</p>

## Loan Application Flow

<p align="center">
  <img src="diagram/Screen Flow oan Application Flow.png" width="700">
</p>

## Payment Flow

<p align="center">
  <img src="diagram/Screen Flow Payment Flow.png" width="700">
</p>

## User Navigation Flow

<p align="center">
  <img src="diagram/Screen Flow User Navigation Flow.png" width="700">
</p>

---

# UML Sequence Diagram

## Registrasi dan KYC

<p align="center">
  <img src="diagram/UML Sequence Diagram Registrasi & KYC.png" width="1000">
</p>

## Pengajuan Pinjaman

<p align="center">
  <img src="diagram/UML Sequence Diagram Pengajuan Pinjaman.png" width="1000">
</p>

## Approval Pinjaman

<p align="center">
  <img src="diagram/UML Sequence Diagram Approval Pinjaman.png" width="1000">
</p>

## Pembayaran Cicilan

<p align="center">
  <img src="diagram/UML Sequence Diagram Pembayaran Cicilan.png" width="1000">
</p>

---

# Flowchart

## Validasi Pengajuan Pinjaman

<p align="center">
  <img src="diagram/Flowchart Validasi Pengajuan Pinjaman.png" width="700">
</p>

## Logika Pembayaran

<p align="center">
  <img src="diagram/Flowchart Logika Pembayaran.png" width="700">
</p>

---

# Sample API Design

## Register User

```http
POST /api/v1/auth/register
```

Request:

```json
{
  "email": "user@mail.com",
  "phoneNumber": "08123456789",
  "password": "Password123"
}
```

Response:

```json
{
  "userId": "USR001",
  "status": "REGISTERED",
  "message": "OTP berhasil dikirim"
}
```

---

## Verify OTP

```http
POST /api/v1/auth/verify-otp
```

Response:

```json
{
  "status": "VERIFIED"
}
```

---

## Loan Simulation

```http
POST /api/v1/loans/simulation
```

---

## Submit Loan Application

```http
POST /api/v1/loans
```

---

## Payment Installment

```http
POST /api/v1/payments
```

---

# Security Design

* HTTPS TLS 1.3
* JWT Authentication
* BCrypt Password Hashing
* OTP Verification
* Redis OTP Storage
* Redis JWT Blacklist
* Device Fingerprinting
* OCR Validation
* Face Recognition
* SLIK OJK Validation
* Rate Limiting menggunakan Redis
* Idempotency Key untuk transaksi pembayaran
* Audit Logging

---

# Architecture Principles

* Microservices Architecture
* Security by Design
* ACID Transaction
* Event Driven Architecture
* Strong Consistency
* High Availability
* Scalability
* Maintainability
* Fault Isolation
* Fraud Prevention First Approach

---

# Full Documentation

Dokumen lengkap dapat dilihat pada file:

```text
docs/Technical test Mandiri DB.pdf
```
