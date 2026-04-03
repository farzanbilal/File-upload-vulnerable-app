# File Upload Vulnerable App

## Vulnerable File Upload Lab
A minimal Flask-based web application intentionally designed with insecure file upload functionality to demonstrate common vulnerabilities such as arbitrary file upload, path traversal, stored XSS, and file overwrite.

---

## Features
- File upload and viewing functionality  
- Intentionally vulnerable design for pentesting practice  

---

## Key Vulnerabilities
- Arbitrary file upload  
- Stored XSS  
- No authentication / access control  
- Unsafe file serving  

---

## Tech Stack
- Python (Flask)  
- HTML, CSS, JavaScript  


## Threat Model
<img width="495" height="368" alt="threatmodel" src="https://github.com/user-attachments/assets/8decb6ff-2c7d-4ed9-8ebe-229c9ee4681a" />
---
## Data flows:
User uploads file → /upload
App stores file → uploads/
File served → /uploads/<filename>
Browser renders it

## S — Spoofing Identity
## Threat:
Anyone can act as a “valid user”
No distinction between attacker and legitimate user
## Impact:
Unlimited abuse of upload functionality
No accountability

## T — Tampering with Data
## Threats:
Path traversal
File overwrite
## Impact:
Application code modification
Backdoor insertion
Data corruption

## R — Repudiation
## Threat:
Attacker uploads malicious file
No way to trace who did it
## Impact:
No forensic visibility
No accountability

## I — Information Disclosure
## Threats:
Guessing file names
Path traversal:
/uploads/../../app.py
## Impact:
Source code leakage
Sensitive file exposure

## D — Denial of Service (DoS)
## Threat:
Upload large files repeatedly
## Impact:
Disk exhaustion
Server slowdown/crash

## E — Elevation of Privilege
## Threat:
Upload malicious file
Trigger execution (XSS or server misconfig)
Gain control
## Impact:
Remote Code Execution (RCE)
Full system compromise

## Vulnerabilities
1. XSS via file upload
<img width="1635" height="507" alt="Capture" src="https://github.com/user-attachments/assets/8f8915f3-4226-47f2-9c76-8be0b7946b28" />
<img width="1312" height="654" alt="2" src="https://github.com/user-attachments/assets/42f85de2-4b72-41b7-b7f0-ee91c877d831" />
2. Path traversal
<img width="1318" height="638" alt="image" src="https://github.com/user-attachments/assets/15241fe6-b6aa-4a54-9fed-d3b9be19a70d" />
3. Arbitrary file upload
<img width="875" height="591" alt="image" src="https://github.com/user-attachments/assets/2a853714-ba79-49f7-a232-4efaecbe3384" />
<img width="565" height="195" alt="image" src="https://github.com/user-attachments/assets/d9d54b51-7c2d-4b1c-9b14-db24b285b9e2" />


