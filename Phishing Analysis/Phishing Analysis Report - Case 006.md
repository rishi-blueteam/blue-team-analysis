# Phishing Analysis Report – Case 006



---



## 1. Case Information



- **Case Number:** 006

- **Analyst:** Rishab Shorey

- **Date Reported:** 10-03-2026
- **Date Analyzed:** 10-03-2026

- **Email File Name:** External-Analysis-006

- **Source of Sample:** User Reported / External (Wireshark Case Study)



---



## 2. Executive Summary



Provide a concise overview of the phishing attempt.



- **Type of phishing:** Malware Delivery Phishing (Attachment-Based Phishing)

- **Intent (Credential Harvesting / Malware Delivery / Redirect / BEC):** Malware Delivery. The attacker attempts to trick the recipient into downloading and executing a malicious attachment disguised as a document file.

- **Key Indicators:** Malicious .scr attachment disguised as a document, high VirusTotal detection ratio (65/71), embedded outbound connections to suspicious domains and IPs, executable payload inside a ZIP archive, and malware behavior such as process injection, defense evasion, and command-and-control communication.

- **Risk Severity (Low / Medium / High / Critical):** Critical



**Summary:**



> This email represents a malicious phishing attempt designed to deliver malware through a deceptive attachment. The message contains a ZIP archive that includes a file named document8961294.scr, which masquerades as a legitimate document but is actually a Windows executable. Static and behavioral analysis using VirusTotal shows a high detection rate of 65/71, confirming the presence of known malware families including trojan downloader variants. Behavioral telemetry indicates actions consistent with defense evasion, process injection, and command-and-control communication with multiple external domains and IP addresses. The malware also attempts system discovery activities such as network configuration enumeration and file system discovery. The combination of malicious attachment delivery, suspicious infrastructure, and confirmed malware execution strongly indicates a high-risk phishing campaign targeting victims for system compromise.



---



## 3. Email Metadata Overview



- **From:** John Santoro <john.santoro@dascosupply.com>

- **To:** N/A

- **Reply-To:** N/A

- **Subject:** Your Document

- **Date:** Fri, 06 Feb 2015 17:07:31 +0000

- **Message-ID:** 44a68df889b44f16b20c874a08667e21@VS2.dasco.local

- **Return-Path:** N/A

- **Language Used:** English (ENG)

![Header Meta Data Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Header%20Meta%20Data%20Information.png)

---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details



- **Sender IP (Defanged):** 96.57.102.59

- **Originating IP:** 96[.]57[.]102[.]59

- **ASN Information:** AS6128 CABLE-NET-1 - Cablevision Systems Corp., US (registered Nov 30, -0001) 

- **Resolved Host:** ool-6039663b.static.optonline.net 

- **Geo Location:** United States

![Tool 1 IP Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Tool-1%20Analysis.png)

![Tool 2 IP Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Tool-2%20Analysis.png)

### Email Authentication Results

- **SPF:** Pass

- **DKIM:** Missing

- **DMARC:** Not Found



### Domain Comparison



- **Message-ID Domain:** VS2.dasco.local

- **From Domain:** dascosupply.com

- **Mismatch Detected:** Partial



**Header Observations:**



> The email originates from the IP address 96.57.102.59 associated with a residential ISP rather than a corporate mail server, which is unusual for legitimate business communications. While SPF authentication passed, DKIM was not present and DMARC was not configured, reducing the overall trustworthiness of the message authentication. The Message-ID domain VS2.dasco.local differs from the external sender domain dascosupply.com, indicating partial domain inconsistency and possible internal spoofing or compromised mail infrastructure. The presence of a residential IP address as the sending infrastructure further raises suspicion, as legitimate organizations typically send mail through dedicated corporate mail servers or cloud email services.



---



## 5. Infrastructure Analysis



### Sender IP Analysis

#### IP-1 Analysis

> We found this information of extra IP via the Custom Email Analyzer Tool as seen in the Above Image of the Header Analyzer

- **IP-1 Found:** 192.168.4.33 (Assigned by Internet Assigned Number Authority)
- 
- **IP-2 Found:** 192.1.1.2 

- **ASN:** AS1856 DISN-PILOTNET2 - RTX BBN Technologies, Inc., US (registered May 27, 1992) 

- **ISP:** N/A
 
- **Hosting Type (Cloud / VPS / Residential):** N/A

- **Reputation Check Result:** 0/94 Threat score (Virus Total)

![IP2_Virus Total Reputation Check](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/IP2_Virus%20Total%20Reputation%20Check.png)

> Domain Tools Identifies there is a domain that uses the IP

![IP2_Virus Total Reputation Check](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Reverse%20IP%20To%20find%20Domain.png)
![Reverse IP To find Domain]()

- **Abuse Reports:** N/A


### Domain Analysis



- **Domain Name:** dbyi[.]cn

- **Registrar:** Not Found

- **Creation Date:** 2014-05-03 00:44:51

- **Domain Age:** 12 Years
 
- **Name Servers:** ns3.dns.com

- **Reputation:** Not Found

![Domain Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Domain%20Analysis%20Values.png)

**Infrastructure Assessment:**



