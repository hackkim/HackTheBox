# 🌐 Introduction and Structure of Web Applications

---

## 📌 What is a Web Application?

A **Web Application** is an interactive application that runs in a web browser. It typically follows a client-server architecture, comprising a frontend (user interface) and a backend (server and databases).

Examples include:

- 📧 Gmail (Online email service)
- 🛒 Amazon (Online marketplace)
- 📄 Google Docs (Online document editing)

---

## 🖥️ Web Applications vs Websites

| Aspect           | Websites (Web 1.0)              | Web Applications (Web 2.0)           |
|------------------|---------------------------------|--------------------------------------|
| Form             | Provides static content         | Dynamic and interactive              |
| Real-time        | Not possible                    | Possible                             |
| Examples         | Blogs, corporate sites          | Online marketplaces, social media    |

---

## 💻 Web Applications vs Native Applications

| Aspect      | Web Applications            | Native Applications                |
|-------------|-----------------------------|------------------------------------|
| Installation| Not required (runs in browser)| Required                           |
| Platform    | OS independent              | OS dependent                       |
| Updates     | Immediate from central server| Individual user updates required   |
| Speed       | Comparatively slower        | Faster (deep OS integration)       |

---

## 🛠️ Components of a Web Application

### 1. Front-End

- **HTML:** Defines webpage structure 📄
- **CSS:** Styling and layout 🎨
- **JavaScript:** Handles dynamic functionality ⚙️

### 2. Back-End

- **Server:** Apache, NGINX, IIS 🌍
- **Database:** MySQL, MongoDB 🗃️
- **Framework:** Laravel, Django, Express 🚧

---

## 🔗 Web Application Architecture

Web applications are usually divided into three layers:

| Layer                   | Description                                 |
|-------------------------|---------------------------------------------|
| Presentation Layer 🎯    | Interaction with users (UI/UX)              |
| Application Layer 🚦     | Handles requests and business logic         |
| Data Layer 📊            | Manages data storage (connected to DB)      |

---

## 🚧 Common Web Application Vulnerabilities

| Vulnerability                | Description                               |
|------------------------------|-------------------------------------------|
| Authentication Bypass 🔑      | Unauthorized access through authentication bypass|
| File Upload Vulnerabilities 📂| Allows unvalidated file uploads          |
| Command Injection 💣          | Executes OS commands from unvalidated user inputs|
| SQL Injection 🛠️              | Executes SQL commands from unvalidated user inputs|

---

## 📍 Front-End Security Vulnerabilities

| Vulnerability                   | Description                             |
|---------------------------------|-----------------------------------------|
| Sensitive Data Exposure 🔓       | Exposes passwords, API keys in source code|
| HTML Injection 📛                | Executes HTML code without filtering input|
| Cross-Site Scripting (XSS) 🚨    | Executes user input as JavaScript        |
| Cross-Site Request Forgery (CSRF)🌊| Performs requests using authenticated user privileges|

---

## 🗃️ Database Types

### Relational Databases (SQL)
- MySQL, MSSQL, Oracle
- Efficient management of structured data

### Non-relational Databases (NoSQL)
- MongoDB, Redis, Cassandra
- Handles unstructured data and rapid scalability

---

## 🌐 API Types

| API Type | Description                                  |
|----------|----------------------------------------------|
| REST 🛣️ | Data transmission via URL and HTTP methods (typically JSON)|
| SOAP 📦  | XML-based data transmission; suitable for complex data handling|

---

## ⚠️ CVSS (Common Vulnerability Scoring System)

| Severity         | CVSS Score (v3) |
|------------------|-----------------|
| Low 🟢            | 0.1-3.9         |
| Medium 🟡         | 4.0-6.9         |
| High 🔴           | 7.0-8.9         |
| Critical 🔥       | 9.0-10.0        |

---

## 📚 Next Steps

Deepen your understanding through practical exercises:

1. Install a web server on a VM 💻
2. Create an HTML page 📄
3. Style it using CSS 🎨
4. Add JavaScript functionality ⚙️
5. Build a simple web app 🚀
6. Connect it to a database 🗃️
7. Experiment with APIs 🛠️
8. Test and remediate vulnerabilities 🔧

**Recommended next modules:**

- OWASP Top 10 📖
- SQL Injection Practice 🛠️
- HackTheBox Easy Boxes 🔍

---

## 🚀 References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [HackTheBox](https://www.hackthebox.eu/)

---

✅ **Conclusion:**
Continuous learning and practice are essential for mastering web application security. Use this guide as your foundation and apply it practically to enhance your skills! 🛡️🎯
