# 🔐 CodeAlpha Task 3 – Secure Coding Review

## Overview
For this task, I manually reviewed a sample Python web app to identify security vulnerabilities using OWASP Secure Coding Practices.

## Sample Code Reviewed

```python
@app.route('/login')
def login():
    username = request.args.get('username')
    password = request.args.get('password')
    cursor.execute(f"SELECT * FROM users WHERE username = '{username}' AND password = '{password}'")
Vulnerabilities Found
	•	❗ SQL Injection – User input directly in SQL query
	•	❗ No Input Validation – Username/password not sanitized
	•	❗ Hardcoded DB Path – Not using environment variables
	•	❗ No Error Handling – App can crash or expose details

Recommendations
	•	✅ Use parameterized queries (?)
	•	✅ Sanitize user input
	•	✅ Move DB path to environment variables
	•	✅ Add try-except blocks for errors

Author

Aisha Ibrahim Zakari
CodeAlpha Internship – June 2025
