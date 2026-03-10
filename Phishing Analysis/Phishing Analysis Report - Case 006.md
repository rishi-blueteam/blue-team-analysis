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



- **Type of phishing:** {{Type of Phishing}}

- **Intent (Credential Harvesting / Malware Delivery / Redirect / BEC):** {{Intent Behind the Mail}}

- **Key Indicators:** {{Key Indicators supporting the intent}}

- **Risk Severity (Low / Medium / High / Critical):** {{Risk Severity}}



**Summary:**



> {{Write 5–8 line professional summary of findings}}



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



---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details



- **Sender IP (Defanged):** 96.57.102.59

- **Originating IP:** 96[.]57[.]102[.]59

- **ASN Information:** AS6128 CABLE-NET-1 - Cablevision Systems Corp., US (registered Nov 30, -0001) 

- **Resolved Host:** ool-6039663b.static.optonline.net 

- **Geo Location:** United States

![Tool 1 IP Analysis]()

![Tool 2 IP Analysis]()

### Email Authentication Results



- **SPF:** Pass

- **DKIM:** Missing

- **DMARC:** Not Found



### Domain Comparison



- **Message-ID Domain:** VS2.dasco.local

- **From Domain:** dascosupply.com

- **Mismatch Detected:** Partial



**Header Observations:**



> {{Describe spoofing indicators, authentication failures, suspicious routing}}



---



## 5. Infrastructure Analysis



### Sender IP Analysis

#### IP-1 Analysis

- **IP-1 Found:** 192.168.4.33 (Assigned by Internet Assigned Number Authority)



- **IP-2 Found:** 192.1.1.2 

- **ASN:** AS1856 DISN-PILOTNET2 - RTX BBN Technologies, Inc., US (registered May 27, 1992) 

- **ISP:** N/A
 
- **Hosting Type (Cloud / VPS / Residential):** N/A

- **Reputation Check Result:** 0/94 Threat score (Virus Total)

![IP2_Virus Total Reputation Check]()

> Domain Tools Identifies there is a domain that uses the IP

![Reverse IP To find Domain]()

- **Abuse Reports:** N/A


### Domain Analysis



- **Domain Name:** dbyi[.]cn

- **Registrar:** Not Found

- **Creation Date:** 2014-05-03 00:44:51

- **Domain Age:** 12 Years
 
- **Name Servers:** ns3.dns.com

- **Reputation:** Not Found



**Infrastructure Assessment:**



> {{Describe legitimacy or malicious indicators}}



---



## 6. URL Analysis (None)


**Analysis:**



> {{Explain purpose and malicious indicators}}



---



## 7. Attachment Analysis - Present



- **Attachment Name:** document8961294[.]scr

- **File Type (Actual):** Iniial Zip ( Inside contents: Win32 EXE )

- **File Size:** 24.0 KiB (24,576 bytes)

![File Details]()

- **MD5:** 1d38c362198ad67329fdf58b4743165e

- **SHA1:** 9faac97f5d9b8f6885592d530229d42e49ef564c

- **SHA256:** 5387585bc905f6304b190493af158a714bdd0baed1be7e81db40407d4a92af01

- **VirusTotal Detection Ratio:** 65/71

- **Contains Embedded URLs:** Yes

![Embedded URL Contacted]()

- **Threat Categories:** trojan, Downloader, upatre, smnf, waski 


![Virus Total Hash Values and Threat Score]()

**Graph Summary** 

![Graph Summary]()

**Crowd Strike Rules Triggerd**

![CrowdStrike Rules]()


**Behavioral Observations:**



> {{Describe payload, embedded scripts, execution behavior}}


![Behavioral Pattern for Analysis]()

---



## 8. Social Engineering Indicators



- **Urgency Language:** {{Urgency Language:}}
- **Fear Tactics:** {{Fear Tactics:}}
- **Brand Impersonation:** {{Brand Impersonation:}}
- **Grammar / Formatting Issues:** {{Grammar / Formatting Issues:}}
- **Domain Impersonation:** {{Domain Impersonation:}}
- **Homoglyph Indicators:** {{Homoglyph Indicators:}}



**Assessment:**



> {{Explain how the attacker manipulates the recipient}}



---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | {{Suspicious / Malicious / Clean}}   |
| Attachment         | {{Malicious / Suspicious / None}}  |
| Authentication     | {{Failed / Partial / Passed}}   |
| Social Engineering | {{High / Moderate / Low}}   |
| **Overall**        | **{{Low / Medium / High / Critical}}** |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- {{IP}}

- {{IP}}



### Domains (Defanged)

- {{Domain}}



### URLs (Defanged)

- {{URL}}



### File Hashes

- MD5:

- SHA1:

- SHA256:



### Email Addresses

- {{Sender}}

- {{Reply-To}}



---



## 11. Final Verdict



> {{Clearly state whether email is malicious, suspicious, or benign and justify technically}}



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

- Reset user credentials (if clicked)

- Monitor for follow-up attempts



### Communicate

- Notify affected users

- Share awareness advisory



---



## 13. Tools Used



- {{VirusTotal}}

- {{WHOIS Lookup}}

- {{Any Sandbox}}

- {{Custom Email Analyzer Tool}}



---



## 14. Evidence & Screenshots



### Email Screenshot

![Original Email]()



### URL Page Screenshot

N/A


### Attachment Preview

![aTTACHMENT pREVIEW]()


---



**Analyst Signature:**  

RS



---



