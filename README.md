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


###Assignment 3:Burp Suite Configuration and Traffic Analysis

This project demonstrates the process of configuring Burp Suite for web traffic analysis, a key skill in web application security testing. The setup involves integrating Burp Suite with a browser, managing SSL certificates, and defining a clear scope for analysis to ensure efficient and focused testing.
Key Steps:
1.Proxy Configuration: Traffic from the browser is routed through Burp Suite by configuring a proxy. The browser (using an extension like FoxyProxy) is set to send all requests to 127.0.0.1:8080, where Burp Suite's proxy listener is active.
2.SSL Certificate Installation: To intercept and decrypt HTTPS traffic, Burp Suite's self-signed Certificate Authority (CA) certificate is exported and then imported into the browser's trust store. This allows Burp Suite to act as a man-in-the-middle for secure connections without triggering browser security warnings.
3.Defining the Target Scope: A specific target domain (e.g., youtube.com) is added to Burp Suite's scope. This is a crucial step that tells Burp Suite to focus its logging and analysis on a single application, filtering out all other web traffic and reducing noise.
4.Traffic Capture and Analysis: Once configured, Burp Suite captures all in-scope HTTP and HTTPS requests and responses. The traffic can then be viewed in a structured format, allowing for detailed inspection of individual requests, identification of potential vulnerabilities, and mapping of the application's attack surface.