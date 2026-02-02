# Day-37-100-Days-challenge-in-cybersecurity-
## 🛡️ Day 37: Open Redirect Vulnerability Analysis

### Overview
On Day 37, we analyze the **Open Redirect (Unvalidated Redirects and Forwards)** vulnerability. While often classified as a "low" severity bug, its utility in high-impact phishing campaigns makes it a critical chain in modern social engineering.

### 🛠 The Mechanics
An attacker exploits a vulnerable redirect parameter to mask a malicious destination:
`https://example.com/login?redirect_url=https://attacker-site.net`

### 📋 Attack Lifecycle
1. **Initial Vector:** A phishing email contains a link to a trusted domain.
2. **Server Processing:** The trusted server (vulnerable) receives the request and redirects the user-agent.
3. **Credential Harvesting:** The victim lands on a spoofed page and submits sensitive data.

### 🚀 Prevention Strategies
* **Deny-by-Default:** Avoid using user-provided URLs in redirect functions.
* **Allowlisting:** Maintain a server-side list of approved destinations.
* **URL Mapping:** Use tokens or IDs instead of literal URLs (e.g., `?goto=dashboard` maps to `/internal/dashboard`).
* **Referrer Policy:** Implement strict headers to prevent token leakage during transitions.

> **Key Lesson:** Security is not just about protecting data on your server; it's about protecting the trust your users place in your domain name.
