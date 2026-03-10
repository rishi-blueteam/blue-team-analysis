# Phishing Analysis Report – Case 009



---



## 1. Case Information



- **Case Number:** 009

- **Analyst:** Rishab Shorey

- **Date Reported:** 10-03-2026

- **Date Analyzed:** 10-03-2026

- **Email File Name:** Sample-1013

- **Source of Sample:** Lab



---



## 2. Executive Summary



Provide a concise overview of the phishing attempt.



- **Type of phishing:** Advance Fee Fraud / Business Email Compromise (BEC) Style Scam

- **Intent (Credential Harvesting / Malware Delivery / Redirect / BEC):** Financial Scam / Social Engineering (Victim Engagement)

- **Key Indicators:** Reply-To Gmail mismatch, emotional manipulation referencing illness and inheritance funds, SPF softfail, missing DKIM, DMARC failure, sender domain unrelated to email content, suspicious originating IP located in South Africa.

- **Risk Severity (Low / Medium / High / Critical):** Medium



**Summary:**



> The analyzed email represents a social-engineering based phishing attempt resembling a classic advance-fee fraud or BEC-style scam. The attacker claims to be a terminally ill individual seeking assistance to manage funds belonging to her late husband’s legacy. Technical analysis reveals authentication failures including SPF softfail, missing DKIM signature, and DMARC failure, indicating weak sender verification. The email also contains a reply-to Gmail address that does not match the sender domain, which is a common tactic used to redirect communication to attacker-controlled accounts. The originating IP address is located in South Africa and is unrelated to the sender domain infrastructure. The message does not contain URLs or attachments and instead relies purely on emotional manipulation to encourage victims to respond. Based on authentication issues, infrastructure inconsistencies, and social engineering tactics, the email is assessed as suspicious with moderate risk.



---



## 3. Email Metadata Overview



- **From:** shore@suksapan.or.th

- **To:** Recipients <shore@suksapan.or.th>

- **Reply-To:** elizabethray993@gmail.com

- **Subject:** Hi

- **Date:** Tue, 01 Aug 2023 17:09:24 +0100

- **Message-ID:** 481485b6-1e17-4ac0-aa95-77fd08bac8b8@DM6NAM10FT113.eop-nam10.prod.protection.outlook.com

- **Return-Path:** shore@suksapan.or.th

- **Language Used:** English (ENG)

![Header Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/Header%20Metadata%20Overview.png)

---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details


- **IP (Defanged):** 102[.]69[.]133[.]254

- **Originating IP:** 102[.]69[.]133[.]254

- **ASN Information:** AS328431 Connected-Space-AS, ZA (registered Feb 06, 2019) 

- **Resolved Host:** afrinic.net

- **Geo Location:** South Africa

![Tool-1](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/Tool-1.png)

![Tool-2](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/Tool-2.png)



### Email Authentication Results



- **SPF:** SoftFail

- **DKIM:** Missing

- **DMARC:** none (Message Not SIgned) (Compauth: Fail)



### Domain Comparison



- **Message-ID Domain:** outlook.com

- **From Domain:** suksapan.or.th

- **Mismatch Detected:** Yes



**Header Observations:**



> The email shows multiple authentication failures that indicate possible spoofing or unauthorized sending. SPF validation returned a softfail, meaning the sending IP address is not explicitly authorized by the domain’s SPF policy. DKIM authentication is missing, preventing verification of message integrity and sender authenticity. DMARC validation also failed, further indicating that the message could not be authenticated according to domain policy. Additionally, the Message-ID domain is associated with Microsoft Outlook infrastructure while the visible sender domain is suksapan.or.th, suggesting relay through external infrastructure. The originating IP address resolves to a network located in South Africa, which is inconsistent with the Thai domain used in the sender address, raising further suspicion regarding the legitimacy of the sending source.



---



## 5. Infrastructure Analysis



### Other Sender IP Analysis

#### IP-2 Analysis

- **De-Fanged IP:** 102[.]69[.]133[.]254

- **ASN:** AS132300 NIPA-AS-TH NIPA TECHNOLOGY CO., LTD, TH (registered Jun 13, 2012) 

- **ISP:** N/A

- **Hosting Type (Cloud / VPS / Residential):** host4.ns.co.th

- **Reputation Check Result:** n/a

- **Abuse Reports:** N/A

![IP2](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/ip2.png)

