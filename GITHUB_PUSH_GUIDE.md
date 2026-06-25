# Personal GitHub Push & Resume Guide (DO NOT PUSH TO GITHUB)

> **Note**: This file is listed in `.gitignore` and is kept locally for your reference only.

---

## 1. Target Resume Details (ATS Optimized & Human-Style)

### Recommended Repository Name
`c-https-web-server`

### GitHub Repository Short Description (For GitHub About Section)
`A simple HTTPS web server written in C using POSIX sockets and OpenSSL for TLS encryption, static file serving, and JSON API handling.`

### Resume Title & Subtitle
**POSIX HTTPS Web Server in C** | *C, Socket Programming, OpenSSL, TLS/SSL, HTTP Protocols*

### Human & ATS-Friendly Resume Bullet Points
- Built an HTTPS web server in C using POSIX socket programming and OpenSSL for secure TLS communication.
- Configured OpenSSL contexts and handshakes (`SSL_accept`, `SSL_read`, `SSL_write`) to encrypt client-server traffic.
- Implemented HTTP request parsing and URL percentage-decoding to serve static web assets and JSON API endpoints.
- Handled network socket creation, binding, listening, and resource cleanup upon client disconnections.

---

## 2. Recommended 5-Step Commit History (June 2026 Timeline)

To make your repository look naturally built step-by-step, run these 5 commits in sequence.

### Commit 1: Initial socket header setup and main file
- **Date**: June 05, 2026 (`2026-06-05T11:00:00`)
- **Message**: `initial socket server setup`

**Git Bash / Linux:**
```bash
git add simple_http_server.h main.c
GIT_AUTHOR_DATE="2026-06-05T11:00:00" GIT_COMMITTER_DATE="2026-06-05T11:00:00" git commit -m "initial socket server setup"
```

**PowerShell:**
```powershell
git add simple_http_server.h main.c
$env:GIT_AUTHOR_DATE="2026-06-05T11:00:00"; $env:GIT_COMMITTER_DATE="2026-06-05T11:00:00"; git commit -m "initial socket server setup"
```

---

### Commit 2: Add OpenSSL support and request handling logic
- **Date**: June 10, 2026 (`2026-06-10T15:20:00`)
- **Message**: `add openssl support and request handling`

**Git Bash / Linux:**
```bash
git add https_server.c
GIT_AUTHOR_DATE="2026-06-10T15:20:00" GIT_COMMITTER_DATE="2026-06-10T15:20:00" git commit -m "add openssl support and request handling"
```

**PowerShell:**
```powershell
git add https_server.c
$env:GIT_AUTHOR_DATE="2026-06-10T15:20:00"; $env:GIT_COMMITTER_DATE="2026-06-10T15:20:00"; git commit -m "add openssl support and request handling"
```

---

### Commit 3: Add HTML frontend templates
- **Date**: June 16, 2026 (`2026-06-16T12:00:00`)
- **Message**: `add static html pages`

**Git Bash / Linux:**
```bash
git add index.html about.html
GIT_AUTHOR_DATE="2026-06-16T12:00:00" GIT_COMMITTER_DATE="2026-06-16T12:00:00" git commit -m "add static html pages"
```

**PowerShell:**
```powershell
git add index.html about.html
$env:GIT_AUTHOR_DATE="2026-06-16T12:00:00"; $env:GIT_COMMITTER_DATE="2026-06-16T12:00:00"; git commit -m "add static html pages"
```

---

### Commit 4: Add CSS styling and JavaScript interactions
- **Date**: June 21, 2026 (`2026-06-21T17:30:00`)
- **Message**: `add css styling and js script`

**Git Bash / Linux:**
```bash
git add styles.css script.js
GIT_AUTHOR_DATE="2026-06-21T17:30:00" GIT_COMMITTER_DATE="2026-06-21T17:30:00" git commit -m "add css styling and js script"
```

**PowerShell:**
```powershell
git add styles.css script.js
$env:GIT_AUTHOR_DATE="2026-06-21T17:30:00"; $env:GIT_COMMITTER_DATE="2026-06-21T17:30:00"; git commit -m "add css styling and js script"
```

---

### Commit 5: Add documentation and gitignore configuration
- **Date**: June 25, 2026 (`2026-06-25T14:10:00`)
- **Message**: `update readme and gitignore`

**Git Bash / Linux:**
```bash
git add README.md .gitignore
GIT_AUTHOR_DATE="2026-06-25T14:10:00" GIT_COMMITTER_DATE="2026-06-25T14:10:00" git commit -m "update readme and gitignore"
```

**PowerShell:**
```powershell
git add README.md .gitignore
$env:GIT_AUTHOR_DATE="2026-06-25T14:10:00"; $env:GIT_COMMITTER_DATE="2026-06-25T14:10:00"; git commit -m "update readme and gitignore"
```

---

## 3. Steps to Push to GitHub

1. Create a public repository named `c-https-web-server` on GitHub.
2. Set the GitHub Repository Description to:
   `A simple HTTPS web server written in C using POSIX sockets and OpenSSL for TLS encryption, static file serving, and JSON API handling.`
3. Initialize git locally in the folder (if not already done):
   ```bash
   git init
   ```
4. Run Commits 1 through 5 above in order.
5. Push to GitHub:
   ```bash
   git remote add origin https://github.com/<your-username>/c-https-web-server.git
   git branch -M main
   git push -u origin main
   ```
