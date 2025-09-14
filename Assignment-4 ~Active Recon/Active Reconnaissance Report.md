**Active Reconnaissance Report**



Target: zero.webappsecurity.com



1\. Host Discovery Results



The initial reconnaissance phase confirmed that the target host, `zero.webappsecurity.com`, is live and responding.



IP Address: `54.82.22.214`

Status: Host is up.



This was verified using a simple Nmap ping scan.





&nbsp;2. Nmap Outputs



Multiple Nmap scans were performed to gather detailed information about the target's network services.



TCP SYN Scan: The first scan quickly identified three open ports.

Full Port Scan: A comprehensive scan of all 65,535 TCP ports confirmed that only the previously identified ports were open.

OS Detection: Nmap's OS detection was inconclusive, but it suggested the target is likely running a virtual machine environment (guesses included Oracle Virtualbox and QEMU with high confidence).





3\. Open Ports \& Services with Version Info



The Nmap scans identified the following open ports and their associated services and versions:



Port 80/tcp:

&nbsp; State: open

&nbsp; Service: http

&nbsp; Version: Apache Tomcat/Coyote JSP engine 1.1

Port 443/tcp:

&nbsp; State: open

&nbsp; Service: ssl/http

&nbsp; Version: Apache httpd 2.2.6 ((Win32) mod\_ssl/2.2.6 OpenSSL/0.9.8e mod\_jk/1.2.40)

Port 8080/tcp:

&nbsp; State: open

&nbsp; Service: http

&nbsp; Version: Apache Tomcat/Coyote JSP engine 1.1





4\. NSE Scripts Used and Findings



Nmap Scripting Engine (NSE) scripts were used to perform further enumeration and vulnerability checks.



http-methods: This script was run on ports 80 and 443 and revealed that potentially risky HTTP methods such as `PUT`, `DELETE`, and `TRACE` are enabled on both web servers. The presence of these methods could allow for file creation, deletion, or information disclosure.

ssl-cert: This script was run on port 443. It extracted the SSL certificate details, including the common name `zero.webappsecurity.com` and the organization `Micro Focus LLC`. It also confirmed that the server supports SSLv2, which is an outdated and insecure protocol.





5\. HTTP Enumeration Results (dirb output)



The Dirb tool was used to brute-force common directories and files on the web server using both the HTTPS and HTTP protocols.



HTTPS Scan: The scan found 11 directories and files. The most notable findings were the `index.html` page (which returned a 200 OK) and several others that returned a 403 Forbidden status, including `/admin` and `/cgi-bin`.

HTTP Scan: A similar scan on the HTTP protocol also found 11 entries. Many of these resulted in a `302 Found` redirect, likely to the HTTPS version of the site. A significant finding was the `/server-status` page, which returned a `200 OK` response, indicating it is accessible and could reveal internal server information.





6\. Web Fingerprinting (whatweb, nikto)



Web fingerprinting tools provided high-level and detailed information about the web application.



whatweb:

&nbsp;   \* Confirmed the server as Apache-Coyote/1.1.

&nbsp;   \* Identified frontend technologies as Bootstrap and jQuery (version 1.8.2).

&nbsp;   \* Extracted the page title: "Zero - Personal Banking - Loans - Credit Cards".

&nbsp;   \* Noted a missing `X-UA-Compatible` header.



nikto:

&nbsp;   \* Confirmed the `Apache-Coyote/1.1` and `Apache/2.2.6` server versions.

&nbsp;   \* Reported a number of potentially risky HTTP methods including `PUT`, `DELETE`, `TRACE`, and `PATCH`.

&nbsp;   \* Indicated the absence of security headers like `X-Frame-Options` and `X-Content-Type-Options`, which could make the site vulnerable to attacks like Clickjacking.

&nbsp;   \* Verified the information leakage from the `/server-status` page.

&nbsp;   \* Discovered several key directories and files, including:

&nbsp;   \* `/admin/` and `/admin/index.html` (Admin login page).

&nbsp;   \* `/login.html` (Login page).

&nbsp;   \* `/manager/html` and `/manager/status` (Default Tomcat Manager interfaces, which often use weak credentials).

&nbsp;   \* A test for `/wp-config.php.php` was performed, but the file was not found, indicating the site is not running WordPress.

