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

***

## How To Use

- Clone the repo:
  ```
  git clone https://github.com/Rahulgandham/SkillHorizon-Internship.git
  ```
- Navigate to assignment folders and follow the scripts/usage instructions in each.
- Install recommended tools via apt, go, or pip as per tool documentation.
- Only use authorized or in-scope domains for all reconnaissance tasks.

***

## Prerequisites

- Kali Linux (recommended) or any compatible Linux distribution.
- Basic understanding of Linux CLI and cybersecurity concepts.
- All tools should be installed and updated; see official docs for each.
