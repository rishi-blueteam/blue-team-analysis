## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** Practical_9 - Alerts for Angular Alerts



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



**Suspected victim IP:** 172.16.101.196



**Notable protocols observed:** http,urlencoded-form,tcp,eth,ip,frame 



**Timezone used for analysis:** UTC



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Date & Time of Activity

**Answer** From ( 2015-03-03 | 19:05:11 ) | | To ( 2015-03-03 | 19:12:59 ) 


**Question-1:** IP address of the associated desktop or computer

**Answer** 172.16.101.196


**Question-1:** Host Name, User Agent and MAC of the Desktop 

**Answer** Gregory, Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; WOW64; Trident/6.0), ASUSTekCOMPU_3d:ef:01 (38:2c:4a:3d:ef:01)



![Host Name, IP, MAC](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Host%20Name%2C%20IP%2C%20MAC.png)


**Question-1:** Summary of the Activity 

**Answer** We are able to notice that the user was browsing a compromised website to which he was redirected to another website, which was malacious. That malacious website had multiple redirect links which probably tempted the user to click on it to get exposed to the malware present in those website. 


<br>



### Level 2 – Intermediate Level**



**Question** Site User interacted with initially

**Answer:** www[.]awesomeapartments[.]com

![Site Preview](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/A.png)

**Question** Compromised Website Details (Name, IP, Threat Score)

**Answer:** www[.]awesomeapartments[.]com, 192[.]186[.]248[.]36


![Awesome_Apartment_Compromsied Proof](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Awesome_Apartment_Compromsied%20Proof.png)

**Question** Malware Found (Type, Threat Score)

**Answer:** Trojan


**Question** Re-Directed SIte containing Malware (Page Preview, IP Address)

**Answer:** hxxp://moonstoneafgelekte[.]onewide[.]co[.]uk/R1kIcmqyPTEiPARlfB_rx3Yg9uwUhVs0GJteIS

![redirected_site_moonstone_from_awesomeapartments]([https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Re-Directed%20Site_1%20Moonstoneaf.png](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/redirected_site_moonstone_from_awesomeapartments.png)

> This was how the Malware Site looked like 

![Moonstone Preview](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Re-Directed%20Site_1%20Moonstoneaf.png)


![Moon_Redirected_Site_Threat_Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Moon_Redirected_Site_Threat_Score.png)

These are the URL which are found inside the re-directed site which contains malware.

![RD1_URL1](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/URL1_RD1_Found.png)

**Question**  Any Other Re-Directs Destination

**Answer:** http://1454316211[.]xml[.]diprotector[.]com/clk/kw?k=4110301199&t=1454316211&s=1921&f=227652234&qip=5[.]62[.]3[.]68

![Re-Directed Site_2.xml.diprotector.html.png](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/URL2_RD1_Found.png)


**Question**  Any Other Re-Directs Destination

**Answer:** http://3296472[.]3939947[.]optimize[.]clickshieldfilter[.]com/click[.]php?x=dBitTkqiJtXVbveLtU8IFHBU25HqqlhaEO5Xj53cEYM8wbn6PkfXWvsqBU0AneWC85PF3t8YSE448kX7RKdvRpxHSbUxj291aXrOMWyxyXtgfCwQgAlcMzgeGc0a2ZhNNdfdk3TlJGFeoXKape8JPdHDHptARqRKi16fuRnG8opJqv4M7dO4PhU5jS9YJZv3gVuqBHvMyNRMaxSgqCnml6F5IEVAiK3BdH%2FeJ7Ksh%2BgzES97gD%2F%2BFfdWkYGsTKFdmZnYup8on4ZxYuYctZzzqc6naWZHI1UEln0Ogsb8v4sReqL3XAyd%2F3N8PAJCFLfuwshKD%2FcHy6BYsZmyipSa%2Bch%2Brn40aTexGVqZ885Hrdd%2FbUsPI%2BjBtgor6eZ5bszEahFGUyhBO3CzX9Me2C%2FH9AfZ6EiPlJYNHYbGF4tRfp%2BiDXchkkZiPkG2dWj%2FuPamz4MPwsYAeyEWICj%2FqQ9jebU6b40rCRtTvh%2BosHZCl2XK5BBAvyMLEPF%2FrRFdbXQSJL5KLEfkYR4R4jzqoW%2F5%2BaFrRW5e%2FN6suFpMWFjZCQnWRCQDvBDYxIr6ojHrytWF


![Re-Directed Site_3 xmlka.com.png](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/URL3_RD1_Found.png)

![Re-Directed 4](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/URL4_RD1_Found.png)

![Re-Directed 5](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/URL5_RD1_Found.png)

Malware found for the destination Link

> SInce the file type was mentioned it was high possiblity that this was malacious

![Malware for clickshieldFilter](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Malware%20Possible%20Javafile%20found%20for%20clickshielfilter.png)


<br>



## Wireshark Filters Used

- dhcp
- dns
- http
- http.request
- http
- nbns
- http.content_type


<br>



## Indicators of Compromise (IOCs)


**User Agents**

- Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; WOW64; Trident/6.0)

**IP-ADDRESS**

- 95[.]211[.]192[.]222


**RE-Directs**

- wrY.z9kMZJF.com
- TobTiJ7.6wm4LK.com
- 8MXHN7VK.dkA.com
- ALJsZnVa.LZ6am.com
- tVf5MY.sCr4YPF.com

>other important redirects were also found

![Redirect 2](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Re-Directed%20Site_2.xml.diprotector.html.png)

![redirect 3](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%209%20Angler%20EK%20Report/Re-Directed%20Site_3%20xmlka.com.png)

**Site IOC**

MD5 : ff415e16ea2c8ddc9d254206476d6566
SHA-1 : abbae8c21f638417d591e5f705026f6a6155a215
SHA-256 : 11145608a8207124cc4e10fdfee63c888ddfc6adc5a2218b7c3b3d008100fb73 

<br>





## Key Takeaways & Learning**

- I believe there was nothing new which I could learn, what I did was just another analysis, not much of a challenge, found many other malware possible sites. 

<br>





## References**



MalwareTrafficAnalysis.net exercise page

















