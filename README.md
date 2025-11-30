AES Encryption Web Application

A full-stack AES visualization and encryption platform built with React, Spring Boot, MySQL, and JWT Authentication.
The application allows users to securely encrypt and decrypt data using multiple AES modes while learning how AES works, and stores encrypted history for visualization purposes.

🚀 Overview

This project is a complete, deployed full-stack cryptography application.
It is designed as both a secure encryption service and an educational tool to help users understand AES block cipher behavior across different modes.

Features include:

    AES-128 / AES-192 / AES-256 support

    CBC, CFB, OFB, CTR block modes

    Full-text encryption and decryption

    User authentication with JWT

    Persistent encryption history

    Clean UI showing algorithm details

    Railway-deployed frontend, backend, and database

🧱 Tech Stack

    Frontend

        React (Vite)

        TypeScript

        Axios (with interceptor for JWT)

        React Router

        CSS modules / custom components

    Backend

        Spring Boot 3+

        Spring Security with JWT

        JPA / Hibernate

        MySQL on Railway

        AES encryption implemented in Java

        RESTful API architecture

    Infrastructure

        Railway hosting (3 services: frontend, backend, MySQL)

        Environment variables for production configs

        HTTPS enforced by Railway’s proxy

        Stateless authentication

🔐 Security & Authentication

    The app uses JWT-based authentication:

    /auth/login & /auth/signup → public

    All AES operations & history → protected

    JWT stored in local storage

    Axios interceptor attaches Authorization: Bearer <token> automatically

    Backend validates JWT via a custom filter (JwtAuthenticationFilter)

    Sensitive information is not stored in history:

        ❌ Keys are not exposed or stored

        ❌ Plaintext is not stored in database

    Only:

        Mode

        Key size

        Ciphertext

        IV / CTR (non-sensitive)

        Timestamp

        User email

📦 Features:

    Encryption

    Choose key size: 128 / 192 / 256 bits

    Choose mode: CBC / CFB / OFB / CTR

    Provide:

        Plaintext

        Hex key

        IV or Counter (depending on mode)

    Generates:

        Ciphertext (hex)

        Block visualization (if enabled)

        Decryption

        Provide ciphertext + parameters

        Obtain plaintext output

        Consistent results with encryption

        History Dashboard

    Shows past operations:

        Mode

        Key size

        Ciphertext

        Timestamp

        Operation type (Encrypt / Decrypt)

        Sensitive fields like key and plaintext are intentionally hidden.

🗂 Project Structure
aes-encryption-app/
│
├── Backend AES
│   ├── controller/     → REST endpoints
│   ├── service/        → AES logic + history
│   ├── security/       → JWT auth, SecurityConfig
│   ├── entity/         → JPA models (EncryptionRecord)
│   ├── dto/            → Request/Response payloads
│   └── repository/     → MySQL persistence
│
└── Frontend AES
    ├── src/
    │   ├── pages/      → Login, Signup, AES views, Dashboard
    │   ├── api/        → axios client + interceptors
    │   ├── components/ → reusable UI components
    │   └── contexts/   → Theme/Auth contexts

☁️ Deployment (Railway)

The app deploys in 3 services:

    1. MySQL Database

    2. Spring Boot Backend

    3. React Frontend

🧪 Testing

Tested manually for:

    Login/signup flows

    Encrypt/decrypt accuracy across all modes

    History filtering & correctness

    JWT validation

    CORS behavior

    Deployment routing between FE → BE → DB

🌟 Why This Project Matters

This is more than a typical CRUD fullstack project.

It demonstrates:

    Secure authentication

    Understanding of cryptographic algorithms

    Full-stack architecture

    State management & UI flows

    Deployment + environment configuration

    API design & separation of concerns
