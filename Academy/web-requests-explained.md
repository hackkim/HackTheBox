# 📚 HTTP and HTTPS Fundamentals

> This document summarizes core HTTP/HTTPS concepts based on personal studies at Hack The Box Academy.

---

## 🌐 HyperText Transfer Protocol (HTTP)

Today, most applications constantly interact with the internet. HTTP is an **application-layer protocol** used to access World Wide Web (WWW) resources.

- **Hypertext**: Text containing links to other resources
- **HTTP Communication**:
  - Client sends request
  - Server processes and responds
- **Default Port**: `80`
- We use Fully Qualified Domain Names (FQDN) and URLs (Uniform Resource Locator) to reach websites.

### 🧩 URL Structure
| Component | Example | Description |
|:--|:--|:--|
| Scheme | `http://`, `https://` | Protocol used |
| User Info | `admin:password@` | Optional credentials |
| Host | `inlanefreight.com` | Resource location |
| Port | `:80` | Network port (default `80` or `443`) |
| Path | `/dashboard.php` | Specific resource path |
| Query String | `?login=true` | Parameters and values |
| Fragment | `#status` | Section inside resource |

Only `Scheme` and `Host` are mandatory.

---

## 🔄 HTTP Flow

When you enter a URL:
1. Browser queries DNS → gets IP
2. Sends HTTP GET request to server
3. Server returns response (e.g., `index.html`)

**Key Status Code**: `200 OK`

> ℹ️ Browsers first check `/etc/hosts` file before DNS lookup.

---

## ⚡ Using cURL

- Send requests from command line
- Supports multiple protocols (HTTP, HTTPS, FTP, etc.)

```bash
curl inlanefreight.com
curl -O inlanefreight.com/index.html
curl -s -O inlanefreight.com/index.html
curl -h  # View help
```

**Silent mode** with `-s`, **Save output** with `-O` or `-o filename`.

---

## 🔐 Hypertext Transfer Protocol Secure (HTTPS)

- Solves HTTP security issues by encrypting traffic
- Prevents **Man-in-the-Middle (MITM)** attacks
- Default Port: `443`
- SSL/TLS handshake establishes secure channel

### 🚨 HTTPS Downgrade Attack
Modern browsers protect against downgrade attacks from HTTPS → HTTP.

---

## 🌍 HTTP Requests and Responses

- **Request**: Sent by client
- **Response**: Sent by server

### 🛠️ Request Structure
```text
GET /users/login.html HTTP/1.1
Host: inlanefreight.com
User-Agent: curl/7.65.3
Accept: */*
```

### 🛠️ Response Structure
```text
HTTP/1.1 200 OK
Content-Type: text/html
Date: ...
<html>...</html>
```

Use `curl -v` to view full request/response exchange.

---

## 📑 HTTP Headers

| Header Type | Example | Purpose |
|:--|:--|:--|
| General | `Date: ...`, `Connection: close` | Message metadata |
| Entity | `Content-Type: text/html` | About content |
| Request | `User-Agent: curl/7.77.0` | Client info |
| Response | `Server: Apache/2.4.14` | Server info |
| Security | `Strict-Transport-Security: ...` | Enforce HTTPS |

Use `curl -I` to view only response headers.

---

## 🔄 HTTP Methods

| Method | Purpose |
|:--|:--|
| GET | Retrieve resources |
| POST | Submit data to server |
| PUT | Replace resource |
| PATCH | Partially modify resource |
| DELETE | Remove resource |
| HEAD | Retrieve headers only |
| OPTIONS | Supported methods info |

Use browser DevTools or cURL to observe methods.

---

## ⚙️ HTTP Response Codes

| Code | Meaning |
|:--|:--|
| 1xx | Informational |
| 2xx | Success |
| 3xx | Redirection |
| 4xx | Client Error |
| 5xx | Server Error |

Example:
- `200 OK`: Successful request
- `404 Not Found`: Resource missing
- `500 Internal Server Error`: Server crashed

---

## 🛡️ HTTP Basic Authentication

Protects resources with simple username/password:
```bash
curl -u admin:admin http://target_ip:port/
```

Authorization header:
```
Authorization: Basic base64(user:pass)
```

---

## 🗂️ Working with GET and POST

- **GET**: Parameters in URL
- **POST**: Parameters in request body

Example POST with cURL:
```bash
curl -X POST -d 'username=admin&password=admin' http://target_ip:port/
```

---

## 🛠️ Cookies in Authentication

Store session ID in cookies after login:
```bash
curl -b 'PHPSESSID=sessionid' http://target_ip:port/
```

Can also be injected manually via browser DevTools.

---

## 📦 JSON Data Handling

- `Content-Type: application/json`
- Used for APIs
- Send JSON with POST:
```bash
curl -X POST -H "Content-Type: application/json" -d '{"search":"london"}' http://target_ip:port/search.php
```

---

## 🧹 CRUD API (Create, Read, Update, Delete)

**Typical API interactions:**

| Operation | HTTP Method | Action |
|:--|:--|:--|
| Create | POST | Add entry |
| Read | GET | Retrieve entry |
| Update | PUT | Modify entry |
| Delete | DELETE | Remove entry |

Example update:
```bash
curl -X PUT -H "Content-Type: application/json" -d '{"city_name":"NewCity"}' http://target_ip:port/api.php/city/london
```

---

# 🚀 End of HTTP/HTTPS Fundamentals Summary

