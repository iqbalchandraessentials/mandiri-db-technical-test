# Mandiri DB Technical Test

## Overview

Technical Test untuk perancangan aplikasi Pinjaman Online (Fintech Lending Platform) menggunakan pendekatan **Microservices Architecture**.

---

## Technology Stack

| Layer              | Technology                                   |
| ------------------ | -------------------------------------------- |
| Mobile Application | Flutter                                      |
| API Gateway        | Kong Gateway / Spring Cloud Gateway          |
| Backend Services   | Spring Boot                                  |
| Database           | PostgreSQL                                   |
| Cache              | Redis                                        |
| Message Broker     | RabbitMQ                                     |
| Authentication     | JWT                                          |
| Notification       | Email, SMS Gateway, Firebase Cloud Messaging |
| KYC                | OCR, Face Recognition, SLIK OJK              |

---

# Entity Relationship Diagram (ERD)

<table>
<tr>
<td bgcolor="white">

<img src="diagram/ERD.png" width="1000">

</td>
</tr>
</table>

---

# Screen Flow

## Authentication & Registration Flow

<table>
<tr>
<td bgcolor="white">

<img src="diagram/Screen Flow Authentication & Registration Flow.png" width="900">

</td>
</tr>
</table>

## Loan Application Flow

<table>
<tr>
<td bgcolor="white">

<img src="diagram/Screen Flow oan Application Flow.png" width="900">

</td>
</tr>
</table>

## Payment Flow

<table>
<tr>
<td bgcolor="white">

<img src="diagram/Screen Flow Payment Flow.png" width="900">

</td>
</tr>
</table>

## User Navigation Flow

<table>
<tr>
<td bgcolor="white">

<img src="diagram/Screen Flow User Navigation Flow.png" width="900">

</td>
</tr>
</table>

---

# UML Sequence Diagram

## Registrasi & KYC

<table>
<tr>
<td bgcolor="white">

<img src="diagram/UML Sequence Diagram Registrasi & KYC.png" width="1000">

</td>
</tr>
</table>

## Pengajuan Pinjaman

<table>
<tr>
<td bgcolor="white">

<img src="diagram/UML Sequence Diagram Pengajuan Pinjaman.png" width="1000">

</td>
</tr>
</table>

## Approval Pinjaman

<table>
<tr>
<td bgcolor="white">

<img src="diagram/UML Sequence Diagram Approval Pinjaman.png" width="1000">

</td>
</tr>
</table>

## Pembayaran Cicilan

<table>
<tr>
<td bgcolor="white">

<img src="diagram/UML Sequence Diagram Pembayaran Cicilan.png" width="1000">

</td>
</tr>
</table>

---

# Flowchart

## Validasi Pengajuan Pinjaman

<table>
<tr>
<td bgcolor="white">

<img src="diagram/Flowchart Validasi Pengajuan Pinjaman.png" width="900">

</td>
</tr>
</table>

## Logika Pembayaran

<table>
<tr>
<td bgcolor="white">

<img src="diagram/Flowchart Logika Pembayaran.png" width="900">

</td>
</tr>
</table>

---

# Sample API

## Register User

```http
POST /api/v1/auth/register
```

Request

```json
{
  "email": "user@mail.com",
  "phoneNumber": "08123456789",
  "password": "Password123"
}
```

Response

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

# Security Architecture

* HTTPS TLS 1.3
* JWT Authentication
* BCrypt Password Hashing
* OTP Verification
* Redis OTP Storage
* Redis JWT Blacklist
* OCR Validation
* Face Recognition
* SLIK OJK Validation
* Device Fingerprinting
* Rate Limiting menggunakan Redis
* Audit Logging
* Idempotency Key

---

# Architecture Principles

* Microservices Architecture
* Security by Design
* ACID Transaction
* Strong Consistency
* Event Driven Architecture
* High Availability
* Scalability
* Maintainability
* Fault Isolation
* Fraud Prevention First

---

# Full Documentation

Dokumen lengkap tersedia pada:

```text
docs/Technical test Mandiri DB.pdf
```
