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



**Notable protocols observed:** UDP, HTTP, NBNS, DNS, TLS, SSL



**Timezone used for analysis:** UTC



<br>



## Questions For Analysis



### L1- Basic Level Questions



**Question-1:** Date and time of the activity


**Answer** Tue, 24 Feb 2015 04:06:15 GMT


**Question-2:** IP Address, MAC Address, Host Name of the Associated device



**Answer**  10.10.100.139| 28:92:4a:3b:5f:cd (HewlettPacka_3b:5f:cd) | STEPHANIE-PC<00> 


![NBNS and Required INformation](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/NBNS%20and%20required%20INformation.png)

----------------------------- 


### Extra Findings Observations

**Site compromised:** www[.]legacylifespaces[.]com

![Compromised Website](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Compromised%20Website.png)

![Redirect Seen of Compromsied Wesbite](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Compromised%20Website%20First%20Re-Direct.png)

**Malacious Website:** hxxp://mpzfprxfdn[.]serveftp.com/tdstest/1b346b77c2e9991535ede3925f5463e598/

![Malacious Website Preview](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Malacious%20Website.png)

**EK Found:** SilverFlash

After the user has been on the same site for a while he ends up coming across another malware:

![Silverflash EK Found](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Silverlightapp%20found%20in%20another%20site.png)

![Silverlight Flash Malware Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/hx-malware.png)

**EK Found:** Java JNPL File

![Java JNPL File Found](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Java%20Files%20Found%20Malware.png)

![Java JNPL File Found with threat score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Java%20Files%20Found%20Malware%20virustotal.png)


**EK Found in Other File Format:** PDF


![File of PDF Found in PCAP](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/PDF%20File%20Found.png)

![Preview of PDF](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/PDF%20File.png)

![pdf File Threat Score](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/PDF%20Virus%20Total.png)


**Another EK Found** Shockwave File Found

![Shcokwave File FLash](https://github.com/rishi-blueteam/blue-team-analysis/blob/main/network-traffic-analysis/Screenshots-per-Case/Practical%208%3A%20HELPING%20OUT%20AN%20INEXPERIENCED%20ANALYST/Shockwave%20File%20Observed%20from%20Malacious%20Site%20sub%20directory.png)



## Wireshark Filters Used

- https
- http
- dns
- tcp.stream
- nbns
- tcp





<br>



## Indicators of Compromise (IOCs)

**Any Domains**

- hxxp://mpzfprxfdn[.]serveftp.com/tdstest/1b346b77c2e9991535ede3925f5463e598/




<br>





## Key Takeaways & Learning**


### What I learned from this analysis**

> From this analysis I have learnt and explored a lot, as I have been able to analyze better, think better, identify various possible exploits, extract and exported them so that I can even learn about them and their scope of attack to the user they intended to target.


### Mistakes or confusion faced**

> I would not say mistake but I would say that I documented on another day but the mistake is a good analyst documents its findings on one day and not another. This does not only create consistency but this creates habit, and fast learning, understanding and makes the other senior analyst specially if used in escallation to read the details more better


### What I would investigate further in a real SOC**

> Further what I could explore is to go down to the scope of the attack speially the MITRE AT&CK Graph Work and even the Pyramid of Pain to notice the TTP to not just assume but better understand what exactly the attacker's mindset is.



<br>





## References**



- MalwareTrafficAnalysis.net exercise page



- Any malware research links (if used)



















