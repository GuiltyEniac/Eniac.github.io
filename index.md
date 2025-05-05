---
layout: Eniac Portfolio
---


[Link to another page](https://freightr.app/).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Cybersecurity Skills Portfolio

Welcome to my cybersecurity skills portfolio. Here you'll find demonstrations, code samples, and explanations of a wide range of cyber skills, from ethical hacking to secure coding and digital forensics.

## Penetration Testing

> Penetration testing (pentesting) is the practice of simulating cyberattacks to identify vulnerabilities in systems and applications.
>
> "The best defense is a good offense."

### Example: Simple Port Scanner in Python

```python
import socket

target = '127.0.0.1'
for port in range(20, 1024):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.settimeout(0.5)
    result = s.connect_ex((target, port))
    if result == 0:
        print(f"Port {port} is open")
    s.close()
```

### Example: SQL Injection Test

```sql
SELECT * FROM users WHERE username = 'admin' --' AND password = 'password';
```

#### Common Pentesting Tools

*   Nmap
*   Metasploit
*   Burp Suite
*   Wireshark

##### Pentesting Process

1.  Reconnaissance
2.  Scanning
3.  Exploitation
4.  Post-Exploitation
5.  Reporting

###### Example Vulnerability Table

| Vulnerability   | Severity | Description                |
|:---------------|:--------:|:---------------------------|
| SQL Injection  | High     | User input not sanitized   |
| XSS            | Medium   | Reflected script injection |
| Open Port      | Low      | Unnecessary service open   |

### ---

### Secure Coding Practices

*   Input validation
*   Output encoding
*   Principle of least privilege
*   Use of secure libraries

### Example: Password Hashing in Python

```python
import bcrypt

password = b"supersecret"
hashed = bcrypt.hashpw(password, bcrypt.gensalt())
print(hashed)
```

### Secure Coding Checklist

1.  Sanitize all user inputs
2.  Use parameterized queries
3.  Avoid hardcoded secrets
4.  Implement proper error handling

### Nested List: Secure Development Lifecycle

- Requirements
  - Security requirements
  - Compliance requirements
    - GDPR
    - HIPAA
- Design
  - Threat modeling
  - Secure architecture
- Implementation
  - Code reviews
  - Static analysis
- Testing
  - Dynamic analysis
  - Penetration testing
- Deployment
  - Secure configuration
  - Monitoring

### Small image

![Cybersecurity](https://upload.wikimedia.org/wikipedia/commons/4/4a/Cyber_Security_Malware.png)

### Large image

![Network Defense](https://www.csoonline.com/wp-content/uploads/2023/10/cybersecurity_network_security_shutterstock_1937225139-100876367-orig.jpg)

### Digital Forensics

<dl>
<dt>Definition</dt>
<dd>Digital forensics is the process of uncovering and interpreting electronic data.</dd>
<dt>Tools</dt>
<dd>Autopsy, FTK, EnCase</dd>
<dt>Process</dt>
<dd>Acquisition, Analysis, Reporting</dd>
</dl>

```
# Example: Extracting metadata from a file using exiftool
exiftool suspicious.jpg
```

```
# Example: Hashing a file for integrity
sha256sum important.docx
```

### Cybersecurity Certifications

* CompTIA Security+
* Certified Ethical Hacker (CEH)
* Offensive Security Certified Professional (OSCP)
* GIAC Security Essentials (GSEC)

### The final element: Stay curious, keep learning, and always practice ethical hacking!

