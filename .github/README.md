Cybersecurity Projects & Tools

Welcome to my cybersecurity repository!

This collection represents years of self-driven learning, adaptability, and growth. My path hasn’t always been straightforward, but every challenge has strengthened my resilience and shaped my commitment to continuous improvement. As I advance in my cybersecurity career, I feel a responsibility to give back—helping others learn faster, avoid common pitfalls, and stay motivated in an ever-evolving field.

My mission: Automate. Educate. Defend.

This repo includes tools, scripts, and resources designed to support offensive security, defensive operations, and cybersecurity education.

## Highlights

Automated Reconnaissance – Fast subdomain and asset discovery tools

Custom Vulnerability Scanners – Scripts for detecting common web and network flaws

Incident Response Playbooks – Practical, step-by-step workflows and automation

Malware Analysis Utilities – Static and dynamic analysis helpers

Defensive Scripts – Log parsing tools, SIEM helpers, hardening resources

CTF Tools & Writeups – Scripts and notes from solving real-world CTF challenges

## Repository Structure
Folder	Description
recon-tools/	Automated reconnaissance & OSINT utilities
vuln-scanners/	Custom vulnerability scanning scripts
incident-response/	Playbooks & automation for IR workflows
malware-analysis/	Static/dynamic analysis tools
defensive-scripts/	Log parsing, SIEM helpers, system hardening
ctf-scripts/	Writeups and challenge scripts

Each subfolder includes its own README.md for more detailed information.

## Systems & Requirements

Python 3.x

Bash (for shell scripts)

Docker (isolated testing environments)

Common security tools used:
nmap, wireshark, tcpdump, yara, curl, jq, etc.

## Usage Example

Example: running a tool inside recon-tools/:

cd recon-tools/subdomain-enum/
pip install -r requirements.txt
python3 subenum.py -d example.com

## Contributing

Pull requests, improvements, and suggestions are always welcome.
If you find a bug or have an idea for a new tool, feel free to open an issue.