#### IP-3 Analysis

- **De-Fanged IP:** 10[.]13[.]153[.]119

> Assigned by the Internet Assigned Numbers Authority (IANA)

![IP-3](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/IP-3%20Results_iana.png)


### Domain Analysis

- **Domain Name:** suksapan.or.th

- **Registrar:** THNIC

- **Creation Date:**  06 Feb 2007

- **Domain Age:** 22 years

- **Name Servers:** MYNA.CAT.NET.TH | TEAL.CAT.NET.TH

- **Reputation:** False Positive Alert

![Domain ANalysis Virus Total](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/Domain%20ANALYSIS%20rESULTS_%20Virus%20Total.png)

![Virus Total Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/Virsu%20Total%20Threat%20Score.png)



**Infrastructure Assessment:**



> The domain suksapan.or.th was registered in 2007 and has a relatively long operational history, which may normally suggest legitimacy. However, the domain is unrelated to the financial narrative presented in the email. The infrastructure analysis also reveals that the email originated from an IP address located in South Africa that is unrelated to the domain's hosting environment. Furthermore, the reply-to address redirects communication to a public Gmail account, which does not match the sender domain. These inconsistencies between domain ownership, email purpose, and communication channel indicate that the infrastructure is likely being abused or spoofed as part of a social engineering campaign.



---



## 6. URL Analysis (None Present)
=

**Analysis:**

> No URLs are present in the email. The absence of links indicates that the attacker’s objective is not immediate redirection to a phishing website. Instead, the email is designed to initiate direct communication between the victim and the attacker through the provided reply-to email address. This approach is common in advance-fee fraud scams where attackers attempt to build trust and gradually request sensitive information or financial transfers during follow-up communications.



---



## 7. Attachment Analysis (None Present)


**Behavioral Observations:**



> No attachments or embedded scripts were identified in the email. The message contains only plain text content designed to persuade the recipient to respond. Because there are no files or executable content, the threat vector relies entirely on social engineering rather than technical exploitation or malware delivery.



---



## 8. Social Engineering Indicators



- **Urgency Language:** Urgent Situation With a limited timeframe due to cancer”

- **Fear Tactics:** Reference to terminal illness and limited time remaining to handle the funds

- **Brand Impersonation:** None

- **Grammar / Formatting Issues:** Informal greeting (“Hi”), inconsistent sentence structure, and poorly structured message body

- **Domain Impersonation:** Sender domain suksapan.or.th does not relate to the narrative presented in the email

- **Homoglyph Indicators:** None



**Assessment:**



> The attacker relies heavily on emotional manipulation to influence the recipient’s response. By claiming to suffer from cancer and referencing a deceased husband’s financial legacy, the attacker attempts to create sympathy and urgency. This narrative encourages the recipient to feel morally obligated to assist the sender. The absence of links or attachments suggests the primary objective is to initiate a conversation with the attacker through the provided Gmail reply-to address. Once communication is established, the attacker would likely attempt to extract sensitive information or request financial assistance as part of an advance-fee fraud scheme.



---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Suspicious   |
| Attachment         | None  |
| Authentication     | Failed   |
| Social Engineering | High   |
| **Overall**        | **Medium** |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- 102[.]69[.]133[.]254
- 10[.]13[.]153[.]119



### Domains (Defanged)

- suksapan[.]or[.]th



### Email Addresses

- Sender: shore@suksapan.or.th

- Reply To: elizabethray993@gmail.com



---



## 11. Final Verdict



> The email is classified as suspicious and indicative of an advance-fee fraud or BEC-style scam. Technical analysis reveals multiple authentication failures including SPF softfail, missing DKIM signature, and DMARC failure. Additionally, the sender domain does not align with the financial narrative presented in the email, and communication is redirected to a public Gmail account through the reply-to field. The originating IP address is located in South Africa and does not match the sender domain infrastructure. The message contains no URLs or attachments and instead relies on emotional manipulation involving illness and inheritance funds to encourage victims to initiate contact. Based on these indicators, the email is assessed as a social engineering phishing attempt with moderate risk.



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
- WHOIS Lookup
- WhoisDomain
- Custom Email Analyzer Tool



---



## 14. Evidence & Screenshots



### Email Screenshot

![Original Email Screenshot](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%209/Original%20Mail.png)



---



**Analyst Signature:**  

Rishab Shorey



---




