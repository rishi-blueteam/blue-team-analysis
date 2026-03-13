## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** You have the PCap, Now Tell Me About It


**PCAP File Name:** 2015-05-08-traffic-analysis-exercise



**Traffic Time Range:** 2015-05-08 (20:51:36) TO 2015-05-08 (20:53:41)



**File Link:** https://www.malware-traffic-analysis.net/2015/05/08/index.html



**Suspected Malware Family (if known):** SWF



**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary





<br>



## Environment & Initial Observations



**Internal IP range:** 192.168.138.158


**Suspected victim IP:** 192.168.138.158


**Notable protocols observed:** tcp, udp, http, ssl, nbns



**Timezone used for analysis:** UTC



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Host Name if available, IP Address, Mac Address if Available, User Agent


**Answer** No Host Name Seen , 192.168.138.158, No Mac Shown, **User Agent** Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; WOW64; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0)

![User AGent, IP and Host Information](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/User%20AGent%2C%20IP%20and%20Host%20Information.png)

<br>

> The first site the user visited was: 

**Site 1**: hxxp://va872g[.]g90e1h[.]b8[.]642b63u[.]j985a2[.]v33e[.]37[.]pa269cc[.]e8mfzdgrf7g0[.]groupprograms[.]in/?285a4d4e4e5a4d4d4649584c5d43064b4745



![Site Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/Site%20Threat%20Score.png)

> User is redirected to another malacious site, rather prompted to use the Malacious Flash. Host SIte and referer can be seen as below

![Re-Direct 1 to 2](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/Re-Direct%201%20%2B%202.png)

![Redirect 2 to 3+ Malacious SWF](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/Second%20Redirect%20to%20third%20Site%20(Containing%20SWF).png)

> Noticeable Threat Found, Exploit Kit Found SWF, threat categories mentioned as Trojan, plus CVE-2015-0311 also mentioned

![SWF File Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/SWF%20File%20Threat%20SCORE%20Found.png)

**IP OF REDIRECTED site is** : 62.75.195.236

**Site:** hxxp://r03afd2[.]c3008e[.]xc07r[.]b0f[.]a39[.]h7f0fa5eu[.]vb8fbl[.]e8mfzdgrf7g0[.]groupprogram

![IP OF re-direct 1 and 2](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/IP%20OF%20re-direct%201%20and%202.png)

DLL Exploit Kit found: Potential Malware

![urldmon files found](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/urldmon%20files%20found.png)




## Wireshark Filters Used

- dns
- http
- http.content_type
- http.request
- tcp stream
- nbns




<br>



## Indicators of Compromise (IOCs)

**Any Domains**

va872g[.]g90e1h[.]b8[.]642b63u[.]j985a2[.]v33e[.]37[.]pa269cc[.]e8mfzdgrf7g0[.]groupprograms[.]in/?285a4d4e4e5a4d4d4649584c5d43064b4745

**User Agents**

- Apache/2.2.15 (CentOS) DAV/2 mod_fastcgi/2.4.6
- Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; WOW64; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0)

**IP-ADDRESS**

- 62.75.195.236
- 192.168.138.158

**RE-Directs**

- http://ubb67.3c147o.u806a4.w07d919.o5f.f1.b80w.r0faf9.e8mfzdgrf7g0.groupprogra
- http://r03afd2.c3008e.xc07r.b0f.a39.h7f0fa5eu.vb8fbl.e8mfzdgrf7g0.groupprogram 

<br>

**SHA-256**: 81523163b298f2543d5f56a4c44ef8b07c6c9b3844b629b04fb870ca356c1437
**File Size**: 8.76 KB 


**Aim of the Attacker**

Based on the MITRE Tactics

![MITRE Tactics](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2010%3A%20You%20Have%20the%20PCap%20Now%20Tell%20me%20Bout%20it/MITRE%20Tactics.png)


## Key Takeaways & Learning**

> Nothing much to learn. I believe this was one wya to secure my learning ways to do analysis much better, all this while I have been focusing on the exercise of the EK. I believe these practical 10 packet captures I have done dedicatedly builds confidence and helps me to learn and explore a lot. 


### Aim for being a better analyst

> First and the most important is to get introduced to the tool of snort and learn more on that, after learning about snort I will develop my skills how to do analysis via help of snort and what rules get triggered with the snort.
> Since I have covered about 10 packet captures with just simple filtering, following http protocol and tcp streams, noting protcols, ip addresses, mac addresses, user agents, content types etc. It is time for me to do better, to document better. 
> My next focus will be towards maybe sandbox malware file analysis on cases where I find interesting malwares plus also because for free access I have limited number of file uploads to a sandbox.   
> I will focus on doing IP lookup to gain more infomration on the particular address of the malware site to gain better information. So I will have to format my document also in such a way to make the learning better.

<br>





## References**



- MalwareTrafficAnalysis.net exercise page















