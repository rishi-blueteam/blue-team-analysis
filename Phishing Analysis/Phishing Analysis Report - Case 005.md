# Phishing Analysis Report – Case 005



---



## 1. Case Information



- **Case Number:** 005

- **Analyst:** Rishab H Shorey

- **Date Reported:** 24-02-2026

- **Date Analyzed:** 24-02-2026

- **Email File Name:** sample1010[.]eml

- **Source of Sample:** Lab



---



## 2. Executive Summary

This helps to provide a concise overview of the phishing attempt.



- Type of phishing: Possible Impersonation

- Intent (Credential Harvesting / Malware Delivery / Redirect / BEC): Intent is Monetary Stealing but false positive alert

- Key Indicators: Phishing Webpage, MisMatch with original Website

- Risk Severity (Low / Medium / High / Critical): High



**Summary:**



> The analyzed email was initially suspected to be a possible impersonation attempt with potential monetary intent. However, detailed header analysis confirmed that SPF, DKIM, and DMARC authentication mechanisms successfully passed, indicating authorized email transmission. The message originated from SendGrid (AS11377), a legitimate cloud email service provider, and no negative reputation indicators were identified. Infrastructure and domain analysis of quantinsti.com and its subdomain showed no malicious reputation or abuse records. The embedded SendGrid tracking URL resolved to Amazon-hosted infrastructure with a valid SSL certificate and normal page behavior. No attachments, credential harvesting elements, or malicious redirects were observed. Although a minor Message-ID and domain mismatch was detected, it does not indicate malicious intent. Based on the overall technical assessment, the email is determined to be legitimate and safe.



---



## 3. Email Metadata Overview



- **From:** Raunaq Sahni raunaq[.]s@quantinsti[.]com

- **To:** n/a

- **Reply-To:** N/A

- **Subject:** Desvende os Segredos do Momentum Trading em Português

- **Date:** Fri, 28 Jul 2023 19:32:27 +0000

- **Message-ID:** USPP9TOgSja8rIXka996_A@geopod-ismtpd-0

- **Return-Path:** hotmail.com@em.quantinsti.com

- **Language Used:** Portuguese

![Language]()


---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details



- **Sender IP (Defanged):** 10[.]13[.]183[.]94

- **Originating IP:** 10[.]13[.]183[.]94

- **ASN Information:** AS11377 SENDGRID - SendGrid, Inc., US (registered Jun 28, 2012) 

- **Resolved Host:** o73.email.quantinsti.com 

- **Geo Location:** USA

![IP LOOKUP Image]()



### Email Authentication Results



- **SPF:** PASS

- **DKIM:** Present

- **DMARC:** Pass

![Email Authentication Results]()


### Domain Comparison



- **Message-ID Domain:** USPP9TOgSja8rIXka996_A@geopod-ismtpd-0

- **From Domain:** raunaq.s@quantinsti.com

- **Mismatch Detected:** Yes



**Header Observations:**



> While the Email Authentication passes, Sender and Routing Detail appears to be as legitimate, Domain and message id domain mismatch but no scope of malaicious intent is to be seen. 



---



## 5. Infrastructure Analysis



### Sender IP Analysis



- ASN: AS11377 SENDGRID - SendGrid, Inc., US (registered Jun 28, 2012) 

- ISP: N/A

- Hosting Type (Cloud / VPS / Residential): Cloud

- Reputation Check Result: Clean

- Abuse Reports: N/A

![ip Score CHeck]()


### Domain Analysis



- Domain Name: quantra[.]quantinsti[.]com

- Registrar: May 3rd 2010, 11:47:47 (UTC)

- Creation Date: May 3rd 2010, 11:47:47 (UTC)

- Domain Age: Valid for 3 Months

- Name Servers: AMAZON-02 - Amazon.com, Inc.,

- Reputation: Not Classified




**Infrastructure Assessment:**



> Legitmate domain appeared. NO malaicious intent found.



---



## 6. URL Analysis



### URL 1



- **Fanged URL:** https://u13167954.ct.sendgrid.net/ls/click?upn=cCwlxFFkk6IY-2BfKHW5dgoh1or-2FQ7KJUScu4inDlSgZ0bthg-2BdzxSLrqUxQq8L4LnHGaTsyeKhM-2BGoGZULX-2BQDtKX4KQTEiqQnreMUHwSq4lbJ1CWx6-2BGInyvwrkWbe-2Bwub0R1ynAbkw2ra-2BadpP46SY4q2aUoMOrNTtQ3Sr0qFk-3DpKU-_Ee7nT2ZQdJ749eAGxVv-2FHN3XNBqa48KbYVWhgkx4gPlepzXOF3ammh8xLlzB8DbUYkzIaPk4OLvL-2BwE4oacnVy018owo4uZxEZWTLYlzUscwf2Vi7O851tVduXijZ1mSTyAYBbFHqud7qT2SNGgLIea9MrmnTbjsMkEntX9gWWzQjrSd-2B4R7q57K5tD9HLb4oTUftyCHahaOv2lh44zXo-2BTCeN7w2UO-2F6SxcLwfCk1v7qZPu0-2BHRKUWXfBUMaU2i3hsW74xKNFXYWV7mCDpV2hKj1iYGSwzxrLcvo7sLqAJBNL4tRRLnag6PEYH2sq3lJjQI3hHpGpCt-2FDMF5YtbeJuad0z-2FGL5pHIVZ9pNhDilKWBx-2BETLUJJ5gkdPWLpGxgc4Rv-2FWVYDtQ49YmpVwSc3JAhK3AIPftD-2BnjDVMV-2Bjvh1fpi9BnLDKDM1cfP1xBU

