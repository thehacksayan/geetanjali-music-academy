<div align="center">

<img src="https://img.shields.io/badge/Geetanjali-Music_Academy-6B21A8?style=for-the-badge&labelColor=3B0764&color=6B21A8" alt="Geetanjali Music Academy" height="40"/>

# 🎵 Geetanjali Music Academy
### Music Learning Platform

*Without Music Life Would Be A Mistake !!*

<br/>

[![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](https://nestjs.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![AWS S3](https://img.shields.io/badge/AWS_S3-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/s3)
[![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)](https://jwt.io)

[![Status](https://img.shields.io/badge/Status-In_Development-A855F7?style=for-the-badge)](.)
[![Platform](https://img.shields.io/badge/Platform-Android_|_iOS-6B21A8?style=for-the-badge)](.)
[![License](https://img.shields.io/badge/License-Private-3B0764?style=for-the-badge)](.)

<br/>

> A secure mobile platform built for **Geetanjali Music Academy** — connecting **ALL INDIA RADIO** musician mentors with their students for notation sharing, live online classes, and academy-wide discussions.

<br/>

</div>

---

## 🏛️ About the Academy

**Geetanjali Music Academy** is a prestigious institution located in **Shibpur, Howrah, West Bengal, India**, founded by **Badrinath Chatterjee**.

The academy is home to **ALL INDIA RADIO musicians** who mentor students across a diverse range of musical traditions — including Mandolin, Guitar, Piano, Tabla, Vocals, and Hawaiian Guitar — spanning Classical, Bengali, Bollywood, and Western genres.

---

## ✨ Features

<table>
<tr>
<td align="center" width="33%">

### 🔐 Secure Onboarding
Phone OTP registration via Firebase, selfie verification, and admin-controlled account approval before any access is granted.

</td>
<td align="center" width="33%">

### 🎼 Notation Sharing
Mentors upload PDF/image lesson materials directly to each student's private library. Students access only their own materials.

</td>
<td align="center" width="33%">

### 📹 Live Video Classes
1-on-1 online classes powered by **Jitsi Meet** (free & open source). Mentor initiates, student receives instant push notification.

</td>
</tr>
<tr>
<td align="center" width="33%">

### 📊 Class Tracking
Mentors view enrolled students with total class count, last session date, and session status at a glance.

</td>
<td align="center" width="33%">

### 📢 Announcements
Admin broadcasts academy-wide announcements that auto-pin to the top of the community feed in real time.

</td>
<td align="center" width="33%">

### 🎬 Tutorials
In-app YouTube feed fetching all videos from the official GMA channel via YouTube Data API v3.

</td>
</tr>
</table>

---

## 👥 User Roles

```
┌─────────────────────────────────────────────────────────────────┐
│                        ROLE HIERARCHY                           │
│                                                                 │
│   👑 Super Admin  →  Full system control                       │
│        ↓                                                        │
│   🛡️  Admin       →  User verification, announcements          │
│        ↓                                                        │
│   👨‍🏫  Mentor      →  Upload notations, host video calls        │
│        ↓                                                        │
│   🎓  Student     →  View materials, join classes              │
│        ↓                                                        │
│   ⏳  Pending     →  Tutorials, About, Community (read-only)   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🔄 Registration Flow

```
📱 Enter Phone Number
        ↓
🔢 OTP Verification  (Firebase Phone Auth)
        ↓
🤳 Upload Selfie
        ↓
⏳ Account PENDING  (Admin Review)
        ↓
✅ Admin Approves  →  Account ACTIVE  →  Role Assigned
        ↓
🏠 Role-based Dashboard
```

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                      Flutter Mobile App                         │
│           (Android + iOS)  •  Dart  •  Riverpod                │
└──────────────────────────┬──────────────────────────────────────┘
                           │ REST API  /api/v1
┌──────────────────────────▼──────────────────────────────────────┐
│                   NestJS Backend  (TypeScript)                   │
│   Controllers → Services → Repositories → Models                │
└────┬──────────┬──────────┬──────────┬──────────┬───────────────┘
     │          │          │          │          │
  🐘 PG     🪣 S3     🔥 Firebase  📹 Jitsi  📺 YouTube
PostgreSQL  AWS S3   Phone Auth   Meet SDK   Data API
             +FCM
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| 📱 Mobile | Flutter + Dart | Cross-platform Android & iOS |
| 🔧 Backend | NestJS + TypeScript | REST API, business logic |
| 🗄️ Database | PostgreSQL + TypeORM | Relational data storage |
| 🪣 Storage | AWS S3 | Notation files + selfies |
| 🔐 Auth OTP | Firebase Phone Auth | SMS OTP — India |
| 🔑 Sessions | JWT | Secure token-based auth |
| 📹 Video | Jitsi Meet | Free open-source 1-on-1 calls |
| 📺 Tutorials | YouTube Data API v3 | GMA channel video feed |
| 🔔 Notifications | Firebase Cloud Messaging | Push notifications |
| 🖥️ Hosting | DigitalOcean | Production server |

---

## 🎨 Design System

<table>
<tr>
<th>Token</th>
<th>Color</th>
<th>Usage</th>
</tr>
<tr><td>primary</td><td>![#6B21A8](https://placehold.co/15x15/6B21A8/6B21A8.png) <code>#6B21A8</code></td><td>Buttons, active nav, headers</td></tr>
<tr><td>primary-light</td><td>![#A855F7](https://placehold.co/15x15/A855F7/A855F7.png) <code>#A855F7</code></td><td>Highlights, icons, badges</td></tr>
<tr><td>primary-dark</td><td>![#3B0764](https://placehold.co/15x15/3B0764/3B0764.png) <code>#3B0764</code></td><td>AppBar, dark backgrounds</td></tr>
<tr><td>accent</td><td>![#DDD6FE](https://placehold.co/15x15/DDD6FE/DDD6FE.png) <code>#DDD6FE</code></td><td>Cards, chips, subtle fills</td></tr>
<tr><td>surface</td><td>![#F5F3FF](https://placehold.co/15x15/F5F3FF/F5F3FF.png) <code>#F5F3FF</code></td><td>Screen backgrounds</td></tr>
</table>

---

## 🗺️ Roadmap

- [x] Authentication & Registration (Phone OTP + Selfie)
- [x] Admin Panel — user verification & management
- [x] Role-based dashboards (Student / Mentor / Admin)
- [x] Notation system — upload & download lesson materials
- [x] Live 1-on-1 video classes (Jitsi Meet)
- [x] Community feed & academy-wide announcements
- [x] In-app YouTube tutorial feed
- [x] Class tracking & session history for mentors
- [ ] Progress reports & performance tracking
- [ ] Fee management & payment integration
- [ ] Push notifications for class reminders
- [ ] UI polish & final brand identity
- [ ] Beta release for enrolled students & mentors
- [ ] Android & iOS app store release

---

## 🔒 Security

- ✅ Students can **never** access other students' data
- ✅ Mentors can **only** access their assigned students
- ✅ Pending users are blocked from all private features
- ✅ All authorization enforced **server-side** — never UI-only
- ✅ File uploads validated for type and size
- ✅ All secrets in environment variables — never hardcoded

---

## 📸 Screenshots

> Coming soon — app is currently in active development.

---

<div align="center">

---

*🎵 Without Music Life Would Be A Mistake !!*

**Thanks to Badrinath Chatterjee — Founder of Geetanjali Music Academy**

<br/>

Built with ❤️ by [Sayan Chatterjee (HackSayan)](https://github.com/thehacksayan)

[![GitHub](https://img.shields.io/badge/GitHub-thehacksayan-6B21A8?style=for-the-badge&logo=github&logoColor=white)](https://github.com/thehacksayan)

</div>
