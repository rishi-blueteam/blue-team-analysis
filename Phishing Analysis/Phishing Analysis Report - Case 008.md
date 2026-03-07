# Phishing Analysis Report – Case 008



---



## 1. Case Information



- **Case Number:** 008

- **Analyst:** Rishab Shorey

- **Date Reported:** 02-08-2023

- **Date Analyzed:** 06-03-2026

- **Email File Name:** Sample-1012[.]eml

- **Source of Sample:** Lab


---



## 2. Executive Summary



Provide a concise overview of the phishing attempt.



- **Type of phishing:** Impersonation

![Impersonation of Domain](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Suksapan%20Domain%20Phishing%20Possible.png)

- **Intent (Credential Harvesting / Malware Delivery / Redirect / BEC):** Money Theft

- **Key Indicators:** Poor Languagge, Grammer, Reply to mail and threat scores

- **Risk Severity (Low / Medium / High / Critical):** Medium



**Summary:**



> The analyzed email appears to be a phishing or spam campaign promoting financial loan services under the name “Global Merit Expert.” Header analysis reveals authentication weaknesses, including SPF softfail, missing DKIM signature, and DMARC softfail, indicating poor sender authentication and potential spoofing risk. The sender domain suksapan.or.th does not align with the advertised service, and the reply-to address redirects communication to a Gmail account, which is commonly used in fraudulent campaigns. Infrastructure analysis shows that the domain has been flagged for possible phishing activity on security platforms. Although no attachments or URLs were included, the email relies on social engineering techniques to encourage victims to initiate contact. The message structure resembles unsolicited financial spam designed to lure recipients into engaging with the attacker. Based on authentication issues, domain inconsistencies, and social engineering indicators, the email is classified as suspicious and potentially malicious



---



## 3. Email Metadata Overview



- **From:** shore@suksapan[.]or[.]th

- **To:** Recipients <shore@suksapan.or.th>

- **Reply-To:** globalmeritexperts@gmail.com

- **Subject:** Hi

- **Date:** Wed, 02 Aug 2023 13:47:50 +0100

- **Message-ID:** 6e0afff7-e921-4f9b-a051-93760dc1e4ca@AM7EUR06FT021.eop-eur06[.]prod[.]protection[.]outlook[.]com

- **Return-Path:** shore@suksapan[.]or[.]th

- **Language Used:** English

![Original Email](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Original%20Email.png)


![Tool Email Header Analysis](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Tool%20Email%20Header%20Analysis.png)


---



## 4. Email Header & Authentication Analysis



### Sender & Routing Details

> In Total there are 3 IP found and our considered as our crucial for investigation purposes 

#### IP - 1

- **IP (Defanged):** 102[.]69[.]139[.]111

- **Originating IP:** 102[.]69[.]139[.]111

- **ASN Information:** N/A

- **Resolved Host:** N/A

- **Geo Location:** N/A

![ip1_Tool-1_](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/ip1_talos_tool.png)

![ip1_tool-1](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/ip1_whoisdomian_tool.png)

#### IP 2

- **Originating IP:** 10[.]233[.]255[.]227

- **ASN Information:** N/A

- **Resolved Host:** Nipa

- **Geo Location:** Thailand

> Other detail refer the image below from both tools


![ip2_whoisdomain_tool](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/ip2_whoisdomian_tool.png)

![ip2_talos_tool](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/ip2_talos_tool.png)


#### IP 3

- **Originating IP:** 202[.]129[.]206[.]234

- **ASN Information:** N/A

- **Resolved Host:** Nipa

- **Geo Location:** Thailand

> Other detail refer the image below from both tools


![ip3_whoisdomain_tool](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/ip3_whoisdomian_tool.png)

![ip3_talos_tool](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/ip3_talos_tool.png)







### Email Authentication Results



- **SPF:** SoftFail

- **DKIM:** Missing

- **DMARC:** softfail

> Refer the Email Header Analysis Tool As above

### Domain Comparison



- **Message-ID Domain:** AM7EUR06FT021.eop-eur06.prod.protection.outlook.com

- **From Domain:** suksapan.or.th

- **Mismatch Detected:** Yes



**Header Observations:**



> The email exhibits multiple authentication weaknesses that indicate potential spoofing or unauthorized sending. SPF returned a softfail, meaning the sending host was not explicitly authorized by the domain’s SPF record. DKIM authentication is missing, preventing verification of message integrity and sender authenticity. DMARC also resulted in a softfail, indicating that the domain’s authentication policy did not fully validate the sender. Additionally, the Message-ID domain belongs to Microsoft Outlook protection infrastructure while the visible sender domain is suksapan.or.th, suggesting relay through external infrastructure. The presence of multiple originating IP addresses and routing through different infrastructure locations further raises suspicion about the legitimacy of the email path.



---



## 5. Infrastructure Analysis



### Sender IP Analysis



- **ASN:** N/A

- **ISP:** n/a

- **Hosting Type (Cloud / VPS / Residential):** Cloud

- **Reputation Check Result:** Possible Phishing

- **Abuse Reports:**



### Domain Analysis



- **Domain Name:** suksapan[.]or[.]th

