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



**Notable protocols observed:** 



**Timezone used for analysis:**



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Details of the Victim (Hostname, IP , MAC Address, Windows Username)


**Answer** 

- **Hostname**: DESKTOP-B8TQK49<00> (Workstation/Redirector) (Intel)
- **IP Address of Host**: 10[.]11[.]26[.]183
- **MAC Address:** d0:57:7b:ce:fc:8b
- **Windows Username:** oboomwald


<br>



### Level 2 – Intermediate Level**



**Question** Supected Domain & IP Address

**Answer:** 

- hxxp://modandcrackedapk[.]com (193[.]42[.]38[.]139)
- hxxp://confirmsubscription[.]com (13[.]56[.]30[.]207)
- hxxp://geo[.]netsupportsoftware[.]com/location/loca[.]asp (104[.]26[.]1[.]231)
  
![Possible Malware]()

![Another Possible Malware]()

![Url found in Malware site]()

**Redirected Site**

- confirmsubscription[.]com 13[.]56[.]30[.]207

![Redirected Site]()

- URL Found in redirected site

![Url found in Re-Directed Site]()

- Threat Score of Malware
![Threat Score of Re-Directed Site Malware]()


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

[Snort Alerts File]()



<br>



## Indicators of Compromise (IOCs)

Any Domains

- modandcrackedapk[.]com 
- confirmsubscription[.]com 
- geo[.]netsupportsoftware[.]com/location/loca[.]asp

User Agents

**IP-ADDRESS**

193[.]42[.]38[.]139
13[.]56[.]30[.]207
104[.]26[.]1[.]231


**RE-Directs**

confirmsubscription[.]com 

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



### What I would investigate further in a real SOC**

-



<br>





## References**



- MalwareTrafficAnalysis.net exercise page



Any malware research links

- 



- Screenshot Link

&nbsp; 















