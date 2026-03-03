## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:**  Practical 7: Nuclear EK Infection


**PCAP File Name:**  TRAFFIC ANALYSIS EXERCISE: DOCUMENTING A NUCLEAR EXPLOIT KIT (EK) INFECTION | 2015-02-15



**Traffic Time Range:** 



**File Link:** https://www.malware-traffic-analysis.net/2015/02/15/index.html



**Suspected Malware Family (if known):**
 


**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary

You're working as an analyst at your organization's Security Operations Center (SOC).  One of the other analysts is investigating an alert for Nuclear exploit kit (EK).  This activity happened at your UK office.  Fortunately, that location has full packet capture, and the analyst retrieved a pcap of network traffic from the associated IP address.

The analyst reviewed the pcap and found what triggered the snort alert.  Unfortunately, the analyst cannot determine if the computer at your UK location was infected.  You've been asked to take a look.


You review the pcap and check the other analyst's report.  First, you double-check the following:

Date and time of the activity
- IP address of computer
- Host name of computer
- MAC address of computer
- IP address and domain name that generated the Nuclear EK traffic
 

Traffic indicates the user was web browsing.  With this in mind, you try to determine:

What website the user looked at before the Nuclear EK traffic
If a malware payload was sent that could possibly infect the user's computer




<br>



## Environment & Initial Observations



**Suspected victim IP:** 192.168.137.81



**Notable protocols observed:** data-text-lines,http,ip,tcp,eth,frame, udp, dns, nbns



**Timezone used for analysis:** UK (UTC+)



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1: IP address of computer**

**Answer** 192.168.137.81


**Question-2: Host name && MAC of computer**

**Answer:** BARTO-PC<00> (Workstation/Redirector) |  Dell_6a:bd:22 (5c:f9:dd:6a:bd:22)


**Question-3: IP address and domain name that generated the Nuclear EK traffic**

**Answer** 108.178.15.187 || f9wb0396aobdotyzddcwdtf[.]ilaclama[.]us 


<br>

## Suspicious File IOC

**File Link**

- hxxps[:]//www[.]malware-traffic-analysis[.]net/2015/02/15/page5[.]html

Refer the Zip File at the site, extract it to find the suspicious file.



## Wireshark Filters Used

- dns
- http.content_type
- http.request
- tcp.stream
- nbns

<br>

## Indicators of Compromise (IOCs)

**Any Domains**

- hxxp[:]//bnureb0up683ppcbgt1fz9g[.]isbul[.]info/index[.]php?n=anM9MSZ1YnR5emE9cXZieWJtbHQmdGltZT0xNTAyMTUyMzIzMzYzMDkyMjU3NCZzcmM9MjIwJnN1cmw9d29sZmdhbmdzc3RlYWtob3VzZS5jby5rciZzcG9ydD04MCZrZXk9MjY3QzM5RTQmc3VyaT0vd3AtaW5jbHVkZXMvanMvanF1ZXJ5L2pxdWVyeS5qcyUzZnZlcj0xLjExLjE=

- f9wb0396aobdotyzddcwdtf[.]ilaclama[.]us

- hxxp[:]//zz1lb82z00y16gdow25fcxm[.]ilaclama[.]us/watch[.]php?fuhgi=MTIyMDU5ODkwNjhkMTQ5ODNkNDI2YWEzNWJjYjNjNTJi

- http[:]//f9wb0396aobdotyzddcwdtf[.]ilaclama[.]us/VQlXBEpVSwQ[.]html

- hxxp[:]//f9wb0396aobdotyzddcwdtf[.]ilaclama[.]us/B0hCSgFdUgdNBhhTTAMCBFAHAQIGXFJMAAcESgQNHwZTUh4HBUoCWwc

**User Agents**

- Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; Trident/6.0)


**IP-ADDRESS**

- 108.178.15.187


**RE-Directs**

- hxxp[:]//zz1lb82z00y16gdow25fcxm[.]ilaclama[.]us/watch.php?fuhgi=MTIyMDU5ODkwNjhkMTQ5ODNkNDI2YWEzNWJjYjNjNTJi

Compromsied Websie GET request redirect


![Compromised Website Re-Direct]()

<br>

**Threat Score of EK Sites**

- hxxp[:]//f9wb0396aobdotyzddcwdtf[.]ilaclama[.]us/VQlXBEpVSwQ[.]html

![First Site Threat Score]()

- hxxp[:]//f9wb0396aobdotyzddcwdtf[.]ilaclama[.]us/B0hCSgFdUgdNBhhTTAMCBFAHAQIGXFJMAAc

![Second SIte Threat Score]()

![Exploit Kit Name]()

**File Names:**

- 3c25[.]tmp
- Suspicious-File-1
- suspicious-File-2
- suspicious-File-3

**File Hashes**

Tmp File:

**MD5:** 5c1b278efd0d5a952f1ba3ea230e3dbf
**SHA-1:** c6a27c939c64d9eee3d81481337af141832a419e
**SHA-256:** 9d4843ea3f0b0be3b533b50b17e8c1d2460e7136f7a46b4700ea5eb596629d7d 

![File Threat Score tmp]()

Suspicious-File-1:

- **MD5:** da7200f00c1fd92cb514131f418d2f8d
- **SHA-1:** 694007857330f013514f045974d70f388e2bd08a
- **SHA-256:** d9f266eb1dbd2bca408c837c3c4eaa39135417649ace63ba20d58c2df88ea19f 

![Suspicious FIle 1 Threat Score]()

Suspicious-File-2:

- **MD5:** c353f39ea4ed2556e8e30855bc14f18d
- **SHA-1:** d07ebc0844dcdf79f3ad1e639d0230fe67f4847f
- **SHA-256:** c4b1c55a90877d0618c2dc8bad01b33f1d60f3613b3673bdb08465569bdb8236 

![Suspicious-File-2 Threat Score]()


Suspicious-File-3: 

- **MD5:** 03e6eecc83239752fac874bc880588fa
- **SHA-1:** 28b9468949d5f3e4be3207fd568d05e654493090
- **SHA-256:** b4cb839573156364fc2a10a2d0a57cced697f076ce9fe4aa3604ada0b7a77523 

![Suspicious-File-3 Threat Score]()


## Key Takeaways & Learning**





### What I learned from this analysis**




### Mistakes or confusion faced**





### New Wireshark techniques used**

-



### What I would investigate further in a real SOC**

-



<br>





## References**



- MalwareTrafficAnalysis.net exercise page



- Any malware research links (if used): 



&nbsp; 















