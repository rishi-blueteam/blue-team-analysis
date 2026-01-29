## Case Overview

**Source:** MalwareTrafficAnalysis.net

**Exercise Name | Date:** Practical_1 EK Activity_Practice 3 

**PCAP File Name:** 2014-11-16-traffic-analysis-exercise

**Traffic Time Range:** 02:11:49 AM - 02:22:45 AM

**File Link:** https://www.malware-traffic-analysis.net/2014/11/16/index.html

**Suspected Malware Family (if known):** Trojan | Java

**Analysis Tool(s):** Wireshark


<br>



## Scenario Summary

Another practice scenario where the client is trying to access a website but turns out the site has been compromised and gives way for the attacker to add in a Exploit Kit in the form of Flash and Java File. It is a part of **"CVE-2014"**. I have able to notice, be able to use the filters wisely, go through number of packets to find the right the domains, redirects, suspicious links found during the whole analysis. Another EK Activity has been bagged down 4 more left to understand the scope of the problem caused on a unsafe HTTP protocol level.    


<br>



## Environment \& Initial Observations



**Internal IP range:** 172.16.165.165
<br> 
> For this case the noted activity is done with this specific client itself and no other client is seen in the pcap for analysis purposes. 


**Suspected victim IP:** 172.16.165.165

**Notable protocols observed:** udp,dns,llmnr,tls,frame,ip,http,igmp,tcp,data-text-lines,image-jfif,eth,xml,media,nbns,dhcp,image-gif


**Timezone used for analysis:** UTC Date and Time of the Day


<br>



## Questions For Analysis


### L1- Basic Level Questions

**Question_1.1** What is the IP address of the Windows VM that gets infected?

**Answer** 172.16.165.165 

**Question_1.2** What is the host name of the Windows VM that gets infected?

**Answer** K34EN6W3N-PC 

I used the [NBNS filter](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/EK%20Exercise%20/Exercise%203/EK%20Activity%20Practice%203%20NBNS.png) to extract the host name of the user

**Question_1.3** What is the MAC address of the infected VM?

**Answer** f0:19:af:02:9b:f1

**Question_1.4** What is the IP address of the compromised web site?

**Answer** 82.150.140.30 

**Question_1.5** What is the domain name of the compromised web site?

**Answer** www[.]Clinholand[.]nl

**Question_1.6** What is the IP address  that delivered the exploit kit and malware?

**Answer** 37.200.69.143 

**Question_1.7** What is the domain name that delivered the exploit kit and malware?

**Answer** www[.]stand[.]trustandprobaterly[.]com

<br>



### Level 2 – Intermediate Level


**Question_L2.1** What is the redirect URL that points to the exploit kit (EK) landing page?

**Answer** 24corp[-]shop[.]com

The term referer is the actual source from the site we are viewing is often listed and seen. Refer to [this](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/EK%20Exercise%20/Exercise%203/EK%20Activity%20Practice%203%20Re%20Directed%20Site%2C%20and%20Point%20from%20where%20it%20was%20re-directed%20.png)


**Question_L2.2** Besided the landing page (which contains the CVE-2013-2551 IE exploit), what other exploit(s) sent by the EK?

**Answer** The EK visible are X-shockwave-flash, and Java-Archive

**Question_L2.3** How many times was the payload delivered?

**Answer** 3 times in total [EK Exploits Image]

<br>

### Level 3 – Advance Findings

**Question**  What file or page from the compromised website has the malicious script with the URL for the redirect?


**Question** File hash for each of the Exploit?

**Answer:**

Flash: 7b3baa7d6bb3720f369219789e38d6ab

Java: 1e34fdebbf655cebea78b45e43520ddf

> This has been extracted after we have downloaded the exploit via Wireshark.

<br>

**Question** What file from the compromised website has an iframe for the redirect URL?

**Answer:**
[<]iframe src='http[:]//stand[.]trustandprobaterealty[.]com/?PHPSSESID=njrMNruDMhvJFIPGKuXDSKVbM07PThnJko2ahe6JVg|ZDJiZjZiZjI5Yzc5OTg3MzE1MzJkMmExN2M4NmJiOTM'[>]

