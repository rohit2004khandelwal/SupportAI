# 🚀 SupportAI

> A SaaS-ready embeddable AI customer support platform built with **Next.js, TypeScript, Scalekit, MongoDB, and Vercel**.

SupportAI enables businesses to integrate an intelligent chatbot into their websites using a simple script tag while maintaining secure authentication, session handling, and scalable backend architecture.

---

## 🌟 Key Highlights

- 🔐 Secure OAuth authentication using Scalekit
- 🍪 HTTP-only cookie-based session management
- 🧠 AI-powered chatbot backend
- 📦 Embeddable widget via script tag
- 🏗 Full-stack architecture using Next.js App Router
- 🗄 MongoDB integration for persistent storage
- ⚡ Deployed on Vercel (Serverless + Edge-ready)
- 🔒 Production-ready authentication flow

---

## 🏗 Architecture Overview

```
User
  ↓
Login Route (/api/auth/login)
  ↓
Redirect to Scalekit
  ↓
Scalekit returns Authorization Code
  ↓
Callback Route (/api/auth/callback)
  ↓
Code exchanged for session token
  ↓
Session stored in HTTP-only cookie
  ↓
Protected Dashboard
  ↓
Embed Script Generated
  ↓
Client Website loads chatbot.js
```

---

## 🛠 Tech Stack

| Technology | Role |
|------------|------|
| **Next.js (App Router)** | Full-stack framework |
| **TypeScript** | Type-safe development |
| **Scalekit** | OAuth authentication & session management |
| **MongoDB** | Database |
| **Vercel** | Deployment & hosting |
| **REST API Routes** | Backend business logic |
| **Secure Cookies** | Session persistence |

---

## 🔐 Authentication Flow (OAuth Code Flow)

SupportAI implements a secure OAuth Authorization Code flow:

1. User initiates login
2. Redirected to Scalekit authentication
3. Scalekit returns an authorization code
4. Backend exchanges code for session token
5. Token stored in HTTP-only cookie
6. Middleware validates session on protected routes

### Why this approach?

- No token exposure in frontend
- Secure session lifecycle management
- Prevents XSS token theft
- Production-grade auth architecture

---

## 📦 Embeddable Chatbot Integration

After authentication, users can embed the chatbot into any website using:

```html
<script src="https://yourdomain.com/chatbot.js" data-org-id="ORG_ID"></script>
```

The script dynamically injects the chatbot UI without interfering with the host website’s styles.

---

## 📂 Project Structure

```
src/
 ├── app/
 │    ├── api/
 │    │    ├── auth/
 │    │    │    ├── login/route.ts
 │    │    │    ├── callback/route.ts
 │    │    ├── chatbot/
 │    ├── dashboard/
 │    ├── layout.tsx
 │    ├── page.tsx
 │
 ├── components/
 │    ├── HomeClient.tsx
 │    ├── DashboardClient.tsx
 │    ├── EmbedClient.tsx
 │
 ├── lib/
 │    ├── scalekit.ts
 │
 ├── model/
 ├── types/
 
public/
 ├── chatbot.js
```

---

## 🚀 Local Development Setup

### 1️⃣ Clone Repository

```bash
git clone https://github.com/yourusername/SupportAI.git
cd SupportAI
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Setup Environment Variables

Create `.env.local` in the root directory:

```env
SCALEKIT_ENVIRONMENT_URL=your_scalekit_environment_url
SCALEKIT_CLIENT_ID=your_client_id
SCALEKIT_CLIENT_SECRET=your_client_secret
NEXT_PUBLIC_APP_URL=http://localhost:3000
MONGODB_URL=your_mongodb_connection_string
GEMINI_API_KEY=your_ai_api_key
```

### 4️⃣ Run Development Server

```bash
npm run dev
```

---

## 🛡 Security Best Practices Implemented

- HTTP-only cookies
- Secure flag in production
- Environment variables excluded from Git
- Server-side token exchange
- Middleware route protection
- Session expiration policies

---

## 🌍 Deployment

SupportAI is deployed on **Vercel**, enabling:

- Serverless API routes
- Edge-optimized frontend
- Production environment variable management

---

---

## 📄 License

This project is built for educational and portfolio purposes.
