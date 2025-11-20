# SkillHorizon-Internship

## Overview
This repository documents tasks and solutions completed during the SkillHorizon Cybersecurity Internship. It contains practical assignments focusing on reconnaissance, subdomain enumeration, and automation using popular security tools and custom scripts on Kali Linux.

## Assignments

***

### Assignment 1: Subdomain Collection with Multiple Tools

**Objective:**  
Collect subdomains for any two target domains using three different tools/scripts.

**Tools Used:**  
- **subfinder**
- **assetfinder**
- **alterx**

**Instructions:**  
- Select any two target domains (approved for ethical testing or part of bug bounty scope).
- Use each of the three tools above to enumerate subdomains for both targets.
- Collect, compare, and document the discovered subdomains.
- Summarize differences or overlaps in results across the tools.

**Reference Example:**  
```
subfinder -d target1.com -o target1_subfinder.txt
assetfinder --subs-only target1.com > target1_assetfinder.txt
alterx -d target1.com -o target1_alterx.txt
# Repeat above commands for target2.com
```
***

### Assignment 2: Passive Reconnaissance Techniques

**Objective:**  
Perform passive reconnaissance and footprinting for a selected web application.

**Tools Explored:**  
- subfinder
- assetfinder
- amass
- anew
- katana
- gau
- waybackurls
- httpx-toolkit
- httprobe
- dalfox
- jsleak
- fuzzuli
- alterx

**Assignment Requirements:**  
- Gather domain registration info using whois, dig, and nslookup.
- Enumerate subdomains using subfinder, assetfinder, amass, and alterx.
- Scan and collect URLs with tools like gau, katana, waybackurls.
- Run OSINT searches with theHarvester, SpiderFoot.
- Extract metadata from public files using exiftool and metagoofil.
- Analyze discovered JavaScript files for secrets using jsleak.
- Summarize findings and document evidence/screenshots for each step.

- All tools should be installed and updated; see official docs for each.



### Assignment 3: Burp Suite Configuration and Traffic Analysis

This project demonstrates the process of configuring Burp Suite for web traffic analysis, a key skill in web application security testing. The setup involves integrating Burp Suite with a browser, managing SSL certificates, and defining a clear scope for analysis to ensure efficient and focused testing.
Key Steps:
   1.Proxy Configuration: Traffic from the browser is routed through Burp Suite by configuring a proxy. The browser (using an extension like FoxyProxy) is set to send all requests to 127.0.0.1:8080, where Burp       Suite's proxy listener is active.

   2.SSL Certificate Installation: To intercept and decrypt HTTPS traffic, Burp Suite's self-signed Certificate Authority (CA) certificate is exported and then imported into the browser's trust store. This           allows Burp Suite to act as a man-in-the-middle for secure connections without triggering browser security warnings.

   3.Defining the Target Scope: A specific target domain (e.g., youtube.com) is added to Burp Suite's scope. This is a crucial step that tells Burp Suite to focus its logging and analysis on a single                 application, filtering out all other web traffic and reducing noise.

   4.Traffic Capture and Analysis: Once configured, Burp Suite captures all in-scope HTTP and HTTPS requests and responses. The traffic can then be viewed in a structured format, allowing for detailed                inspection of individual requests, identification of potential vulnerabilities, and mapping of the application's attack surface.


### Assignment 4: Active Reconnaissance—Web Enumeration

**Objective:**  
Conduct active recon on an approved target to discover live hosts, open ports, services, OS details, and web application directories/files. Use Nmap for scanning, Dirb/Gobuster for brute-forcing directories, and WhatWeb/Nikto for web fingerprinting and basic vulnerability checks.

**Tools Used:**  
- Nmap (staged scans, OS detection)  
- Dirb, Gobuster  
- WhatWeb, Nikto  

**Tasks:**  
- Host discovery and IP identification  
- Port and service scans with increasing depth  
- Directory brute-forcing and fingerprinting  
- Vulnerability checks and professional reporting

### Assignment 5: Automated Vulnerability Scanning

**Objective:**  
Safely scan an approved web application for vulnerabilities using automated scanners. Plan scans, execute light and aggressive checks, interpret outputs, remove false positives, and generate a professional remediation report.

**Tools Used:**  
- Nmap, WhatWeb, Wappalyzer  
- Dirb, Gobuster  
- Nikto, Nuclei, OWASP ZAP  
- WPScan (WordPress-specific)  

**Tasks:**  
- Recon and discovery of live hosts and open ports  
- Fingerprint scanning and directory enumeration  
- Automated vulnerability scans  
- WPScan analysis if applicable

### Assignment 6: DVWA Web Application Vulnerability Discovery

**Objective:**  
Install and attack DVWA (Damn Vulnerable Web Application) on Kali Linux, exploring common vulnerabilities such as XSS (reflected and stored), SQL injection, command injection, CSRF, file inclusion, and insecure file upload.

**Tasks:**  
- DVWA setup and exploitation scenarios  
- Payload crafting for bypassing filters  
- Reverse shell uploads and listener setups  
- Exploiting and documenting multiple vulnerability types  
- Reference to OWASP and industry best practices for remediation and further learning.

  Here is a concise summary for your DVWA Security Level Comparison Project, suitable for inclusion in a GitHub README file:

***

## DVWA Security Level Comparison Project

This project utilizes Damn Vulnerable Web Application (DVWA) to analyze how web security practices evolve across four configurable security levels
—Low, Medium, High, and Impossible
—by testing common vulnerabilities: SQL Injection (SQLi) and Reflected Cross-Site Scripting (XSS).

### Project Goals
- Demonstrate exploitation techniques against insecure coding in DVWA.
- Evaluate defensive strategies and incremental security improvements found in web application security settings.
- Document practical findings, fostering a deeper understanding of secure development for aspiring cybersecurity professionals.

### Tools and Environment
- DVWA hosted on a local VM with Apache and MySQL for safe, offline testing.
- Manual input forms and Burp Suite used for request interception and payload manipulation.

### Tested Vulnerabilities

| Vulnerability         | Description                                                                                  |
|----------------------|----------------------------------------------------------------------------------------------|
| SQL Injection (SQLi) | Injected SQL queries via user input to gain unauthorized access or extract database contents. |
| Reflected XSS        | Injected JavaScript payloads that were reflected and executed in a victim’s browser.         |

### Security Levels Analysis
- **Low:** No defenses; easy exploitation demonstrates real-world coding flaws.
- **Medium:** Basic input validation; still vulnerable to union-based SQLi and filter bypasses.
- **High:** Advanced filtering; mitigates simple payloads and suppresses error messages.
- **Impossible:** Secure against all tested attacks; fully parameterized queries and robust output encoding prevent vulnerabilities

### Key Findings
- Security hardening through successive coding improvements drastically reduces exploitable attack surfaces.
- DVWA’s layered approach mirrors real-life application hardening, providing excellent hands-on training in defensive programming and vulnerability assessment.

### Educational Value
This project shows how defensive strategies thwart common attacks, offering practical experience essential for future cybersecurity experts.

***

## Getting Started

- Assignments are intended for ethical hacking and authorized educational use.
- Install and update all tools in Kali Linux as per official documentation.
- Use safe, lab environments (local VMs, test sites) for all scans and attacks.

## License

Educational purposes only. All activities must follow legal and ethical guidelines.

***
