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



- **Type of phishing:** Brand Impersonation Phishing

- **Intent (Credential Harvesting / Malware Delivery / Redirect / BEC):** Credential Harvesting via phishing website redirect.

- **Risk Severity (Low / Medium / High / Critical):** High

**Key Indicators:**

- Sender email domain shangriladogchew.com does not belong to Coinbase.
- Display name spoofing: “C o i n b a s e” spaced to bypass filters.
- Suspicious account security alert theme designed to trigger panic.
- Embedded phishing link hxxps://amedyna[.]com/ unrelated to Coinbase.
- Mismatch between Message-ID domain (amazonses.com) and sender domain.
- Use of AWS SES mail infrastructure, commonly abused in phishing campaigns




**Summary:**



> This email is a phishing attempt impersonating Coinbase in order to deceive the recipient into believing that their account security settings have been modified. The message claims that the user’s phone number has been changed and urges them to secure their account by clicking a provided link. The sender address originates from the domain shangriladogchew.com, which is unrelated to Coinbase, indicating clear brand impersonation. The embedded URL redirects users to amedyna[.]com, a domain not associated with Coinbase and likely intended to harvest user credentials or personal verification data. Although the message passes SPF, DKIM, and DMARC authentication through Amazon SES infrastructure, these authentication results only validate the sending server and not the legitimacy of the sender identity. The combination of brand impersonation, deceptive messaging, and a malicious external link strongly indicates a credential harvesting phishing campaign.



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

![Tool Analysis Preview](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Tool%20Analysis%20Preview.png)

### Domain Comparison



- **Message-ID Domain:** amazonses.com

- **From Domain:** shangriladogchew.com

- **Mismatch Detected:** Yes

![Message id domain Threat Score_VirusTotal](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Message%20id%20domain%20Threat%20Score_VirusTotal.png)


**Header Observations:**



> The email uses Amazon Simple Email Service (SES) infrastructure, which explains why SPF, DKIM, and DMARC authentication checks pass. However, authentication success does not guarantee legitimacy because attackers frequently abuse legitimate cloud email services to distribute phishing emails. The sender display name impersonates Coinbase by using spaced characters (“C o i n b a s e”) to evade automated filtering systems. Additionally, the sender domain shangriladogchew.com is unrelated to Coinbase and indicates domain spoofing. There is also a mismatch between the Message-ID domain (amazonses.com) and the sender domain, which further supports the conclusion that the email was sent through third-party infrastructure rather than Coinbase’s official mail servers.



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

![whoisip_tool1](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/whoisIP_Tool-1.png)

![whoisip_tool2](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/whoisIP_Tool-2.png)


### Domain Analysis

- **Domain Name:** http://amazonses.com/
- **Registrar:** Amazones
- **Creation Date:** n/a
- **Domain Age:** n/a
- **Name Servers:** Server
- **Reputation:** N/A

![Message ID Domain Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Message%20id%20domain%20Threat%20Score_VirusTotal.png)

**Infrastructure Assessment:**



> The sending infrastructure originates from Amazon Web Services using Amazon SES mail servers located in the United Kingdom. While AWS infrastructure itself is legitimate, it is frequently abused by attackers to distribute phishing emails due to its reputation and ability to pass authentication checks. The sender domain shangriladogchew.com appears unrelated to Coinbase or any financial service and likely represents a compromised or attacker-controlled domain used solely for phishing campaigns. The mismatch between the sender domain and the impersonated brand, combined with the presence of an external phishing URL (amedyna[.]com), strongly indicates malicious infrastructure usage rather than legitimate communication.



---



## 6. URL Analysis (Present)


- **Fanged URL:** https://amedyna.com/
- **De-Fanged URL:** hxxps://amedyna[.]com/
- **Resolved-IP:** n/a
- **Page Behavior:**

![Page Behavior](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Page%20Behavior.png)

![Virus Total URL Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/URL%20Analysis%20-%20VT.png)

![URL Scan](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/URL%20Analysis%20-%20URLScan.png)




**Analysis:**



> {The email contains a call-to-action button labeled “Secure My Account”, which redirects the user to hxxps://amedyna[.]com/. This domain is not associated with Coinbase and is therefore highly suspicious. The purpose of this URL is likely to host a fake login page that imitates the Coinbase authentication interface in order to capture user credentials or personal verification details. Such phishing pages typically request login credentials, two-factor authentication codes, or identity verification data. The use of a completely unrelated domain is a strong indicator of phishing activity designed to redirect victims to a malicious credential harvesting page.



---



## 7. Attachment Analysis - None Present


> No file attachments were present in the email. The phishing attack relies solely on social engineering and a malicious embedded URL to redirect the victim to an external phishing website.



---



## 8. Social Engineering Indicators



- **Urgency Language:** The subject line “Important: Your phone number has been changed” creates urgency and suggests immediate account compromise.

- **Fear Tactics:** The message implies unauthorized access to the victim’s account and restriction of cryptocurrency withdrawals to create panic and pressure the recipient into acting quickly.

- **Brand Impersonation:** The attacker impersonates Coinbase, a well-known cryptocurrency platform, to exploit user trust.

- **Grammar / Formatting Issues:** Subject line typo: “You phone number has been changed” instead of “Your phone number”, Unusual display name formatting “C o i n b a s e”, Slight grammatical inconsistencies in the message body.

- **Domain Impersonation:** Sender domain shangriladogchew.com is unrelated to Coinbase and indicates brand impersonation.

- **Homoglyph Indicators:** No direct homoglyph substitution detected, but spacing manipulation in “C o i n b a s e” is used to mimic the legitimate brand.

![Preview of Mail](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Email%20Preview.png)

**Assessment:**



> The attacker uses a classic account security alert scenario to manipulate the recipient into reacting quickly without verifying the authenticity of the message. By claiming that the victim’s phone number has been changed and that cryptocurrency withdrawals are restricted, the email creates a sense of urgency and fear of financial loss. The attacker then provides a “Secure My Account” button that leads to an external phishing site. This technique relies on emotional pressure and brand trust to trick users into revealing sensitive account credentials.



---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Suspicious   |
| Attachment         | None  |
| Authentication     | Passed   |
| Social Engineering | High   |
| **Overall**        | High |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- 10[.]152[.]29[.]182

- 23[.]249[.]218[.]14



### Domains (Defanged)

- shangriladogchew[.]com



### URLs (Defanged)

- hxxps://amedyna[.]com/





### Email Addresses

- **To:** noreply-coinbasewalletverifiying.irs.mantab@shangriladogchew.com

- **Reply-To:** N/A



---



## 11. Final Verdict



> This email is classified as malicious phishing. The message impersonates Coinbase and falsely claims that the recipient’s phone number was changed in order to create urgency and fear. The sender domain shangriladogchew.com is unrelated to Coinbase and indicates domain impersonation. The embedded link redirects users to amedyna[.]com, which is not associated with Coinbase and is likely designed to harvest user credentials. Although SPF, DKIM, and DMARC authentication checks pass due to the use of Amazon SES infrastructure, these results only confirm the sending server and do not validate the legitimacy of the sender identity. The combination of brand impersonation, deceptive messaging, and a malicious external link confirms this email as a credential harvesting phishing attempt.



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

![Email Preview](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Email%20Preview.png)



### URL Page Screenshot

![Page Behaviour](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%2010/Page%20Behavior.png)


---



**Analyst Signature:**  

RS


---



