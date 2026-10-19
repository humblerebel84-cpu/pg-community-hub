# Persona Guardian — Community Hub 🛡️

Official hub for the **Persona Guardian Android Community Dogfooding Program** — an on-device privacy engine that eliminates cross-app tracking, ad-broker correlation, and hardware fingerprinting without a remote proxy.

---

## 📥 Download (Official Source)

**Canonical download:** https://pg-api-111313389599.asia-south1.run.app/download

| Property | Value |
| :--- | :--- |
| Version | 0.1.0 (versionCode 1) — Android 8.0+ (API 26) |
| Size | 32,397,641 bytes (30.90 MB) |
| SHA-256 | `ADCFB4E41A6279725A935EE92C87457C6454A44A74244CEDC41FF0FDF5C7E331` |
| Signing | Release keystore `CN=Persona Guardian` |

**Verify before installing:**
- Windows: `certutil -hashfile PersonaGuardian-v0.1.0-dogfood.apk SHA256`
- macOS / Linux: `shasum -a 256 PersonaGuardian-v0.1.0-dogfood.apk`

Full checksum record: [checksums.txt](checksums.txt)

---

## 🧪 Real-World Dogfooding (30+ Days on Developer's Phone)

Before opening this public beta, I ran Persona Guardian 24/7 on my personal daily-driver Android device (a physical Xiaomi/Redmi phone) for over a month — from **mid-September through mid-October 2026**.

Nobody should install a privacy tool or network filter unless the developer lives with it first. Here is the verified reality of what happened:

* **Real Usage:** Over **500,000+ live network queries** inspected across 30+ continuous days.
* **On-Device Audit Trail:** Generated over **250 MB of raw, cryptographic SQLite ledgers** directly on the phone.
* **Everyday Apps Tested (Nothing Broke):**
  * *Messaging & Social:* WhatsApp, WhatsApp Business, Telegram, Instagram, Messenger.
  * *Food Delivery:* Zomato, Swiggy, Blinkit.
  * *Shopping & Commerce:* Meesho, Myntra, Flipkart.
  * *Financial & Trading:* HDFC SKY, PhonePe, banking & UPI apps.
  * *Utilities:* Truecaller, NoBroker.
  Legitimate traffic was never broken, and connections switched smoothly between Wi-Fi and 4G/5G with zero drops.
* **Trackers Intercepted & Stalled in Background:**
  * *CleverTap & MoEngage:* Relentless telemetry pings fired by delivery and utility apps.
  * *AppsFlyer:* Cross-app attribution trackers attempting to profile installs and clicks.
  * *InMobi & Moloco:* Background ad-exchange profiling beacons.
  * *Google Play Services:* Non-stop telemetry calls to `app-measurement.com`.
  * *OEM Telemetry:* Xiaomi system ad servers (`api.ad.intl.xiaomi.com`).
* **Performance:** Packet inspection took <1ms with zero cloud relay and negligible battery impact once OEM background settings were configured.

---

## 📖 Dogfooding Guide

Everything you need — install steps, battery-optimization setup per OEM (Xiaomi / Samsung / OnePlus), persona vault usage, and the feedback process — is in **[COMMUNITY_DOGFOODING_GUIDE.md](COMMUNITY_DOGFOODING_GUIDE.md)**.

---

## 🔐 Privacy Model (What Leaves Your Phone)

- **Your traffic is inspected on-device** in a TUN network interface and released directly to your Wi-Fi or mobile network. It **never traverses our infrastructure** — there is no remote proxy and no VPN exit server.
- **No browsing data, ledger contents, or CSV exports are ever uploaded.** The CSV export exists strictly for you to audit on your own device — we explicitly do not want it.
- **The one deliberate exception:** the opt-in honeytoken tripwire. If a planted canary credential is used on the web, a canary-event alert (never your browsing activity) reaches our alert feed so the app can warn you instantly.
- **Tracker blocklist:** versioned, public, and independently auditable at [pg-blocklists](https://github.com/humblerebel84-cpu/pg-blocklists) (currently v5 — 906 domains). Devices sync it directly over HTTPS every 24 hours.

---

## 🤝 How to Help & Give Feedback

We welcome all community observations:
1. **Broken apps?** Tell us the app name and what happened.
2. **Tracker slipping through?** Share the domain name.
3. **Battery & stability** observations over 24h of continuous protection.
4. **General feedback & ledger screenshots:**

* **Bug Reports & Issues:** [Open a GitHub Issue](https://github.com/humblerebel84-cpu/pg-community-hub/issues)
* **Community Discussions:** [Join GitHub Discussions](https://github.com/humblerebel84-cpu/pg-community-hub/discussions)
* **Confidential Email:** `humblerebel84@gmail.com` — Subject: `[Dogfood Feedback] <Your Phone Model>`

---

## ⚖️ Beta Software License & Disclaimer

By downloading and participating in the Persona Guardian Community Dogfooding program, you acknowledge and agree to the following:

1. **Pre-Release Software ("AS-IS"):** Persona Guardian beta builds are provided strictly on an "AS-IS" and "AS-AVAILABLE" basis for evaluation, testing, and feedback purposes. The developer makes no warranties, express or implied, regarding performance, stability, or uninterrupted operation.
2. **Limitation of Liability:** The developer shall not be held liable for any temporary connection interruptions, third-party app incompatibilities, or data loss arising from the use of this pre-release software.
3. **Privacy & Data Ownership:** Persona Guardian inspects network traffic entirely on your device — your browsing data never traverses our infrastructure. The sole exception is the opt-in honeytoken tripwire: if a planted canary credential is used on the web, a canary-event alert (never your browsing activity) reaches our alert feed so the app can warn you. Exported CSV ledgers generated on your device belong exclusively to you.
4. **Official Sources Only:** Download the APK only from the official beta portal (or this repository's verified release) and verify the published SHA-256 checksum before installing. Binaries obtained from any other source may have been tampered with.
5. **Proprietary Rights:** Persona Guardian and its underlying core engine are proprietary software protected by applicable copyright laws. You are granted a personal, revocable, non-exclusive license to test the beta application. Decompiling, reverse-engineering, or redistributing the binaries for commercial resale is strictly prohibited.

© 2026 Persona Guardian. All rights reserved.
