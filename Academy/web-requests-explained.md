> 📚 This document summarizes core HTTP/HTTPS concepts based on personal studies at Hack The Box Academy.


# HTTP and HTTPS Fundamentals

---

## 🌐 What is HTTP?

- **HTTP** (HyperText Transfer Protocol) is an application-layer protocol used to access resources over the World Wide Web (WWW).
- It enables communication between **clients** (e.g., browsers) and **servers**.
- Default port: **80** (can be changed based on server configuration).
- To visit a site like `www.hackthebox.com`, users input a Fully Qualified Domain Name (FQDN) or URL.

---

## 🛣️ URL Structure

A URL consists of several components:

| Component | Example | Description |
|:---|:---|:---|
| Scheme | `http://` or `https://` | Specifies the protocol |
| User Info | `admin:password@` | Optional credentials |
| Host | `inlanefreight.com` | Domain or IP address |
| Port | `:80` | Communication port (default 80 for HTTP, 443 for HTTPS) |
| Path | `/dashboard.php` | Resource location |
| Query String | `?login=true` | Additional parameters |
| Fragment | `#status` | Navigation to a section within the page |

Only the **Scheme** and **Host** are mandatory for making a valid request.

---

## 🔄 HTTP Communication Flow

1. Browser resolves the domain via DNS (checks `/etc/hosts` first).
2. Browser sends an HTTP `GET` request to the server.
3. Server processes the request and responds with an index file (e.g., `index.html`).
4. Browser renders the HTML content for the user.

---

## 🛠️ Introduction to cURL

- **cURL** is a command-line tool to send requests over HTTP and other protocols.
- Unlike browsers, cURL outputs raw HTML without rendering.

Example:
```bash
curl inlanefreight.com
```

Download a file:
```bash
curl -O inlanefreight.com/index.html
```

Silent mode:
```bash
curl -s -O inlanefreight.com/index.html
```

Display cURL options:
```bash
curl -h
```

---

## 🔒 Why HTTPS Matters

- **HTTP** transmits data as plain text (vulnerable to MITM attacks).
- **HTTPS** encrypts communication, protecting sensitive information like login credentials.

Browser indicator for HTTPS:
- URL starts with `https://`
- Lock icon appears in browser address bar

---

## 🛡️ How HTTPS Works

1. Client connects to port 80.
2. Server redirects to port 443 (`301 Moved Permanently`).
3. SSL/TLS handshake occurs (certificate exchange and validation).
4. Encrypted communication begins.
5. Downgrade attacks are blocked by modern browsers and servers.

cURL connecting to an invalid certificate:
```bash
curl https://inlanefreight.com
```

Skip certificate verification:
```bash
curl -k https://inlanefreight.com
```

---

## 📄 HTTP Request and Response

### HTTP Request Format

- Method: e.g., `GET`
- Path: e.g., `/users/login.html`
- Version: e.g., `HTTP/1.1`
- Headers: Host, User-Agent, Accept, etc.
- Body: Optional data payload (e.g., POST request)

### HTTP Response Format

- Status Line: Version + Response Code (e.g., `HTTP/1.1 200 OK`)
- Headers: Server, Set-Cookie, Content-Type, etc.
- Body: HTML, JSON, images, etc.

Verbose cURL example:
```bash
curl -v inlanefreight.com
```

---

## 🧰 Browser Developer Tools

- Open DevTools with `F12` or `Ctrl+Shift+I`.
- **Network Tab** shows all web requests and responses.
- Inspect HTTP methods, status codes, headers, and response bodies.

---

## 📑 HTTP Headers Overview

| Type | Examples | Purpose |
|:---|:---|:---|
| General Headers | `Date`, `Connection` | Describe message metadata |
| Entity Headers | `Content-Type`, `Content-Length` | Describe the resource content |
| Request Headers | `Host`, `User-Agent`, `Accept`, `Authorization` | Provide client-specific data |
| Response Headers | `Server`, `Set-Cookie`, `WWW-Authenticate` | Server context info |
| Security Headers | `Content-Security-Policy`, `Strict-Transport-Security`, `Referrer-Policy` | Enforce browser security policies |

---

## 🚀 Key Takeaways

- HTTP is unencrypted; HTTPS provides secure communication.
- Understanding the structure of HTTP requests/responses is vital for web security.
- Tools like cURL and DevTools are essential for penetration testing and debugging.
- Proper use of HTTP headers enhances communication security and performance.

---

> 🧠 This study note is based on practical exercises from Hack The Box Academy, rewritten for personal learning documentation.



# HTTP Methods and Status Codes

---

## 📩 HTTP Methods

HTTP supports multiple methods that define actions to be performed on resources. These methods inform the server about the intended action for a given request.

Here are the commonly used HTTP methods:

| Method | Description |
|:---|:---|:---|
| GET | Requests a specific resource. Can send additional data via query strings (`?param=value`). |
| POST | Sends data to the server (e.g., form submissions, file uploads). Data is sent in the request body. |
| HEAD | Requests headers for a resource, without the body. Useful for checking metadata like file size before downloading. |
| PUT | Uploads or creates a new resource on the server. |
| DELETE | Deletes an existing resource. Poor configuration can lead to dangerous data removal. |
| OPTIONS | Returns supported HTTP methods for the server or resource. |
| PATCH | Partially modifies a resource. |

> Note: Most web applications primarily use **GET** and **POST**. APIs often use **PUT** and **DELETE** for modifying and deleting data.

---

## 📜 HTTP Status Codes

HTTP status codes indicate the outcome of the request and are grouped into five categories:

| Type | Description |
|:---|:---|:---|
| 1xx | Informational responses (Request received, continuing process). |
| 2xx | Success (The request was successfully received, understood, and accepted). |
| 3xx | Redirection (Further action needs to be taken). |
| 4xx | Client Errors (The request contains bad syntax or cannot be fulfilled). |
| 5xx | Server Errors (The server failed to fulfill a valid request). |

### Common Status Codes

| Code | Meaning | Description |
|:---|:---|:---|
| 200 | OK | Request succeeded; resource is returned. |
| 302 | Found | Temporary redirection to another URL. |
| 400 | Bad Request | Malformed request syntax. |
| 403 | Forbidden | Server understood request but refuses to authorize it. |
| 404 | Not Found | Requested resource does not exist. |
| 500 | Internal Server Error | Server encountered an error processing the request. |

---

## 🔍 Example Requests

GET request with cURL:
```bash
curl http://example.com
```

POST request with cURL:
```bash
curl -X POST -d 'username=admin&password=admin' http://example.com/login
```

Handling cookies with cURL:
```bash
curl -b 'SESSIONID=abcdef123456' http://example.com/profile
```

---

> 🧠 This study note is based on practical exercises from Hack The Box Academy, restructured for personal learning documentation.