- **Registrar:** THNIC

- **Creation Date:**  06 Feb 2007

- **Domain Age:** 22 years (Expected)

- **Name Servers:**  TEAL.CAT.NET.TH

- **Reputation:** Possible Phishing (Virus Total)

- **Threat Score** 2/94

![Virus Total DOmain Check](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Virus%20Total%20Domain%20Check.png)

![Virus Total Domain Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Virus%20Total%20Domain%20Check%20Threat%20Score.png)



**Infrastructure Assessment:**



> The infrastructure associated with the email shows mixed indicators. The domain suksapan.or.th is a long-standing domain registered in 2007, which normally suggests legitimacy; however, security reputation checks indicate that the domain has been flagged for possible phishing activity. The email also uses a reply-to address hosted on Gmail (globalmeritexperts@gmail.com
), which does not match the sender domain and is a common tactic used in phishing campaigns. Additionally, the infrastructure routing through multiple IP addresses without clear attribution further increases suspicion. These inconsistencies between domain ownership, reply address, and email purpose indicate potentially malicious usage of the infrastructure.



---



## 6. URL Analysis - None Present



**Analysis:**



> No URLs were identified in the email body, indicating that the attacker’s objective is not immediate redirection to a phishing page. Instead, the purpose of the message is likely to initiate direct communication with the victim through the provided email address. This tactic is commonly used in financial fraud or advance-fee scams, where victims are persuaded to contact the attacker to receive fraudulent loan offers. The absence of URLs or attachments suggests a social engineering approach designed to bypass automated email security filters



---



## 7. Attachment Analysis - None Present 




**Behavioral Observations:**



> No attachments, embedded scripts, or executable payloads were identified within the email. The message contains only text content promoting financial loan services and encouraging the recipient to respond to the provided contact email address. As a result, there is no direct execution behavior associated with the email. The primary threat vector is social interaction, where the attacker attempts to initiate communication and potentially conduct financial fraud or social engineering through follow-up exchanges.


---



## 8. Social Engineering Indicators



- **Urgency Language:** None

- **Fear Tactics:** 

    - **Brand Impersonation:** Possible impersonation of a financial services entity named “Global Merit Expert.” However, there is no clear evidence that it impersonates a known legitimate financial institution. The name appears generic and may be used to appear credible.

    - **Grammar / Formatting Issues:** Minor formatting inconsistencies observed. The greeting structure (“Hi” followed by “Hello”) is redundant, and there is a spacing issue in the sentence: “financial needs.Whether you need…”. Additionally, the message is structured like a bulk marketing email rather than a personalized communication.

    - **Domain Impersonation:** Yes. The sender domain suksapan.or.th does not align with the service being advertised (Global Merit Expert) and the contact email provided (globalmeritexperts@gmail.com
). This mismatch between sender domain and promoted service is a strong indicator of suspicious or spam behavior.

- **Homoglyph Indicators:** None observed. No characters appear to be visually deceptive substitutions (e.g., Cyrillic characters replacing Latin characters).



**Assessment:**



> The attacker uses a social engineering approach based on opportunity rather than urgency. The message advertises financial loan services and positions the sender as a trusted financial partner to attract individuals seeking financial assistance. By offering multiple loan options such as personal loans, mortgages, and business loans, the attacker attempts to appeal to a wide audience. The inclusion of a reply-to Gmail address encourages victims to initiate contact directly, allowing the attacker to continue the conversation outside the original email thread. This tactic is commonly used in advance-fee fraud or loan scams where victims are manipulated into providing sensitive information or paying fraudulent processing fees.



---



## 9. Risk Assessment



| Category           | Assessment |
|--------------------|------------|
| Infrastructure     | Suspicious   |
| Attachment         | None  |
| Authentication     | Partial   |
| Social Engineering | Moderate   |
| **Overall**        | **Medium** |



---



## 10. Indicators of Compromise (IOCs)



### IP Addresses (Defanged)

- 202.129.206.234

- 10.233.255.227

- 192.168.88.181

- 102.69.139.111

### Domains (Defanged)

- suksapan[.]or[.]th



### Email Addresses

- shore@suksapan.or.th

- globalmeritexperts@gmail.com



---



## 11. Final Verdict



> The email is classified as suspicious. While no malicious attachments or URLs were identified, several technical indicators raise concern. These include SPF softfail, missing DKIM authentication, DMARC softfail, and the use of a reply-to Gmail address that does not match the sender domain. Additionally, the sender domain has been flagged for potential phishing activity by security platforms. The email promotes financial services unrelated to the sending domain and encourages the recipient to initiate communication with an external email address, which is a common tactic in financial scam campaigns. Due to these inconsistencies and social engineering elements, the message presents a moderate security risk and should be treated as suspicious.



---



## 12. Recommended Defensive Actions (C.E.R.C Framework)



### Contain

- Block sender domain

- Block IP

- Block URL but since none is found we do not take any action.



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



- VirusTotal

- Talos INtelligence 

- None

- Custom Email Analyzer Tool



---



## 14. Evidence & Screenshots



### Email Screenshot

![Original Email](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Original%20Email.png)



---



**Analyst Signature:**  

RS


---




