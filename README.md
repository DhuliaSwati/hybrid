
# 🛡️ Hybrid Cloaker Setup (Next.js + SSR + Fingerprint Encryption)

This is a military-grade hybrid cloaker using:

- ✅ Age verification via popup
- ✅ Server-Side Rendering (SSR-only) for redirection
- ✅ Dynamic fingerprint + session ID encryption
- ✅ Serverless redirect API with Vercel support

---

## 🧩 Project Structure

```
pages/
  ├── consent.tsx         # Age verification popup
  ├── checking.tsx        # SSR-only redirect logic (no JS in browser)
  └── api/
      └── [slug].ts       # Encrypted fingerprint-based decision + logging
```

---

## 🚀 Setup Instructions

### 1. Clone this repo and install dependencies

```bash
npm install
```

### 2. Deploy to Vercel

```bash
vercel --prod
```

This will:
- Auto-detect your Next.js project
- Deploy your SSR `/checking` route as a serverless function
- Route `/api/[slug]` dynamically per fingerprint session

---

## 🔐 Stealth Features

- No cloaking logic visible in frontend
- No hardcoded routes, redirections, or labels
- Fingerprint payload is base64-encoded and POSTed invisibly
- Server-only decision logic via Vercel Edge-compatible API

---

## 📦 Payload Tracking

Use `https://your-logging-endpoint.com/log` to store:
- IP
- sessionToken
- User Agent
- Decision (offer/white)
- Timestamp

You can use Supabase, GSheets, or your own Node endpoint.

---

## ✅ Vercel Compatibility

- Fully supports Vercel functions (ESModules)
- Does **NOT** require CommonJS
- `vercel.json` is optional and not included (default routing is used)

---

## 🧠 Author's Note

This setup is designed for scale, stealth, and review-safe compliance.

If you need:
- Country-based flows
- FingerprintJS Pro integration
- Cloaking detection response fallback

Let us know. You're ready for flight 🚀
