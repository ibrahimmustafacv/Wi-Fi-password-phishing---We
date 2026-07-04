# 🔐 Wi-Fi Password Phishing — WE  
### Educational Wireless Security Awareness Tool

<p align="center">
  <img src="https://img.shields.io/badge/status-active-brightgreen" alt="Status"/>
  <img src="https://img.shields.io/badge/platform-Linux%20%7C%20Kali%20%7C%20Parrot-blue" alt="Platform"/>
  <img src="https://img.shields.io/badge/license-MIT-yellow" alt="License"/>
  <img src="https://img.shields.io/badge/developer-Ibrahim%20Mustafa-orange" alt="Developer"/>
  <img src="https://img.shields.io/badge/purpose-educational%20only-critical" alt="Educational Use"/>
</p>

> ⚠️ **هذا المشروع مُصمّم حصرياً للأغراض التعليمية واختبار الاختراق المصرح به وأبحاث الأمن السيبراني. أي استخدام غير قانوني ممنوع منعاً باتاً وقد يُعرّضك للمساءلة القانونية.**  
> **This project is designed exclusively for educational environments, authorized penetration testing and security research. Misuse is strictly prohibited and may be illegal.**

---

## 🧠 About
**Wi-Fi Password Phishing — WE** is a controlled, open-source simulation tool that demonstrates how attackers can trick users into revealing Wi‑Fi passwords through a rogue access point and captive portal. The tool recreates a realistic social engineering attack vector commonly known as an “evil twin” attack, allowing students, network administrators, and cybersecurity professionals to understand, detect, and defend against such threats.

The **“WE”** in the name references both the target brand (We, the Egyptian telecom operator) and **Wireless Exploitation**, reminding us that knowledge can be a weapon or a shield depending on whose hands it falls into.

The repository includes a ready‑to‑use **captive portal page** (see the template below) that mimics a “300 GB free gift” promotion from We, tricking users into submitting their router password along with other personal data.

---

## 🎓 Educational Purpose
This project was built to serve as a **hands‑on lab** for:

- University cybersecurity courses and ethical hacking training.
- Corporate security awareness programs (with explicit written authorization).
- Demonstrating how trivial an evil twin attack can be with common hardware.
- Helping defenders identify indicators of Wi‑Fi phishing attacks.
- Testing the susceptibility of employees or students to social engineering in a safe, legal environment.

**Never use this tool against any network or device without prior, written consent from the owner.**

---

## ✨ Features
- **Evil Twin Access Point Creation** – clones any nearby legitimate Wi‑Fi network.
- **Automated Deauthentication** – politely disconnects real clients (optional) so they see the fake AP.
- **Customisable Captive Portal** – includes a realistic “300 GB gift” page in Arabic (We template) that can be replaced with your own.
- **Password Capture & Logging** – saves submitted credentials in a local, encrypted SQLite database; **never** transmits data to a third party (except for the educational Telegram logging built into the template – see note below).
- **MAC Address Spoofing** – mimics the original BSSID for increased realism.
- **Session Recording** – logs all steps for after‑action debriefing.
- **Headless Mode** – run entirely from the CLI, suitable for automated labs.
- **Dry‑run / Safe Mode** – simulates the infrastructure without injecting any deauthentication packets.
- **Clean Exit** – all wireless interfaces are restored to their original state upon `Ctrl+C`.

---

## ⚙️ How It Works
1. **Scan** – The tool scans the air for nearby Wi‑Fi networks and lets you choose a target.
2. **Clone** – It creates a new access point with the identical SSID and (optionally) the same BSSID using MAC spoofing.
3. **Deauthenticate** – If enabled, it sends deauthentication frames to legitimate clients, forcing them to reconnect.
4. **Captive Portal** – Clients who connect to the rogue AP are shown a realistic login page (see the provided template) requesting the Wi‑Fi password under a pretext (e.g., “Your session has expired – please re‑enter your password to receive your free gift”).
5. **Capture & Report** – Submitted data is stored locally and a summary report is generated for the trainer.

All steps are logged, making it easy to explain the attack flow during a class or training session.

---

## 📁 Project Structure