- **Defanged URL:** https[:]//u13167954[.]ct[.]sendgrid[.]net/ls/click?upn=cCwlxFFkk6IY-2BfKHW5dgoh1or-2FQ7KJUScu4inDlSgZ0bthg-2BdzxSLrqUxQq8L4LnHGaTsyeKhM-2BGoGZULX-2BQDtKX4KQTEiqQnreMUHwSq4lbJ1CWx6-2BGInyvwrkWbe-2Bwub0R1ynAbkw2ra-2BadpP46SY4q2aUoMOrNTtQ3Sr0qFk-3DpKU-_Ee7nT2ZQdJ749eAGxVv-2FHN3XNBqa48KbYVWhgkx4gPlepzXOF3ammh8xLlzB8DbUYkzIaPk4OLvL-2BwE4oacnVy018owo4uZxEZWTLYlzUscwf2Vi7O851tVduXijZ1mSTyAYBbFHqud7qT2SNGgLIea9MrmnTbjsMkEntX9gWWzQjrSd-2B4R7q57K5tD9HLb4oTUftyCHahaOv2lh44zXo-2BTCeN7w2UO-2F6SxcLwfCk1v7qZPu0-2BHRKUWXfBUMaU2i3hsW74xKNFXYWV7mCDpV2hKj1iYGSwzxrLcvo7sLqAJBNL4tRRLnag6PEYH2sq3lJjQI3hHpGpCt-2FDMF5YtbeJuad0z-2FGL5pHIVZ9pNhDilKWBx-2BETLUJJ5gkdPWLpGxgc4Rv-2FWVYDtQ49YmpVwSc3JAhK3AIPftD-2BnjDVMV-2Bjvh1fpi9BnLDKDM1cfP1xBU

- **Resolved IP:** 13[.]235[.]226[.]198

- **ASN:** Amazon.com

- **SSL Certificate Info:** Issued by R13 on January 26th 2026. Valid for: 3 months. 

![Resolved IP and ASN information]()

- **Redirect Chain:** Available

![Redirect Request]()



- **Page Behavior:** Normal



**Analysis:**



> No purpose described, site seems normal and fair enough to use.



---



## 7. Attachment Analysis 

None Present

---



## 8. Social Engineering Indicators


- I consider this section as null and void as this is a safe site to use according to my analysis.


**Assessment:**



> N/A


---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Clean      |
| Attachment         | None       |
| Authentication     | Passed     |
| Social Engineering | None       |
| **Overall**        | Clean      |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- 54[.]229[.]75[.]109

- 13[.]235[.]226[.]198 



### Domains (Defanged)

- quantra[.]quantinsti[.]com



### URLs (Defanged)

- https[:]//u13167954[.]ct[.]sendgrid[.]net/ls/click?upn=cCwlxFFkk6IY-2BfKHW5dgoh1or-2FQ7KJUScu4inDlSgZ0bthg-2BdzxSLrqUxQq8L4LnHGaTsyeKhM-2BGoGZULX-2BQDtKX4KQTEiqQnreMUHwSq4lbJ1CWx6-2BGInyvwrkWbe-2Bwub0R1ynAbkw2ra-2BadpP46SY4q2aUoMOrNTtQ3Sr0qFk-3DpKU-_Ee7nT2ZQdJ749eAGxVv-2FHN3XNBqa48KbYVWhgkx4gPlepzXOF3ammh8xLlzB8DbUYkzIaPk4OLvL-2BwE4oacnVy018owo4uZxEZWTLYlzUscwf2Vi7O851tVduXijZ1mSTyAYBbFHqud7qT2SNGgLIea9MrmnTbjsMkEntX9gWWzQjrSd-2B4R7q57K5tD9HLb4oTUftyCHahaOv2lh44zXo-2BTCeN7w2UO-2F6SxcLwfCk1v7qZPu0-2BHRKUWXfBUMaU2i3hsW74xKNFXYWV7mCDpV2hKj1iYGSwzxrLcvo7sLqAJBNL4tRRLnag6PEYH2sq3lJjQI3hHpGpCt-2FDMF5YtbeJuad0z-2FGL5pHIVZ9pNhDilKWBx-2BETLUJJ5gkdPWLpGxgc4Rv-2FWVYDtQ49YmpVwSc3JAhK3AIPftD-2BnjDVMV-2Bjvh1fpi9BnLDKDM1cfP1xBU


### Email Addresses

- raunaq[.]s@quantinsti[.]com


---



## 11. Final Verdict



> Mail is not malacious and is considered safe to use.



---



## 12. Recommended Defensive Actions (C.E.R.C Framework)


- No Action required. The site is safe to use.

---



## 13. Tools Used



- VirusTotal

- WHOIS Lookup

- Checkphish

- Custom Email Analyzer Tool

- Domain Check



---



## 14. Evidence & Screenshots



### Email Screenshot

![Emailscreenshot]()



### URL Page Screenshot

![Site ScreenShot]()






---



**Analyst Signature:**  

Rishab Shorey



---



