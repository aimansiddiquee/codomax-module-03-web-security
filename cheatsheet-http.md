# HTTP Cheat Sheet

| Method | Purpose |
|---|---|
| GET | Read data |
| POST | Send data (login, forms) |
| PUT / PATCH | Update data |
| DELETE | Delete data |

| Status | Meaning |
|---|---|
| 200 | OK |
| 301 / 302 | Redirect |
| 400 | Bad request |
| 401 | Not authenticated |
| 403 | Not authorized |
| 404 | Not found |
| 500 | Server error |

| Security header | Purpose |
|---|---|
| Content-Security-Policy | Limits where scripts and content can load from |
| Strict-Transport-Security | Forces HTTPS |
| X-Content-Type-Options: nosniff | Stops MIME sniffing |
| X-Frame-Options | Prevents clickjacking |
| Set-Cookie flags | HttpOnly, Secure, SameSite |
