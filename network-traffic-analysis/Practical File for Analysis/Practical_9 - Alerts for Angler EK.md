## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** 



**PCAP File Name:** 2015-03-03-traffic-analysis-exercise



**Traffic Time Range:** 



**File Link:** https://www.malware-traffic-analysis.net/2015/03/03/index.html



**Suspected Malware Family (if known):** Includer, 



**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary

Time for another shift at your organization's Security Operations Center (SOC).  You review some EmergingThreats alerts for Angler exploit kit on a host within your network.

### Requirements

- Date and time of the activity
- IP address of the associated desktop (or laptop) computer
- Host name of the associated desktop (or laptop) computer
- MAC address of the associated desktop (or laptop) computer
- Brief summary of the activity
 



<br>



## Environment \& Initial Observations



**Internal IP range:**



**Suspected victim IP:**



**Notable protocols observed:**



**Timezone used for analysis:**



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Date & Time of Activity

**Answer** From ( 2015-03-03 | 19:05:11 ) | | To ( 2015-03-03 | 19:12:59 ) 


**Question-1:** IP address of the associated desktop or computer

**Answer** 


**Question-1:** Host Name, User Agent and MAC of the Desktop 

**Answer**


![Host Name, IP, MAC]()


**Question-1:** Summary of the Activity 

**Answer** 


<br>



### Level 2 – Intermediate Level**



**Question** Site User interacted with initially

**Answer:** www[.]awesomeapartments[.]com

![]

**Question** Compromised Website Details (Name, IP, Threat Score)

**Answer:** www[.]awesomeapartments[.]com, 192[.]186[.]248[.]36

![Awesome_Apartment_Compromsied Proof]()

**Question** Malware Found (Type, Threat Score)

**Answer:** 


**Question** Re-Directed SIte containing Malware (Page Preview, IP Address)

**Answer:** 

![redirected_site_moonstone_from_awesomeapartments]()

![Moon_Redirected_Site_Threat_Score]()


**Question**  Any Other Re-Directs Destination

**Answer:** http://1454316211[.]xml[.]diprotector[.]com/clk/kw?k=4110301199&t=1454316211&s=1921&f=227652234&qip=5[.]62[.]3[.]68

![Re-Directed Site_2.xml.diprotector.html.png]()


**Question**  Any Other Re-Directs Destination

**Answer:** http://3296472[.]3939947[.]optimize[.]clickshieldfilter[.]com/click[.]php?x=dBitTkqiJtXVbveLtU8IFHBU25HqqlhaEO5Xj53cEYM8wbn6PkfXWvsqBU0AneWC85PF3t8YSE448kX7RKdvRpxHSbUxj291aXrOMWyxyXtgfCwQgAlcMzgeGc0a2ZhNNdfdk3TlJGFeoXKape8JPdHDHptARqRKi16fuRnG8opJqv4M7dO4PhU5jS9YJZv3gVuqBHvMyNRMaxSgqCnml6F5IEVAiK3BdH%2FeJ7Ksh%2BgzES97gD%2F%2BFfdWkYGsTKFdmZnYup8on4ZxYuYctZzzqc6naWZHI1UEln0Ogsb8v4sReqL3XAyd%2F3N8PAJCFLfuwshKD%2FcHy6BYsZmyipSa%2Bch%2Brn40aTexGVqZ885Hrdd%2FbUsPI%2BjBtgor6eZ5bszEahFGUyhBO3CzX9Me2C%2FH9AfZ6EiPlJYNHYbGF4tRfp%2BiDXchkkZiPkG2dWj%2FuPamz4MPwsYAeyEWICj%2FqQ9jebU6b40rCRtTvh%2BosHZCl2XK5BBAvyMLEPF%2FrRFdbXQSJL5KLEfkYR4R4jzqoW%2F5%2BaFrRW5e%2FN6suFpMWFjZCQnWRCQDvBDYxIr6ojHrytWF


![Re-Directed Site_3 xmlka.com.png]()

Malware found for the destination Link

![Malware for clickshieldFilter]()


<br>



### Level 3 – Basic Findings



**Question**



**Answer**



<br>



## Wireshark Filters Used






<br>



## Indicators of Compromise (IOCs)

- Any Domains

- User Agents

**IP-ADDRESS**

- 95[.]211[.]192[.]222


**RE-Directs**

- wrY.z9kMZJF.com
- TobTiJ7.6wm4LK.com
- 8MXHN7VK.dkA.com
- ALJsZnVa.LZ6am.com
- tVf5MY.sCr4YPF.com

**Site IOC**

MD5 : ff415e16ea2c8ddc9d254206476d6566
SHA-1 : abbae8c21f638417d591e5f705026f6a6155a215
SHA-256 : 11145608a8207124cc4e10fdfee63c888ddfc6adc5a2218b7c3b3d008100fb73 

<br>





## Key Takeaways \& Learning**



### What I learned from this analysis**




### Mistakes or confusion faced**





### New Wireshark techniques used**

-



### What I would investigate further in a real SOC**

-



<br>





## References**



- MalwareTrafficAnalysis.net exercise page



- Any malware research links (if used)
















