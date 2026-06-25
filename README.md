# Simple HTTPS Web Server in C

A basic HTTPS web server written in C using standard POSIX network sockets and the OpenSSL library. It listens for web requests, establishes secure TLS/SSL encrypted connections, serves static files (HTML, CSS, JavaScript), handles API requests, and processes web form submissions.

The project demonstrates low-level networking in C, socket programming, OpenSSL integration, and simple HTTP request parsing.

---

## How It Works

The server listens on a TCP port, wraps accepted client connections using OpenSSL, and returns HTTP responses based on the requested URL path.

```mermaid
sequenceDiagram
    autonumber
    actor Client as Browser / Client
    participant Socket as POSIX Socket
    participant SSL as OpenSSL Engine
    participant Server as Request Handler

    Client->>Socket: Connect to Port 4433
    Socket->>SSL: Initiate SSL_accept Handshake
    Client<->>SSL: Perform Secure TLS Handshake
    Client->>SSL: Send HTTP Request
    SSL->>Server: Decrypt Request Data (SSL_read)
    
    alt GET /users
        Server-->>SSL: Return JSON user list
    else POST /feedback
        Server-->>SSL: Parse form data & return HTML response
    else GET / (Static Files)
        Server-->>SSL: Read & return HTML/CSS/JS file
    else Unknown Route
        Server-->>SSL: Return 404 Not Found HTML page
    end

    SSL-->>Client: Encrypted HTTP Response (SSL_write)
```

---

## What It Can Do

- Secure HTTPS Support: Uses OpenSSL to encrypt connections with TLS/SSL protocol.
- Socket Programming: Implemented using BSD socket calls (`socket`, `bind`, `listen`, `accept`).
- Static File Serving: Delivers HTML pages, CSS stylesheets, and JavaScript files to browsers.
- Simple JSON API: Returns mock user data in JSON format at the `/users` endpoint.
- Web Form Handling: Receives feedback submissions at `POST /feedback` and decodes URL percentage-encoded text.

---

## Project Files

- `https_server.c`: Main server code for SSL setup, socket listening, request parsing, and routing.
- `simple_http_server.h`: Header file with constants and function declarations.
- `index.html` & `about.html`: Static web page templates.
- `styles.css` & `script.js`: Frontend styles and client-side scripts.

---

## How to Build and Run

### Requirements
- GCC (or any C compiler)
- OpenSSL libraries (`libssl-dev` on Linux)
- POSIX-compliant OS (Linux, macOS, or WSL)

### 1. Install Dependencies (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install build-essential libssl-dev
```

### 2. Generate SSL Certificate and Key
Generate a self-signed certificate and private key for local testing:
```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout server.key -out server.crt
```

### 3. Compile
Compile using GCC and link the OpenSSL and pthread libraries:
```bash
gcc -o https_server https_server.c -lssl -lcrypto -lpthread
```

### 4. Run the Server
Run the binary:
```bash
./https_server
```

By default, the server listens on port 4433. You can test it by opening a browser and navigating to:
- Website: `https://localhost:4433`
- API Route: `https://localhost:4433/users`

*(Note: Since the SSL certificate is self-signed for local testing, your browser will display a certificate warning. You can safely bypass it to view the page.)*

---

## Current Limitations

- Basic Thread Model: Processes incoming connections sequentially on blocking sockets without a thread pool or async event loops (`epoll`).
- Simple HTTP Parser: Handles basic `GET` and `POST` requests, but does not support HTTP `Keep-Alive`, chunked transfers, or dynamic request headers.
- Fixed Routes: Routes and responses are coded directly into the server logic rather than being served dynamically from a router configuration.
