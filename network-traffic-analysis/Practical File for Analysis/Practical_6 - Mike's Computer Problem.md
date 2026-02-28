## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** Practical_6 - Mike's Computer Problem  | 25-02-2026



**PCAP File Name:** 2015-02-08-traffic-analysis-exercise[.]pcap



**Traffic Time Range:** 2015-02-08 18:20 PM to 2015-02-08 18:44 PM



**File Link:** https://www.malware-traffic-analysis.net/2015/02/08/index.html



**Suspected Malware Family (if known):** upatre, generickds, smnf


**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary

<p> Mike calls the Help Desk and says his desktop computer is "acting weird" but he refuses to provide any details.  The Help Desk reports it to your organization's Security Operations Center (SOC).  A phone call to Mike doesn't reveal any details.  He insists his computer is "acting weird" but will not say what, exactly, is wrong.

One of the SOC analysts searched through network traffic and retreived a pcap related to this activity.  This traffic occurred shortly before Mike called the Help Desk.  The analyst cannot figure out what happened, so you've been asked to take a look.

</p>


## Requirement 

You review the pcap and take notes.  First, you document the following:

Date and time of the activity
IP address of Mike desktop computer
Host name of Mike's desktop computer
MAC address of Mike's desktop computer
 


<br>



## Environment \& Initial Observations



**Internal IP range:** 172.16.137[.]1



**Suspected victim IP:** 172.16.137[.]1



**Notable protocols observed:** DNS, HTTP, SMTP, TLS, SSL, TCP, UDP, 



**Timezone used for analysis:** IST & UTC



<br>



## Questions For Analysis



### L1- Basic Level Questions

Q-1.1: **Date and time of the activity**

- 2015-02-08 18:20:00.781778Z	

Q-1.2: **IP address of Mike desktop computer**

- 172.16.137.40

Q-1.3: **Host name of Mike's desktop computer**

- MIKE-PC

Q-1.4: **MAC address of Mike's desktop computer**

- 08:00:2b:ef:ab:7c

![Mikes COmputer information]()

### L2-Intermidiate Findings

Q-2.1: **Exploit Kit deployed by which site, defanged site name**

- http[:]//www[.]download[.]windowsupdate[.]com/msdownload/update/v3/static/trustedr/en/authrootstl[.]cab



Q-2.2: **IP of site**

- 2[.]16[.]162[.]43

Q-2.3: **Exploit Kit Name and Content Name**

- Authroot[.]stl

![exploit kit findings]()

Q-2.4: **Stream Name | host name | User Agent**

- tcp.stream eq 10 | www[.]download.windowsupdate[.]com | Microsoft-CryptoAPI/6.1

![stream host useragent site]()

### Addiotional and Extra Findings

- We found an img known as the arrowu[.]jpg which contains a trojan file.

![Arrowjpgmalware]()

## Wireshark Filters Used






<br>



## Indicators of Compromise (IOCs)

### Any Domains

- http[:]//checkip[.]dyndns[.]org/ 
- http[:]//harveyouellet[.]com/TOXICOUSTIQUE/arrowu[.]jpg
- http[:]//cwvancouver[.]com/cp/images/digits/arrowu[.]jpg
- http[:]//www[.]download[.]windowsupdate[.]com/msdownload/update/v3/static/trustedr/en/authrootstl[.]cab

### User Agents

- Mozilla/5.0
- Microsoft-CryptoAPI/6.1

### IP-ADDRESS

- 216[.]146[.]39[.]70
- 192[.]185[.]35[.]92
- 71[.]18[.]62[.]202
- 2[.]16[.]162[.]43

### Trojon Image Hash

- **MD5:** 6643e36630b9826fc740a79d6212a0cf
- **SHA-1:** 3de6f7475b467b46d045eb29ebb100d15212a4f9
- **SHA-256:** 99e832a42f6b22057816170b18fc0af66b1a34cd745973fd0d6e62cb33258562 

### Trojan Document File Hash

**MD5 -** 1a9d39436c1597108f8baf6d7dc5dd45
**SHA-1 -** 79b631306b575b0fa3e96ef6d554d1203f2fe27d
**SHA-256 -** db09a7db2f12bff9d64f06c721df40c8d13db47b04d0948598a9c9454af38c56


<br>





## Key Takeaways & Learning**

> The key learnings taken from this analysis is I have been able to analyze quicker, find the relevant sites, export and document them quickly. I found important IOC's in terms of images, IP and websites which the user has clicked and caused a harm to its own system. I also followed many of the tcp streams to see how user initiated conversation with servers and how it did initiate the whole process of getting the malware into the system. I was also able to do the phishing attachment analysis which helped me to take the investigation further to see the root cause of this whole malware attack taking place. Not all attacks are suppsoed to be an exploit kit some are definetly a part of un intended malware download casing harm to the system.



### Mistakes or confusion faced**

> What confusion I faced is maybe some malware can appear clean and un doubted images may not be the required malware that the user appears to click. It is how I should analyze every small detail and document them and not rush to conclude. Mostly my answers does stick to what is expected. 



### New Wireshark techniques used**

-



### What I would investigate further in a real SOC**

-



<br>





## References**



- MalwareTrafficAnalysis.net exercise page



- Any malware research links (if used)



- Screenshot Link

&nbsp; 















