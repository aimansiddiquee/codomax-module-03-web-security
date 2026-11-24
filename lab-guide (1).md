# Lab Guide: Secure Web Application Lab

**Sandbox (choose one):** OWASP Juice Shop (public demo or run locally with Docker: `docker run -p 3000:3000 bkimminich/juice-shop`), DVWA, or `testphp.vulnweb.com`.
**Tools:** Web browser with Developer Tools (F12). Optional: OWASP ZAP.

## Task 1: HTTP lifecycle
1. Open the app, press **F12 → Network**.
2. Log in or search, click a request and note: method, URL, status code, request headers, response headers.

## Task 2: Cookies and sessions
1. **F12 → Application → Cookies.** Record each cookie name and its flags (HttpOnly, Secure, SameSite).
2. Note whether the session cookie is properly protected.

## Task 3: Identify
List all pages, forms and input fields, user roles, and technologies used. Optional: run a ZAP **passive** scan and list the alerts.

## Task 4: Test (sandbox only, harmless inputs)
- **Injection / XSS:** type a harmless string such as `<b>test</b>` in a search box and see whether it is displayed as HTML (a sign of missing output encoding).
- **Error handling:** enter a single quote `'` in a field and observe whether detailed errors appear.
- **Broken access control:** with your own test account, check whether changing an ID in a request returns data that is not yours.
- **Authentication:** check whether very weak passwords are accepted.

## Task 5: Fix
For each issue, write the secure fix (see `remediation-recommendations.md`) and explain how you would re-test.

## Task 6: Document
Fill `vulnerability-report.md` with your real results and screenshots.
