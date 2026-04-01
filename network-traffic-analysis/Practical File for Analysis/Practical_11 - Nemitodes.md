# Practical 11 - Nemitodes

## Case Overview


**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** Nemotodes | 30-03-2026 



**PCAP File Name:** 2024-11-26 - TRAFFIC ANALYSIS EXERCISE: NEMOTODES



**Traffic Time Range:** 2024-11-26 : 04:49:38 AM to 2024-11-26 : 05:43:58 AM 



**File Link:** https://www.malware-traffic-analysis.net/2024/11/26/index.html 



**Suspected Malware Family (if known):**



**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary

You work as a analyst at a Security Operation Center (SOC) for a medical research facility specializing in nemotodes. Alerts on traffic in your network indicate someone has been infected. You don't know which is more disgusting, the nemotodes or the malware.

**LAN segment details:**

- **LAN segment range:**  10.11.26[.]0/24 (10.11.26[.]0 through 10.11.26[.]255)
- **Domain:**  nemotodes[.]health
- **Active Directory (AD) domain controller:**  10.11.26[.]3 - NEMOTODES-DC
- **AD environment name:**  NEMOTODES
- **LAN segment gateway:**  10.11.26[.]1
- **LAN segment broadcast address:**  10.11.26[.]255



<br>



## Environment & Initial Observations



**Internal IP range:** 10.11.26[.]0/24



**Suspected victim IP:** 10.11.26[.]183 - NEMOTODES-DC



**Notable protocols observed:** udp,frame,ip,quic,tls,tcp,eth, lldap, ssdp, tcp



**Timezone used for analysis:** UTC



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Details of the Victim (Hostname, IP , MAC Address, Windows Username)


**Answer** 

- **Hostname**: DESKTOP-B8TQK49<00> (Workstation/Redirector) (Intel)
- **IP Address of Host**: 10[.]11[.]26[.]183
- **MAC Address:** d0:57:7b:ce:fc:8b
- **Windows Username:** oboomwald

![Basic Information about the Client](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Basic%20Information%20about%20client.png)

![Hostname](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Hostname%20.png)

<br>



### Level 2 – Intermediate Level**



**Question** Supected Domain & IP Address

**Answer:** 

We are first able to notice the client visited a site where due to which we could have possibly been redirected to another website due to a fake browser update event. There are not threat score present but we still take this into accountability. The site user first visited was:

- hxxp://classicgrand[.]com

![First Link of Malware Found](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/First%20Link%20to%20Malware%20Site%20Found.png)

The user must have been re-directed


- hxxp://modandcrackedapk[.]com (193[.]42[.]38[.]139)

![ Malware Found](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Possible%20Malware.png)

**Threat Score of Malware given below**

![Threat Score of First site of Malware]()https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Malware%20Threat%20Score.png)

- hxxp://confirmsubscription[.]com (13[.]56[.]30[.]207)

![Re-Directed Site Malware Link Found](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Re-Directed%20Malware.png)


**Threat Score of Re-Directed Malware**

> We are able to notice false positive possibility due to the reason that the threat score is 1 out of 94

![Threat Score of Redirected Malware](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Possible%20Re-Directed%20Malware.png)


> There is another malware link which was possibly found and it is highly classified as a trojan of Netsupport. This is mostly said to be a SOCGHOSHLY kind of software update threat for browsers, we could anyway refer this online for the threat presence and we can refer to the user agent to support the decision of the NetSupport Server which is present

![NetSupport User AGent Server Hello Message Sent](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Server%20for%20Netsupport%20Possible.png)

- hxxp://geo[.]netsupportsoftware[.]com/location/loca[.]asp (104[.]26[.]1[.]231)
  

![Another Possible Malware](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Another%20Possible%20Malware%20Found.png)

> Threat Present in another malware site

![Threat Score of another Malware](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Another%20Malware%20site%20threat%20Score.png)

> There was also a re-directed site present in the URL present below:

![Url found in Malware site](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Possible%20url%20found%20in%20the%20Malware%20site.png)


