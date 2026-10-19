# Persona Guardian — Android Community Dogfooding Guide 🛡️

Welcome to the **Persona Guardian Android Beta Dogfooding Program**! This guide outlines how to install, configure, explore identity sandboxing, and share feedback for Persona Guardian on Android (Android 8.0+).

---

## 🎯 Program Objective
Persona Guardian is designed to eliminate cross-app tracking, ad broker correlation, and hardware fingerprinting using an on-device Rust privacy engine and hand-rolled TUN network stack. 

As a dogfood tester, your role is simply to use your everyday apps (social media, streaming, banking, browsing, delivery) to help ensure:
1. Zero connection drops or freezes during network switches (Wi-Fi ↔ 4G/5G).
2. Zero false positives on legitimate services.
3. Genuine blocking of background telemetry and ad-exchange trackers.

Every dogfood tester receives an **automatic 14-day all-access trial** unlocking all premium shields. After 14 days, shields gracefully halt, allowing you to review your cumulative on-device cryptographic audit ledger.

---

## 📥 Installation & Setup

### 1. Download & Install (Android 8.0+)
- Download the release APK directly from the live beta portal on your Android device:  
  👉 **https://pg-api-111313389599.asia-south1.run.app/download**  
  *(Direct binary: `https://pg-api-111313389599.asia-south1.run.app/download/PersonaGuardian-v0.1.0-dogfood.apk`)*
- **File Size:** `32,397,641 bytes` (30.90 MB)
- **SHA-256 Checksum Proof:** `ADCFB4E41A6279725A935EE92C87457C6454A44A74244CEDC41FF0FDF5C7E331`
- **Signing:** Official Release Keystore (`CN=Persona Guardian`, SHA-256 `0f6bf989…`).
- If prompted, allow your browser or file manager to **"Install unknown apps"**.
- If Google Play Protect displays *"Unrecognized developer"*, tap **More details** ➔ **Install anyway** (standard for sideloaded beta builds).
- Tap **Install**.

### 2. First Launch & System Permissions
1. **Onboarding:** Swipe through the initial Persona introduction.
2. **VPN Permission:** When you tap **"Turn On Protection"**, Android will show a system dialogue:
   > *"Persona Guardian wants to set up a VPN connection..."*  
   > ➔ Tap **OK / Allow**.
3. **Notification Permission:** Allow notifications so the app can maintain its persistent status indicator and alert you if a decoy credential tripwire is triggered.

---

## ⚙️ Crucial Device Setup (Prevent Background Killing)

Android manufacturers aggressively terminate background VPN services to conserve battery. To ensure 24/7 continuous protection:

### For Xiaomi / Redmi / POCO (MIUI / HyperOS):
1. When you first tap **"Turn On Protection"**, the app will deep-link directly to **Background settings**.
2. Select **"No restrictions"** (Battery saver doesn't restrict app's activity).
3. In **Settings ➔ Apps ➔ Manage Apps ➔ Persona Guardian**:
   - Enable **Autostart**.
4. Open your App Switcher (Recents), tap and hold Persona Guardian, and tap the **Lock 🔒 icon**.

### For Samsung (OneUI):
1. Go to **Settings ➔ Apps ➔ Persona Guardian ➔ Battery**.
2. Select **"Unrestricted"**.

### For OnePlus / Oppo / Realme (OxygenOS / ColorOS):
1. Go to **Settings ➔ Apps ➔ App management ➔ Persona Guardian ➔ Battery usage**.
2. Enable **"Allow background activity"** and **"Allow auto-launch"**.

---

## 🎭 How to Use the Identity Vault & Sandboxes

The Identity Vault lets you partition apps into isolated digital personas with distinct DNS resolvers, timezones, and blocking profiles.

### 1. Creating a Custom Persona
1. Tap the **Vault** tab in the bottom navigation bar.
2. Tap the **"+ New"** button in the top right.
3. Configure your new persona:
   - **Name & Emoji**: e.g. `🏦 Banking Vault`, `🛍️ Shopping & Social`, `💼 Work Sandbox`.
   - **DNS Resolver**: Select an upstream provider (Cloudflare `1.1.1.1`, Quad9 `9.9.9.9`, AdGuard `94.140.14.14`, Google `8.8.8.8`).
   - **Spoofed Locale / Timezone**: Choose virtual geographic labels for decoy requests.
4. Tap **Save Persona**.

### 2. Assigning Apps to Personas (App Sandboxing)
1. In the **Vault** tab, scroll down to **APP SANDBOXING** (or tap **"App Assignments"**).
2. You will see a list of installed applications on your phone.
3. Tap on any app (e.g. *Amazon, Instagram, Chrome, Swiggy*).
4. Choose the Persona container you want to bind the app to.
5. Once assigned, all traffic originating from that app is tagged with that Persona's profile in the Data Ledger, using its dedicated DNS upstream and privacy rules.

### 3. Switching Active System Personas
- On the **Shield** tab, tap **"Switch"** on the *Operating As* card.
- Select any persona to make it the active default for unassigned apps and system traffic.

