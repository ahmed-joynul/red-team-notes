# Web Fundamentals for Attackers

This document covers core web technologies from an **attacker’s perspective**.  
Understanding how the web works is mandatory before exploiting it.

---

## 1. DNS (Domain Name System)

### Concept Learned
DNS translates human-readable domain names into IP addresses so systems can communicate over the internet.

### Why It Matters for Attackers
DNS is often the **first reconnaissance layer**:
- Identifying subdomains
- Mapping infrastructure
- Discovering third-party services

### How It’s Abused in Real Attacks
- Subdomain enumeration to find hidden admin panels
- Misconfigured DNS records leaking internal services
- CNAME records pointing to external services (takeover risks)
- TXT records leaking sensitive metadata (SPF, verification tokens)

### How Defenders Mitigate It
- Proper DNS hygiene
- Removing unused records
- Monitoring for DNS changes
- DNSSEC adoption

---

## 2. HTTP / HTTPS

### Concept Learned
HTTP is the protocol used for communication between clients and web servers. HTTPS adds encryption and server authenticity.

### Why It Matters for Attackers
Every web attack rides on HTTP:
- Requests
- Responses
- Headers
- Cookies
- Status codes

Understanding HTTP enables:
- Authentication bypass
- Session attacks
- Input manipulation

### How It’s Abused in Real Attacks
- Manipulating HTTP methods (GET/POST/PUT/DELETE)
- Abuse of status codes for logic flaws
- Header manipulation
- Cookie tampering
- Insecure HTTPS configurations

### How Defenders Mitigate It
- Strict method handling
- Secure headers
- TLS best practices
- Proper authentication flows

---

## 3. How Websites Work (High-Level)

### Concept Learned
Websites consist of:
- Frontend (HTML, CSS, JavaScript)
- Backend (Server-side logic + databases)

### Why It Matters for Attackers
Security flaws usually occur at:
- Trust boundaries between frontend and backend
- Unsanitized input handling
- Backend logic assumptions

### How It’s Abused in Real Attacks
- Client-side injection (HTML/JS)
- Server-side injection (SQL, command injection)
- Logic flaws in backend workflows

### How Defenders Mitigate It
- Input validation
- Output encoding
- Secure backend frameworks
- Least privilege principles

---

## 4. Supporting Infrastructure

### Load Balancers
- Can reveal internal servers via misconfiguration
- Health-check endpoints may leak information

### CDN
- Can be bypassed to hit origin servers directly
- Misconfigurations can expose real IPs

### WAF
- Signature-based, often bypassable
- Misplaced trust in WAF leads to insecure code

---

## Key Takeaway
Most web vulnerabilities exist **not because of complex exploits**,  
but because developers misunderstand how the web actually works.

Understanding fundamentals is the foundation of all web exploitation.
