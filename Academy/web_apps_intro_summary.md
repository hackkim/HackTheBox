# 🛡️ Using Web Proxies for Web Application Penetration Testing

## 📌 Introduction

Modern web and mobile applications rely on constant communication with back-end servers to exchange and process data. This makes **Web Proxies** an essential tool for penetration testers, as they allow interception, modification, and analysis of HTTP requests and responses.

---

## 🔍 What is a Web Proxy?

A **Web Proxy** is a man-in-the-middle (MITM) tool that intercepts traffic between a browser or mobile app and the server. Unlike general network sniffers like Wireshark, web proxies focus on HTTP/HTTPS (ports 80/443) and allow detailed inspection and modification of web traffic.

**Common Features:**
- Capture and replay HTTP(S) requests
- Modify and intercept requests/responses
- Web crawling, fuzzing, scanning
- Request analysis and mapping

---

## 🛠️ Popular Web Proxy Tools

### 1. Burp Suite
- GUI-friendly and widely used
- Available in Community (free) and Pro (paid) editions
- Community version includes most core features
- Built-in Chromium browser for testing

### 2. OWASP ZAP (Zed Attack Proxy)
- Free, open-source alternative to Burp
- No feature restrictions
- Ideal for community use or learning

---

## 🧰 Setting Up Burp & ZAP

Both tools run on Windows, macOS, and Linux, and are pre-installed in Kali/Parrot or HTB PwnBox.

**Launch Burp:**
```bash
java -jar burpsuite.jar
```

**Launch ZAP:**
```bash
java -jar zaproxy.jar
```

---

## 🌐 Proxy Configuration

### 📦 Pre-configured Browsers
- Burp: Proxy > Intercept > Open Browser
- ZAP: Top-right Firefox icon

### 🦊 Using Firefox + FoxyProxy
1. Add `127.0.0.1` and port `8080`
2. Install Burp/ZAP CA certificates
3. Enable proxy through the extension

---

## ✋ Intercepting Web Requests

### Burp
- Enable at Proxy > Intercept > Intercept is on
- Forward/Drop requests manually

### ZAP
- Toggle interception [CTRL+B]
- Use HUD for in-browser control

---

## 🧪 Modifying Requests/Responses

- Test for SQLi, XSS, Command Injection, etc.
- Change parameters, headers, or body
- Automate changes with “Match & Replace” (Burp) or “Replacer” (ZAP)

---

## 🔁 Repeating Requests

### Burp Repeater
- Right-click > Send to Repeater
- Modify and resend requests

### ZAP Request Editor
- Right-click > Resend
- Modify and view live responses

---

## 🔐 Encoding & Decoding

Supported encodings:
- URL, Base64, HTML, Hex, Unicode

### Tools:
- Burp: Decoder tab or Inspector
- ZAP: Encoder/Decoder/Hash ([CTRL+E])

---

## ⚙️ Proxying Other Tools

### proxychains (Linux)
```bash
sudo nano /etc/proxychains.conf
# Add:
http 127.0.0.1 8080
```

### Tools:
- `curl`, `nmap --proxies`, Metasploit `set PROXIES`

---

## 🚀 Burp Intruder & ZAP Fuzzer

### Burp Intruder
- Brute-force, fuzz directories, inject parameters
- Free version is throttled (1 req/sec)

### ZAP Fuzzer
- Unlimited speed
- Built-in wordlists via Marketplace

---

## 🔍 Web Scanners

### Burp Scanner (Pro only)
- Crawl and Audit for vulnerabilities
- Passive and Active scanning
- Generates comprehensive reports

### ZAP Scanner
- Spider for site map generation
- Passive + Active scanners
- Export reports (HTML, XML, Markdown)

---

## 🧩 Extensions

### Burp:
- BApp Store (Extender tab)
- Examples: J2EEScan, Retire.js, ActiveScan++

### ZAP:
- Marketplace (Manage Add-ons)
- Examples: FuzzDB, OS Command Injection lists

---

## ✅ Final Thoughts

Web Proxies like **Burp Suite** and **OWASP ZAP** are essential tools for penetration testers. Mastering their features enables efficient, deep analysis of web applications.

> Practice on HTB Academy and HTB Labs to reinforce these skills!