> The infrastructure associated with this email exhibits multiple suspicious indicators. The sending IP originates from a residential ISP rather than enterprise mail infrastructure, which is uncommon for legitimate business email communications. Additionally, the investigation identified the domain dbyi.cn, which lacks clear registration information and has limited reputation data, a common trait of domains used in malware campaigns. The use of internal private IP addresses observed in the analysis also suggests the sample was captured within a monitored network environment during malware execution. The lack of reputation information combined with suspicious hosting infrastructure increases the likelihood that the domain and related resources were used for malicious activity.



---



## 6. URL Analysis (None)


**Analysis:**


> No URLs were directly present in the email body; however, the malware attachment contains embedded URLs that are contacted during execution. These URLs are used by the malware to establish command-and-control communication, download additional payloads, or exfiltrate system information. The presence of multiple contacted domains and IP addresses during sandbox analysis confirms that the malware attempts to communicate externally to retrieve instructions or additional malicious components



---



## 7. Attachment Analysis - Present



- **Attachment Name:** document8961294[.]scr

- **File Type (Actual):** Iniial Zip ( Inside contents: Win32 EXE )

- **File Size:** 24.0 KiB (24,576 bytes)

![File Details](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/File%20Details.png)

- **MD5:** 1d38c362198ad67329fdf58b4743165e

- **SHA1:** 9faac97f5d9b8f6885592d530229d42e49ef564c

- **SHA256:** 5387585bc905f6304b190493af158a714bdd0baed1be7e81db40407d4a92af01

- **VirusTotal Detection Ratio:** 65/71

- **Contains Embedded URLs:** Yes

![Embedded URL Contacted](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Embedded%20URL%20Contacted.png)

- **Threat Categories:** trojan, Downloader, upatre, smnf, waski 


![Virus Total Hash Values and Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Virus%20Total%20Hash%20Values%20and%20Threat%20Score.png)

**Graph Summary** 

![Graph Summary](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Graph%20Summary.png)

**Crowd Strike Rules Triggerd**

![CrowdStrike Rules](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/CrowdStrike%20Rules.png)


**Behavioral Observations:**



> The attachment document8961294.scr is a Windows executable disguised as a document file. Upon execution, the malware performs several malicious actions including process injection, system information discovery, and network configuration discovery. Behavioral analysis shows the malware attempts to evade detection through techniques such as obfuscated files and indicator removal. The malware establishes outbound connections to multiple domains and IP addresses, indicating command-and-control activity. Additional behaviors include downloading or interacting with external resources, creating dropped files, and attempting to propagate within the environment.


![Behavioral Pattern for Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Behavioral%20Pattern%20For%20Analysis.png)

---



## 8. Social Engineering Indicators



- **Urgency Language:** Low urgency. The message simply asks the recipient to check the attached document without time pressure.
- **Fear Tactics:** None
- **Brand Impersonation:** Possible impersonation of an employee or representative from dascosupply.com to increase credibility.
- **Grammar / Formatting Issues:** Minimal message content with a vague request ("Please check your document attached") and lack of professional formatting or context, which is common in malware delivery phishing campaigns.
- **Domain Impersonation:** Potential. The sender claims to be from dascosupply.com, but infrastructure indicators and suspicious message routing raise the possibility of domain misuse or compromise.
- **Homoglyph Indicators:** None



**Assessment:**



> The attacker uses a minimalistic email message designed to encourage the recipient to open the attachment out of curiosity or perceived work relevance. By presenting the attachment as a document requiring review, the attacker relies on user curiosity and routine workplace behavior to trigger execution of the malicious file. This technique avoids raising suspicion by keeping the message short and direct while disguising the executable file as a legitimate document.



---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Malacious   |
| Attachment         | Malacious  |
| Authentication     | Failed   |
| Social Engineering | Moderate   |
| **Overall**        | Critical |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- 96[.]57[.]102[.]59

- 192[.]1[.]1[.]2



### Domains (Defanged)

- dbyi[.]cn



### URLs (Defanged)

- hxxp://178[.]47[.]141[.]100:12100/0602us21/machine_name>/41/7/4/



### File Hashes

- **MD5:** 1d38c362198ad67329fdf58b4743165e

- **SHA1:** 9faac97f5d9b8f6885592d530229d42e49ef564c

- **SHA256:** 5387585bc905f6304b190493af158a714bdd0baed1be7e81db40407d4a92af01



### Email Addresses

- **Sender:**  john.santoro@dascosupply.com



---



## 11. Final Verdict



> This email is classified as malicious. The message delivers a disguised executable attachment that is confirmed malware based on a high VirusTotal detection ratio of 65/71. Behavioral analysis reveals malicious activities including process injection, system discovery, defense evasion, and communication with external command-and-control infrastructure. The attachment masquerades as a legitimate document file to deceive the recipient, making this a clear example of a malware delivery phishing attack intended to compromise the victim’s system.



---



## 12. Recommended Defensive Actions (C.E.R.C Framework)



### Contain

- Block sender domain

- Block IP

- Block URL



### Eradicate

- Remove from affected mailboxes

- Purge similar Message-ID emails



### Recover


- Monitor for follow-up attempts



### Communicate

- Notify affected users

- Share awareness advisory



---



## 13. Tools Used



- Virus Total

- WhoisLook
- Reverseiplookup
- Wireshark (Network Analysis)
- Custom Email Analyzer Tool



---



## 14. Evidence & Screenshots



### Email Screenshot

![Original Email](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%206/Original%20Email.png)



### URL Page Screenshot

N/A

---



**Analyst Signature:**  

RS



---