> Since there were multiple POST request taking place, analysis of that particular site was also needed and hence we take notes of this crucial indicator too.

- http.//194-180-191-64.mivcloud.com (194.180.191.64)

![Submission Post Request sent for Site](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Submission%20Post%20Request.png)


  ![Threat Score for Malware SUbmission Request](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/Malware%20Threat%20Score%20in%20Form%20Submission%20Site.png)


<br>



## Wireshark Filters Used

- nbns
- http
- tls
- tcp.stream
- ssdp (new)
- ldap (new)
- (http.request or tls.handshake eq 1) && !ssdp (Helps us get the first handshake exchanged between the client and server for certificates, helps us get the request to a site the user intents to connect, and excludes the server discovery protocol)
- ldap.attributedescription == 'GivenName' (New) This technically a new command that help us find the username


## Snort Alerts Captured

[Snort Alerts File](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%2011%20-%20Nemetodes/alert_fast.txt)



<br>



## Indicators of Compromise (IOCs)

**Any Domains**

- classicgrand.com
- modandcrackedapk[.]com 
- confirmsubscription[.]com 
- geo[.]netsupportsoftware[.]com/location/loca[.]asp


User Agents

**IP-ADDRESS**

- 193[.]42[.]38[.]139
- 13[.]56[.]30[.]207
- 104[.]26[.]1[.]231
- 194[.]180[.]191[.]64


**RE-Directs**


- modandcrackedapk[.]com 
- confirmsubscription[.]com 

<br>





## Key Takeaways \& Learning**

> Well after a period of long time I am back to Wireless Analysis, and doing hands on analysis with latest threaths and existing vulnerabilities. This challenge was not as simple as it exist. I have came across various protocols, and seeing new protocols, no easy findings for exploits, or threats was really challenging. I didn't expect it to be different from the head to toe.

### What I learned from this analysis

I learnt about new protocols and its possible use case such as the SSDP

>  The Simple service Discovery Protocol that is used by clients to actively search for any services that are willing to discover other active devices present around. This is mostly actively taking place over the Ethernet or the Wi-Fi and it is a UDP protocol. I tried to relate it to Bluetooth but turns out Bluetooth operates over a Radio, and is using L2CAP protocol


> I also learnt about the LDAP which is used for the accessing and managing the directory information services over the IP. It is mostly used in SSO, EMAIL Systems, VPN Authentication in systems like Docker

> MDNS Protocol is a zero configuration protocol that reslves hostnames to IP Addresses on **small local network** without a dedicated DNS server. 

There are many such protocols but the learning about analysis is another priceless thing

> Unlike previous EK these are threats that are not found easily just by following some http stream and finding exploits in scripts, pdf or url's it is about identifying the right filter to do the right job for analysis and gain results as needed. 

HTTP streams were rather only a part of discovery as a lot of POST request seen which assumes for sure that there are potential alerts as given, sometimes it is not a malacious contnent which could be extracted as a artificat from Pcap but it can lay in a scrip in a url in a domain.

It is important to not just follow one way to find threats and exploints but discover actual findings from a pcap. 

> I have also learned and explore about the new Fake Browser Update Pages exploits which was the possible scenario for the attack to take place in detail.

### Mistakes or confusion faced

> Seeing new protocols should never be confusing, it should be a way of understanding that why did a particular pcap come up with a certain protcol and the actual intent behind it, how and why it is actually taking place. 



### New Wireshark techniques used**

> I haven't used new techniques, it is bout using new filters to find key information that become artifacts that help us get crucial information out from the pcaps.


<br>





## References**



- MalwareTrafficAnalysis.net exercise page



**Any malware research links**

- https://www.proofpoint.com/us/blog/threat-insight/are-you-sure-your-browser-date-current-landscape-fake-browser-updates#870527997
- https://threatfox.abuse.ch/ioc/1347180/
- https://socprime.com/active-threats/smartapesg-delivers-remcos/



&nbsp; 















