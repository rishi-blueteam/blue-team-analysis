# Phishing Analysis Report – 010



---



## 1. Case Information



- **Case Number:** 010

- **Analyst:** Rishab Shorey

- **Date Reported:** 13-03-2026 - 12:50 PM  
- **Date Analyzed:** 13-03-2026 - 12:50 PM

- **Email File Name:** Sample-1015.eml

- **Source of Sample:** Github/PhishingPot



---



## 2. Executive Summary



To Provide a concise overview of the phishing attempt.



- **Type of phishing:** {{Type of Phishing}}

- **Intent (Credential Harvesting / Malware Delivery / Redirect / BEC):** {{Intent Behind the Mail}}

- **Key Indicators:** {{Key Indicators supporting the intent}}

- **Risk Severity (Low / Medium / High / Critical):** {{Risk Severity}}



**Summary:**



> {{Write 5–8 line professional summary of findings}}



---



## 3. Email Metadata Overview



- **From:** C o i n b a s e <noreply-coinbasewalletverifiying.irs.mantab@shangriladogchew.com>

- **To:** rodrigo-fp@hotmail.com

- **Reply-To:** N/A

- **Subject:** Important: You phone number has been changed - Case# 83899065

- **Date:** Fri, 28 Jul 2023 21:25:06 +0000

- **Message-ID:** 010b01899e641610-7339abbc-6cab-4df3-8f67-9a50ec1f5fd1-000000@eu-west-2.amazonses.com

- **Return-Path:** 010b01899e641610-7339abbc-6cab-4df3-8f67-9a50ec1f5fd1-000000@eu-west-2.amazonses.com

- **Language Used:** English



---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details



- **Sender IP (Defanged):** 23[.]249[.]218[.]14

- **Originating IP:** 10[.]152[.]29[.]182

- **ASN Information:**  AS16509 AMAZON-02 - Amazon.com, Inc., US (registered May 04, 2000)

- **Resolved Host:** d218-14.smtp-out.eu-west-2.amazonses.com

- **Geo Location:** United Kingdom Croydon Amazon Web Services Inc.


### Email Authentication Results



- **SPF:** Pass

- **DKIM:** Present

- **DMARC:** Pass



### Domain Comparison



- **Message-ID Domain:** amazonses.com

- **From Domain:** shangriladogchew.com

- **Mismatch Detected:** Yes

![Message id domain Threat Score_VirusTotal]()


**Header Observations:**



> {{Describe spoofing indicators, authentication failures, suspicious routing}}



---



## 5. Infrastructure Analysis



### Sender IP Analysis

#### IP-1 Analysis

- **IP-1 Found:** 10[.]152[.]29[.]182


- **IP-2 Found:** 23[.]249[.]218[.]14
- **ASN:** AS16509 AMAZON-02 - Amazon.com, Inc., US (registered May 04, 2000)
- **ISP:**  United Kingdom
- **Hosting Type (Cloud / VPS / Residential):** d218-14.smtp-out.eu-west-2.amazonses.com

- **Reputation Check Result:** 0/94 Community Score


- **Abuse Reports:** N/A


### Domain Analysis

- **Domain Name:** http://amazonses.com/
- **Registrar:** Amazones
- **Creation Date:** n/a
- **Domain Age:** n/a
- **Name Servers:** Server
- **Reputation:** N/A


**Infrastructure Assessment:**



> {{Describe legitimacy or malicious indicators}}



---



## 6. URL Analysis (Present)


- **Fanged URL:** https://amedyna.com/
- **De-Fanged URL:** hxxps://amedyna[.]com/
- **Resolved-IP:** n/a
- **Page Behavior:**

![Page Behavior]()

![Virus Total URL Analysis]()

![URL Scan]()




**Analysis:**



> {{Explain purpose and malicious indicators}}



---



## 7. Attachment Analysis - None Present


> {{Describe payload, embedded scripts, execution behavior}}



---



## 8. Social Engineering Indicators



- Urgency Language: 

- Fear Tactics:

- Brand Impersonation:

- Grammar / Formatting Issues:

- Domain Impersonation:

- Homoglyph Indicators:

![Preview of Mail]

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





### Email Addresses

- **To:** noreply-coinbasewalletverifiying.irs.mantab@shangriladogchew.com

- **Reply-To:** N/A



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



- Virus Total

- WhoisLookup

- Whoisdomain

- urlscan

- Custom Email Analyzer Tool



---



## 14. Evidence & Screenshots



### Email Screenshot

(Insert image)



### URL Page Screenshot

(Insert image)




---



**Analyst Signature:**  

RS


---



