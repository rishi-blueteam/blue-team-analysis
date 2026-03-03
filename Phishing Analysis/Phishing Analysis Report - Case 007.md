# Phishing Analysis Report – Case 007


---



## 1. Case Information



- **Case Number:** 007

- **Analyst:** Rishab Shorey

- **Date Reported:** 3-03-2026

- **Date Analyzed:** 3-03-2026

- **Email File Name:** {{File Name}}

- **Source of Sample:** Lab Practical


---



## 2. Executive Summary


**Original Mail**:

![Original Mail]()


- **Type of phishing:** Impersonation, Money Extorsion, 

- **Intent** (Credential Harvesting / Malware Delivery / Redirect / BEC):

- **Key Indicators:**

- **Risk Severity (Low / Medium / High / Critical):**



**Summary:**



> The analyzed email is a malicious phishing attempt leveraging impersonation and money extortion tactics. Although the message was sent through Google’s legitimate mail infrastructure (AS15169), authentication checks reveal SPF failure and DMARC failure, indicating domain misuse and potential spoofing behavior. The email contains a TinyURL shortened link, which was later taken down due to policy violations, strongly suggesting malicious intent. Social engineering tactics such as urgency and promotional manipulation were used to pressure the recipient. The use of URL shorteners obscures the final destination and increases risk exposure. No attachments were present; however, the embedded link represents the primary threat vector. Based on authentication failures, URL abuse, and social engineering indicators, the email is assessed as malicious and high risk.



---



## 3. Email Metadata Overview



- **From:** samranefahim@gmail.com

- **To:** kjhgfdxgchvjbkhgfdxcvb@monkey56.skin

- **Reply-To:** N/A

- **Subject:** _Get_Rid_of_Back_Pain_Easily.Try_Therapal!_

- **Date:** Fri, 28 Jul 2023 21:25:06 +0200

- **Message-ID:** CANXpgOo_98j4Gfuj2mMFYUaTgWQhW4GxuO8VONmuQ9MZXcJSDg@mail.gmail.com

- **Return-Path:** kuytrsdyfuyiuytrsedtfyghiuytrf+bncBCEN7T4W34PBBP5MSCTAMGQEQOICCHY@monkey56.skin

- **Language Used:** Default (English)

![Header Analysis - subject, from, to, attachments. Message ID, Date, IP]()

---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details



- **Sender IP (Defanged):** 209[.]85[.]167[.]208

- **Originating IP:** Same as Sender

- **ASN Information:** AS15169 GOOGLE - Google LLC, US (registered Mar 30, 2000)

- **Resolved Host:** mail-oi1-f208.google.com

- **Geo Location:** United States

![Domain Results - Domain tools]()

### Email Authentication Results



- **SPF:** None (protection.outlook.com: monkey56.skin does not designate permitted sender hosts)

- **DKIM:** Present

- **DMARC:** spf=none (sender IP is 209.85.167.208) smtp.mailfrom=monkey56.skin; dkim=pass (signature was verified) header.d=monkey56-skin.20221208.gappssmtp.com;dmarc=fail action=none header.fr


![Email Authentication results]()

### Domain Comparison


- **Message-ID Domain:** mail.gmail.com

- **From Domain:** gmail.com

- **Mismatch Detected:** No



**Header Observations:**



> The email exhibits authentication inconsistencies, including SPF failure and DMARC failure for the domain monkey56.skin, despite DKIM passing. This suggests misalignment between the sending domain and authenticated domain, a common indicator of spoofing or unauthorized domain usage. The Return-Path domain differs significantly from the visible sender (gmail.com), indicating potential envelope spoofing. Additionally, the email was sent to a suspicious, randomly generated domain (monkey56.skin), which raises further concerns. While the sending IP belongs to legitimate Google infrastructure, authentication misalignment and domain irregularities strongly suggest malicious intent.



---



## 5. Infrastructure Analysis



### Sender IP Analysis



- ASN: AS15169 GOOGLE - Google LLC, US (registered Mar 30, 2000)

- ISP: n/a

- Hosting Type (Cloud / VPS / Residential): Cloud

- Reputation Check Result: Not Valid / Removed 

- Abuse Reports: n/a



### Domain Analysis



- Domain Name: tinyurl.com

