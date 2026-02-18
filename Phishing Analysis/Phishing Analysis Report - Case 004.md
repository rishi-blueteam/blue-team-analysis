# Phishing Analysis Report – Case 004	



---



## 1. Case Information



- **Case Number:** 004

- **Analyst:** Rishab Shorey

- **Date Reported:** 17-02-2026

- **Date Analyzed:** 17-02-2026

- **Email File Name:** Sample 1009

- **Source of Sample:** Lab



---



## 2. Executive Summary


- **Type of phishing:** Spoofing

- **Intent:** Malware, Credential Harvesting, Re-Direct and Command and Control

- **Key Indicators:** PDF Threat Score 19, Threat Vecor Graph, MITRE ATT&CK Scope 

- **Risk Severity** (Low / Medium / High / Critical): Medium



**Summary:**



> The Email is pretending to be a user from the Bank Of Brazil. The email, design, layout, and way of structuring seems to bland. It's source IP address, is not a verified place to start with, the pdf, the reply to, its all poorly designed.



---



## 3. Email Metadata Overview



- **From:** sel553r@gmail.com

- **To:** phishing@pot

- **Reply-To:** n/a

- **Subject:** Crédito IR Liberado - v5V0ZVRe1HjazliqQoYz

- **Date:** 29-07-2023

- **Message-ID:** d21e5a021950b9fdf1aab7fa0c059612@gmail.com

- **Return-Path:** sel553r@gmail.com

- **Language Used:** Portugese



---



## 4. Email Header & Authentication Analysis

### Sender & Routing Details



- **Sender IP (Defanged):** 209[.]85[.]222[.]173

- **Originating IP:** N/A

- **ASN Information:**  AS15169 GOOGLE - Google LLC, US (registered Mar 30, 2000) 

- **Resolved Host:** mail-qk1-f173.google[.]com 

- **Geo Location:** USA



### Email Authentication Results



- **SPF:** Pass

- **DKIM:** Pass

- **DMARC:** Pass



### Domain Comparison



- **Message-ID Domain:** d21e5a021950b9fdf1aab7fa0c059612[@]gmail[.]com 

- **From Domain:** mail-qk1-f173[.]google[.]com 

- **Mismatch Detected:** Yes



**Header Observations:**



> The Header analysis concludes multiple factors. The SPF, DMARC are known to be true and safe, which doesn't possess impersonation. Infact various other factors conclude a phishing attempt. First mainly the local IP address appear to be from USA where as the actual domain where the sender is pretending source is to be is Brazil. There is no local IP that runs anywhere close the same continent which makes this into a suspicion. The message ID domain and the From domain are relatively different while it shows impersonation ability to take place. No other anomality's are shown



---



## 5. Infrastructure Analysis



### Sender IP Analysis



- **ASN:** AS15169 GOOGLE - Google LLC, US (registered Mar 30, 2000) 

- **ISP:** N/A

- **Hosting Type** (Cloud / VPS / Residential): Residential

- **Reputation Check Result:** Clean

- **Abuse Reports:** None



### Domain Analysis

- **Domain Name:** n/a
 
- **Registrar:** n/a

- **Creation Date:** n/a

- **Domain Age:** n/a

- **Name Servers:** n/a

- **Reputation:** n/a



**Infrastructure Assessment:**



> The infrastructure appears to look clean as the the CSP is from a Google and no other parameters were found during the investigation.



---



## 6. URL Analysis



### URL 1



- **Fanged URL:** https://okaoskaoskasommmc.z13.web.core.windows.net/

- **Defanged URL:** https[:]//okaoskaoskasommmc[.]z13[.]web[.]core[.]windows[.]net/

- **Resolved IP:** N/A

- **ASN:** N/A

- **Redirect Chain:** N/A

- **SSL Certificate Info:** N/A

- **Page Behavior:** N/A



**Analysis:**



> The web page appears to be taken down, no SSL certificate and redirect chain is found, and hence a fair conclusion cannot be justified.



---



## 7. Attachment Analysis (If Present)



- **Attachment Name:** U1vn48GmdQr.pdf

- **File Type (Actual):** PDF

- **File Size:** 97.4 kb

- **MD5:** 920b39742dcfc9f937ace8ae288e9ac2

- **SHA1:** 86e6d8b2cc1cdcb50daefaefdd3466f279991311

- **SHA256:** 831b3c4cfe0ff181e09a584d180d4ff5b9963a1e7be5e25d6b857ad63713d024

- **VirusTotal Detection Ratio:** 19/64

- **Contains Embedded URLs:** Yes

- **Macro Presence:** No



**Behavioral Observations:**



> The pdf file attached to mail is highly malicious, with a true positive threat score of 19 by 64. Virus Total does verify the File hash containing trojan, & phishing malware included in the file 



---



## 8. Social Engineering Indicators



- **Urgency Language:** No urgency, just attraction of user with high greed of amount has been noticed through the mail.  

- **Fear Tactics:** N/A

- **Brand Impersonation:** Bank 

- **Grammar / Formatting Issues:** Grammar of the mail looks fair, since its Spanish, a true depiction of grammar cannot be justified, yet formatting speaks volumes as it seem just a simple mail to push the luck of the attacker.

- **Domain Impersonation:** Bank of Brazil

- **Homoglyph Indicators:** N/A



**Assessment:**



> {{Explain how the attacker manipulates the recipient}}



---



## 9. Risk Assessment


| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Clean      |
| Attachment         | Malacious  |
| Authentication     | Partial    |
| Social Engineering | Moderate   |
| **Overall**        | **Medium** |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

 - 20[.]161[.]8[.]184
 - 10[.]13[.]2[.]127
 - 209[.]85[.]222[.]173






### Domains (Defanged)

- mail-qk1-f173[.]google[.]com 



### URLs (Defanged)

- https[:]//okaoskaoskasommmc[.]z13[.]web[.]core[.]windows[.]net/



### File Hashes

- **MD5:** 920b39742dcfc9f937ace8ae288e9ac2

- **SHA1:** 86e6d8b2cc1cdcb50daefaefdd3466f279991311

- **SHA256:** 831b3c4cfe0ff181e09a584d180d4ff5b9963a1e7be5e25d6b857ad63713d024



### Email Addresses

- **From:** sel553r@gmail.com

- **Reply To:** sel553r@gmail.com



---



## 11. Final Verdict



> The analazyed mail is bound to be more than just suspicious. Considering it has been impersoniating a legitimate source to trick users to engage with this mail is considered as a **Medium** Risk Score.  



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



- VirusTotal

- WHOIS Domain Lookup

- ReverseIP Lookup
- URLVoid
- URL2PNG
- CheckPhish
- Email Parser Tool (For header analysis, and IP collection) (Rishab Shorey)



---



## 14. Evidence & Screenshots



### Email Screenshot

![Email SS](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%204/Email%20SS.png)



### URL Page Screenshot

![url](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%204/Site%20Not%20Found.png)

### Attachment Preview

![Attachment Preview](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%204/PDF%20File%20Analysis.png)

### Attachment Threat Score 

![Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%204/File%20Analysis%20Threat%20Score.png)


---



**Analyst Signature:**  

Rishab Shorey



---




