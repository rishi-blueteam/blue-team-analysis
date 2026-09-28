# Case 012 - Big Fish in a Small Pond 

## Case Overview 



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** 2024-09-04 - BIG FISH IN A LITTLE POND | 07-04-2026


**PCAP File Name:** 2024-09-04 - TRAFFIC ANALYSIS EXERCISE: BIG FISH IN A LITTLE POND



**Traffic Time Range:** 2024-09-04 17:32:31 PM


**File Link:** https://www.malware-traffic-analysis.net/2024/09/04/index.html



**Suspected Malware Family (if known):** 



**Analysis Tool(s):** Wireshark



<br>





## Scenario Summary

LAN segment details:

- LAN segment range:  172.17.0[.]0/24 (172.17.0[.]0 through 172.17.0[.]255)
- Domain:  bepositive[.]com
- Active Directory (AD) domain controller:  172.17.0[.]17 - WIN-CTL9XBQ9Y19
- AD environment name:  BEPOSITIVE
- LAN segment gateway:  172.17.0[.]1
- LAN segment broadcast address:  172.17.0[.]255

### Background

Reviewing the alerts in your network environment, you find indicators that a host within your environment has been infected with malware.

<br>



## Environment \& Initial Observations



**Internal IP range:** 172.17.0[.]0 through 172.17.0[.]255



**Suspected victim IP:** 172.17.0.99



**Notable protocols observed:**



**Timezone used for analysis:** UTC



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Vitcim Name, Device Name, User Agent, IP Address, MAC Address

**Answer**

- Victim Name : Afletcher
- Device Name : WIN-CTL9XBQ9Y19<20> (Server service)
- IP-Address  : 172.17.0.17
- MAC Address : 00:23:ae:50:ba:fd
- User Agent  : Microsoft NCSI




<br>



### Level 2 – Intermediate Level**



**Question** Any important IOC or website etc


**Answer:** 

- **URL**: hxxps://www[.]bellantonicioccolato[.]it/
- **IP Address**: 46[.]254[.]34[.]201

![Image Site]()

![Virus Total for bellatonic website]()

![Cisco Talo Intelligence Website Rating]()

<br>

**IP-2:** 79.124.78.197

![infomration about the IP-2]()




### Level 3 – Basic Findings



**Question**



**Answer**



<br>



## Wireshark Filters Used






<br>



## Indicators of Compromise (IOCs)

- Any Domains

- User Agents

- IP-ADDRESS

- RE-Directs



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



- Screenshot Link

&nbsp; 















