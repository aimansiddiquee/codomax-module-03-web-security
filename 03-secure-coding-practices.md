# 3. Secure Coding Practices

1. **Validate input** on the server (type, length, format, allow-lists).
2. **Encode output** according to context (HTML, attribute, JavaScript, URL).
3. **Use parameterized queries** and never build SQL with string concatenation.
4. **Hash passwords** with bcrypt or Argon2 with salt; never store plain text.
5. **Enforce access control on the server**; deny by default; check ownership of every object.
6. **Protect sessions:** random IDs, regenerate after login, cookie flags `HttpOnly`, `Secure`, `SameSite`, timeouts.
7. **Use HTTPS** everywhere and set security headers (Content-Security-Policy, X-Content-Type-Options, Strict-Transport-Security).
8. **Handle errors safely:** log details privately, show generic messages to users, fail closed.
9. **Keep dependencies updated** and scan them for known vulnerabilities.
10. **Log security events** (logins, failures, access denials) and monitor them.
11. **Apply least privilege** to users, services and database accounts.
12. **Review and test code** (code review, SAST/DAST tools such as OWASP ZAP).
