# Practical - 8 : HELPING OUT AN INEXPERIENCED ANALYST


## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** Practical 8: HELPING OUT AN INEXPERIENCED ANALYST


**PCAP File Name:** 2015-02-24-traffic-analysis-exercise




**Traffic Time Range:** 2015-02-24 | 04:04:08 AM GMT



**File Link:** https://www.malware-traffic-analysis.net/2015/02/24/index.html



**Suspected Malware Family (if known):**



**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary

It's another evening shift at your organization's Security Operations Center (SOC).  One of the analysts is looking through some traffic that occurred while your snort-based Intrusion Detection System (IDS) was off-line.  The traffic had triggered a non-specific alert of possible malicious activity from another IDS.

The analyst is relatively new and is not experienced with malicious traffic.  That analyst asks you for help.


### Requirement

You review the pcap and document the following:

- Date and time of the activity
- IP address of the associated desktop (or laptop) computer
- Host name of the associated desktop (or laptop) computer
- MAC address of the associated desktop (or laptop) computer
- Brief summary of the activity



<br>



## Environment \& Initial Observations


**Suspected victim IP:** 10.10.100.139



**Notable protocols observed:**



**Timezone used for analysis:** 



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Date and time of the activity


**Answer** Tue, 24 Feb 2015 04:06:15 GMT


**Question-2:** IP Address, MAC Address, Host Name of the Associated device



**Answer**  10.10.100.139| 28:92:4a:3b:5f:cd (HewlettPacka_3b:5f:cd) | STEPHANIE-PC<00> 


<img width="1914" height="928" alt="NBNS and required INformation" src="https://github.com/user-attachments/assets/ca033f9c-70d3-41bb-8132-1cc5d5ede420" />


----------------------------- 


### Extra Findings Observations

**Site compromised:** www[.]legacylifespaces[.]com

![Compromised Website](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Compromised%20Website.png)

![Redirect Seen of Compromsied Wesbite](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/Phishing%20Analysis/Screenshots/Analysis%208/Compromised%20Website%20First%20Re-Direct.png)

**Malacious Website:** hxxp://mpzfprxfdn[.]serveftp.com/tdstest/1b346b77c2e9991535ede3925f5463e598/



**EK Found:** SilverFlash


After the user has been on the same site for a while he ends up coming across another malware:

**EK Found:** 


PDF Found


2. 
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
