---

## 🧪 Exploring Advanced Capabilities

| Feature | Where to Find | What It Does |
| :--- | :--- | :--- |
| **1-Tap Grace Valve** | Shield Tab ➔ **"Relax 15 min"** | If a web page or checkout breaks due to an aggressive ad link, tap *Relax 15 min*. Blocking is paused temporarily, a countdown appears in the notification bar, and protection automatically re-arms fail-closed. |
| **Ultrasonic AudioGuard** | Settings ➔ **AudioGuard** | Passively listens in the 18 kHz–22 kHz near-ultrasound band to detect cross-device retail and TV beacons, without degrading media playback. |
| **Aggressive Tarpitting** | Settings ➔ **Aggressive Tarpitting** | Actively stalls blocked tracker TCP connections for 3,000 ms before dropping them, slowing down data exfiltration pipelines. |
| **Full-Tunnel Mode** | Settings ➔ **Full-Tunnel Mode** | Routes all system IP packets (0.0.0.0/0) through our hand-rolled TUN packet engine and NAT rewriter for TLS SNI packet inspection (DNS-only is the lightweight default). |
| **Honeytoken Canaries** | Audit ➔ **Honeytokens** | View decoy credentials generated on-device. If a shady app steals a planted token and uses it on the web, a high-priority alarm notification fires immediately. |

---

## 📊 Feedback & Reporting (Zero Data Required)

### 🛑 Our Privacy Pledge: We DO NOT Want Your CSV Report or Device Data
* The app features an on-device CSV export feature under the **Audit** tab. **This export exists strictly for YOU** to inspect on your own device in Microsoft Excel or Google Sheets.
* **Please DO NOT send us your CSV report or device logs.** We do not want your personal browsing data, logs, or device history. Your data belongs to you alone.

### 🤝 How You Can Assist Us (Simple & 100% Voluntary):
1. **Broken App Reports:** Did any everyday app (banking, food delivery, shopping, streaming) fail to load or throw an error? Just tell us the **name of the app** and what happened.
2. **Blocklist Suggestions:** Notice an ad or tracking network slipping through? Feel free to share the **domain name** (e.g., `ads.example.com`) so we can add it to the blocklist.
3. **UI / UX & Usability:** Any thoughts on the interface, navigation flow, text readability, or overall design?
4. **Battery & Stability:** How did your device handle battery consumption over a 24-hour period of continuous protection?

### 📬 How to Contact Us:
- **Email:** **`humblerebel84@gmail.com`**
  - **Subject:** `[Dogfood Feedback] <Your Phone Model>`
  - **Body:** Mention your phone model (e.g. *Xiaomi Redmi Note 10, Samsung Galaxy S23*), your Android version, and your observations.

---

## ❓ Encountering Installation or Sideloading Issues?

If you run into any trouble during installation or testing:
1. **"App not installed" / Signature Conflict**:
   - If an earlier development or debug build is installed, uninstall it first: *Settings ➔ Apps ➔ Persona Guardian ➔ Uninstall*. Then install this release APK.
2. **Private DNS Conflict**:
   - If your phone has Android Private DNS enabled (*Settings ➔ Network & Internet ➔ Private DNS* set to a custom provider like `dns.adguard.com`), set it to **"Automatic"** or **"Off"** so Android delegates DNS to Persona Guardian's virtual stack.
3. **Drop Us a Message**:
   - Email: `humblerebel84@gmail.com`
   - We respond to all beta tester inquiries within 24 hours.

---

*Thank you for helping pioneer an un-trackable mobile ecosystem with Persona Guardian!* 🛡️

---

## ⚖️ Beta Software License & Disclaimer

By downloading and participating in the Persona Guardian Community Dogfooding program, you acknowledge and agree to the following:

1. **Pre-Release Software ("AS-IS"):** Persona Guardian beta builds are provided strictly on an "AS-IS" and "AS-AVAILABLE" basis for evaluation, testing, and feedback purposes. The developer makes no warranties, express or implied, regarding performance, stability, or uninterrupted operation.
2. **Limitation of Liability:** The developer shall not be held liable for any temporary connection interruptions, third-party app incompatibilities, or data loss arising from the use of this pre-release software.
3. **Privacy & Data Ownership:** Persona Guardian inspects network traffic entirely on your device — your browsing data never traverses our infrastructure. The sole exception is the opt-in honeytoken tripwire: if a planted canary credential is used on the web, a canary-event alert (never your browsing activity) reaches our alert feed so the app can warn you. Exported CSV ledgers generated on your device belong exclusively to you.
4. **Official Sources Only:** Download the APK only from the official beta portal (or this program's verified release page) and verify the published SHA-256 checksum before installing. Binaries obtained from any other source may have been tampered with.
5. **Proprietary Rights:** Persona Guardian and its underlying core engine are proprietary software protected by applicable copyright laws. You are granted a personal, revocable, non-exclusive license to test the beta application. Decompiling, reverse-engineering, or redistributing the binaries for commercial resale is strictly prohibited.

© 2026 Persona Guardian. All rights reserved.
