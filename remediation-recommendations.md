# Remediation Recommendations (with secure code examples)

## 1. SQL injection: use parameterized queries
```python
# Unsafe: user input is joined into the query
query = "SELECT * FROM users WHERE email = '" + email + "'"

# Safe: parameterized query
cursor.execute("SELECT * FROM users WHERE email = %s", (email,))
```

## 2. Cross-Site Scripting: encode output and use CSP
```python
# Use the template engine's auto-escaping (Jinja2 example)
{{ comment }}          # escaped automatically
```
```
Content-Security-Policy: default-src 'self'; script-src 'self'
```

## 3. Passwords: hash with bcrypt
```python
import bcrypt
hashed = bcrypt.hashpw(password.encode(), bcrypt.gensalt())
bcrypt.checkpw(password.encode(), hashed)
```

## 4. Sessions and cookies
```
Set-Cookie: session=<random>; HttpOnly; Secure; SameSite=Lax; Path=/
```
Regenerate the session ID after login and expire sessions after inactivity.

## 5. Broken access control: check on the server
```python
order = get_order(order_id)
if order.owner_id != current_user.id:
    abort(403)
```
Deny by default and never rely on hidden fields or URLs.

## 6. Error handling
```python
try:
    process()
except Exception:
    log.exception("processing failed")      # details only in private logs
    return "Something went wrong", 500       # generic message for users
```

## 7. Security headers
```
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
Content-Security-Policy: default-src 'self'
```

## 8. Other recommendations
- Enforce MFA and rate limiting on login.
- Keep libraries updated and scan dependencies.
- Log failed logins and access denials, and monitor alerts.
