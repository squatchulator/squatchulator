---
description: 4/10/2023
---

# OWASP Gruyere Lab

1. XSS (Cross-Site Scripting)

* Reflected XSS
  * (NOTE: If using chrome, use `"C:\Documents and Settings\USERNAME\Local Settings\Application Data\Google\Chrome\Application\chrome.exe" --disable-xss-auditor`)
  * To exploit: add `/<script>alert(1)</script>` to the end of the URL.
* Stored XSS
  * To exploit: add `<a onmouseover="alert(1)" href="#">read this!</a>` to a snippet.
* Stored XSS via HTML Attribute
  * To exploit: set profile color to `red' onload='alert(1)' onmouseover='alert(2)`

2. XSRF (Cross-Site Request Forgery)
   * To exploit: add the following to URL - `/deletesnippet?index=0`
3. Information Disclosure by Path Traversal
   * To exploit: try adding `/../secret.txt` to the URL. Most of the time this won't work, so afterwards try `%2f..%2fsecret.txt`
4. Data Tampering by Path Traversal
   * To exploit: Create a new user named `..` or `brie/../..`. Upload a new `secret.txt`. Then visit the URL with `%2fbrie%2f..%2f..%2fsecret.txt`