I had to follow through the HTTP where it prompted the user to redirect so first I used the http.request filter to find each time a new domain request has been made, and once I landed to the site (24corp[-]shop[.]com) the original source from where it asked to go to the malicous site (www[.]stand[.]trustandprobaterly[.]com), as seen in this [image](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/EK%20Exercise%20/Exercise%203/EK%20Activity%20Practice%203%20icon_link1.png) and I could find it within the lines of the code as seen [here](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/EK%20Exercise%20/Exercise%203/EK%20Activity%20Practice%203%20NBNS.png)  

**Question** What are the snorts alert which are generated? 

**Answer:**

- ET INFO JAVA - Java Archive Download By Vulnerable Client [2014473]
- ET CURRENT_EVENTS Cool/BHEK/Goon Applet with Alpha-Numeric Encoded HTML entity [2017064]
- ET CURRENT_EVENTS GoonEK encrypted binary (3) [2018297]
- ET CURRENT_EVENTS Goon/Infinity URI Struct EK Landing May 05 2014 [2018441]
- ET CURRENT_EVENTS RIG EK Landing URI Struct [2019072]
- ET CURRENT_EVENTS RIG EK Landing Page Sept 17 2014 [2019193]
- ET CURRENT_EVENTS RIG EK Landing March 20 2015 M2 [2020726]
- ET CURRENT_EVENTS Possible IE MSMXL Detection of Local SYS (Likely Malicious) [2021430]

<br>



## Wireshark Filters Used

- **tcp.stream eq 20** (It shows a whole new tcp connection of a client trying to form one with a server but specially only and if the session is same but re-directed to a new site for a new session)

- **tcp.stream eq 19** (This filter helped to identify a whole tcp connection process from SYN, SYN-ACK, DATA, to FIN/RST)

- **http** or **http.request** to find sites contacted with, which I could alternatively use with http.request for better responses

- **http.type_content**: To filter out and find the exploit kits which are being used or which is a potential malware

- **NBNS** for host name of the endpoint


<br>


## Indicators of Compromise (IOCs)

**Any Suspicious Domains:**

- 4corp-shop.com
- stand.trustandprobaterealty.com
- adultbiz.in

**User Agents**

- Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; WOW64; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0) | | URL: http[:]//stand[.]trustandprobaterealty[.]com/?PHPSSESID=njrMNruDMhvJFIPGKuXDSKVbM07PThnJko2ahe6JVg|ZDJiZjZiZjI5Yzc5OTg3MzE1MzJkMmExN2M4NmJiOTM  

- Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; WOW64; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0)  | URL: http[:]//24corp-shop[.]com/

**IP-Address**

- 188.225.73.100

- 37.200.69.143:80

**RE-Directs Links**

- 4corp-shop.com

- stand.trustandprobaterealty.com



## File Integrity

**MD5:** 41d34d07aa81f3cb5ee12315cc5c88a9 

**SHA-1:** 8a8f655af61776d6233ca493210e574d673ed112 

**SHA-256:** 0e3fac547536f773bf1a21180a2294a10be97e956f091d24e168f147ecf5fafd


<br>



## Key Takeaways & Learning

### What I learned from this analysis

- TLS application data: Encrypted TLS application data was observed between the victim host and a Google CDN domain prior to a redirect event. This traffic likely represents normal HTTPS content delivery or script execution, as redirects can be triggered from within encrypted responses.

- I have been able to understand the filters better the, right understanding of filters, the way of making sense of how the packet data transfer has taken place.

- 



### Mistakes or confusion faced

Having answers with you always makes you be aware and learn more and hence I was able note mistakes and confusion:

- The big confusion between the filter of tcp.stream eq 19 && tcp.stream eq 20. Initially they are belonging to same ideaolgy of TCP connection but for a different purpose 




**### New Wireshark techniques used**

- 


<br>





## References


- [MalwareTrafficAnalysis.net](https://www.malware-traffic-analysis.net/index.html) source for PCap's



- Any malware research links (if used)


