- Registrar: n/a

- Creation Date: n/a

- Domain Age: n/a

- Name Servers: n/a

- Reputation: Abuse / Not Valid



**Infrastructure Assessment:**



> Although the sender IP originates from Google’s legitimate cloud infrastructure, this alone does not establish trustworthiness. The use of a URL shortening service (tinyurl.com) combined with the domain’s abuse status indicates malicious redirection behavior. The lack of transparent infrastructure details and the fact that the shortened URL has been taken down due to policy violations further confirms misuse. These factors collectively point toward malicious intent rather than legitimate communication.


---



## 6. URL Analysis



### URL 1



- **Fanged URL:** https://tinyurl.com/2jcccaj3

- **Defanged URL:** hxxps[:]//tinyurl[.]com/2jcccaj3

- **Resolved IP:** 209.85.167.208

- **ASN:** n/a

- **Redirect Chain:** n/a

- **SSL Certificate Info:**  N/A (Site Taken Down)

- **Page Behavior:** N/A (Not known, site taken down by tinyurl due to policy misuse)


**Analysis:**



> The primary purpose of the embedded TinyURL link is likely to redirect the victim to a malicious landing page, potentially for financial fraud or scam activity. URL shortening services are commonly used in phishing campaigns to hide the final destination from both users and security tools. The fact that the link has been disabled due to policy misuse strongly indicates that it was associated with malicious or fraudulent activity. The absence of SSL details and redirect transparency further increases suspicion.



---



## 7. Attachment Analysis (None)




**Behavioral Observations:**



> No attachments or embedded executable payloads were identified within the email. The primary threat vector is the embedded shortened URL, which likely redirected the user to an external malicious website. Execution behavior would depend on user interaction, such as clicking the link and submitting personal or financial information. Since the site was taken down, direct payload analysis was not possible; however, the structure indicates a classic link-based phishing attempt.



---



## 8. Social Engineering Indicators



- Urgency Language: Hurry, Sale Ends Soon

- Fear Tactics: Hurry!

- Brand Impersonation: Therapal

- Grammar / Formatting Issues: n/a (It is a iamge which has been pasted)

- Domain Impersonation: n/a (As it is inform of tiny url and upon expanding we get a site not in use due to misuse in policy)

- Homoglyph Indicators: n/a



**Assessment:**



> The attacker uses urgency-based language such as “Hurry” and promotional pressure tactics to create a sense of limited-time opportunity. This psychological manipulation encourages impulsive action without critical evaluation. Brand impersonation (Therapal) is used to create perceived legitimacy and trust. By embedding the content within an image, the attacker attempts to bypass text-based spam filters. The shortened URL conceals the final destination, reducing user suspicion and increasing click probability.



---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Suspicious   |
| Attachment         | None  |
| Authentication     | Partial   |
| Social Engineering | High   |
| **Overall**        | High |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- 209[.]85[.]167[.]208
- 100[.]127[.]140[.]133
- 209[.]85[.]220[.]65




### Domains (Defanged)

- tinyurl[.]com


### URLs (Defanged)

- hxxps[:]//tinyurl[.]com/2jcccaj3
- hxxp[:]//74[.]249[.]99[.]69/?act=oop&pid=0_mt&uid=2&vid=14815&ofid=259&lid=0&cid=0



### Email Addresses

- Sender: Stephanie C. Frisbie" <samranefahim@gmail.com>

- Reply to: None

- Sent to: kjhgfdxgchvjbkhgfdxcvb@monkey56.skin


---



## 11. Final Verdict



> The email is malicious. Despite being sent through legitimate Google mail servers, authentication misalignment (SPF and DMARC failure), use of a shortened URL associated with policy abuse, urgency-based social engineering tactics, and suspicious recipient domain collectively confirm phishing intent. The absence of transparent redirect information and the removal of the landing page due to misuse further validate malicious classification. The overall risk is assessed as High due to strong indicators of deception and financial exploitation intent



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

- WHOIS Lookup domain

- urlvoid

- whois.com

- Custom Email Analyzer Tool



---



## 14. Evidence & Screenshots



### Email Screenshot

(Insert image)



### URL Page Screenshot

(Insert image)



### Attachment Preview

(Insert image)



---



**Analyst Signature:**  

R.S


---



