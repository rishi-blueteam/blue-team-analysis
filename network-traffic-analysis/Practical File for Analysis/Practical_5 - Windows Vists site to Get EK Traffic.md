## Case Overview



**Source:** MalwareTrafficAnalysis.net



**Exercise Name | Date:** Windows Users Views a Website and get EK Traffic



**PCAP File Name:** 2015-01-09 - TRAFFIC ANALYSIS EXERCISE: WINDOWS USER VIEWS A WEBSITE AND GETS EXPLOIT KIT (EK) TRAFFIC



**Traffic Time Range:** 16:24:40 - 16:26:21



**File Link:** https://www.malware-traffic-analysis.net/2015/01/09/index.html 



**Suspected Malware Family (if known):** 



**Analysis Tool(s):** Wireshark



<br>



## Scenario Summary

Briefly describe the scenario provided in the exercise.Example: The traffic appears to originate from a Windows host communicating with external IPs, indicating a possible malware infection following a malicious email.



<br>



## Environment & Initial Observations



**Internal IP range:** 192[.]168[.]204[.]137



**Suspected victim IP:** 192[.]168[.]204[.]137



**Notable protocols observed:** frame,tcp,urlencoded-form,eth,http,ip



**Timezone used for analysis:** GMT



<br>



## Questions For Analysis



## Beginner Questions

### Question 1.1
What is the date and time of this activity?  

**Answer 1.1:** 2015-01-09 | 16:24:40 - 16:26:21

![Image of the Attack and activity taking place]()

---

### Question 1.2
What is the IP address and MAC address of the Windows host that hit the exploit kit?  

**Answer 1.2:** 

**IP-ADDRESS :** 192.168.204.137 | 00:0c:29:9d:b8:6d



---

### Question 1.3
What is the domain name and IP address of the compromised web site?  

**Answer 1.3:** www[.]opushangszer[.]hu/ | 94.199.178.119

![iMAGE OF Redirect 1,2 and final]()
![Iamge of the Site Compromsied Threat Score]()

---

### Question 1.4
What is the domain name and IP address of the exploit kit?  

**Answer 1.4:** http[:]//static[.]domainvertythephones[.]com/xEztiZ7NM12Vj9c2RTB_MT0UEYH_re0UqLWZq_vBhBZGq0KGVP1BTVXxVeSy3Veo | 167.160.46.121



---

### Question 1.5
What web browser is the Windows host using?  

**Answer 1.5:** Mozilla/4.0

![User Agent]()

---

## Advanced Questions

### Question 2.1
What is the exploit kit involved in this activity?  

**Answer 2.1:** SWF (Shockwave Flash) | application/x-shockwave-flash



---

### Question 2.2
What types of exploits were sent by this exploit kit (Flash, IE, Java, Silverlight, etc.)?  

**Answer 2.2:** Shockwave



---

### Question 2.3
Which HTTP request returned a redirect to the exploit kit?  

**Answer 2.3:** 

http\[:]//imprintchurch\[.\]org/d6bc1dc7da4ed54a62b93b5d0f1cc40c\[.\]swf



---

### Question 2.4
In Wireshark, which tcp.stream contains the malware payload?  

**Answer 2.4:** tcp.stream eq 4

---



### Question 2.5
What version of Flash Player is the Windows host using?  

**Answer 2.5:** x-flash-version: 11,8,800,94

---


## Wireshark Filters Used

- http.request
- http
- tcp.stream eq 0
- http.content_type


<br>



## Indicators of Compromise (IOCs)

**Any Domains** 

- https[:]//mawwzy[.]h0jlu3b[.]com/
- qf5z12cszk[.]ib1eciy.com
- KUWfbZtwrv[.]QGtvksAi[.]com
- oEFYbj3.HsYQTe[.]com
- NLP[.]YAD[.]com

**User Agents**

- Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Trident/4.0; SLCC2; .NET CLR 2.0.50727; .NET CLR 3.5.30729; .NET CLR 3.0.30729)

**IP-ADDRESS**

- 94[.]199[.]178[.]119
- 75[.]126[.]113[.]164
- 69[.]65[.]9[.]55
- 167[.]160[.]46[.]121

**RE-Directs**

- 75[.]126[.]113[.]164
- 69[.]65[.]9[.]55
- 167[.]160[.]46[.]121

**Site IOC**

> Compromised Site

- **MD5 :** d0b3a7ac076963f240f6764e787c11ab
- **SHA-1 :** 1654eb39f5ff864e5b88de2391e0b29263bf1433
- **SHA-256 :** 669e591741cd5d5aec0ba56c933d35ee314c0851e3df40da8f30c36dcea69479 

> Re-Directed Site Containing SWF

- **MD5 :** 7e41603c274aeac5ea1890125b5c1500
- **SHA-1 :** 7fcbfe94f3976187b644ca1e1bf8c826d85e3db6
- **SHA-256 :**  3f3e30467aec8b71feecfd47517de059ab390b605ab16f9d227dc26fa454969f


> Another Re-Directed Site 

- **MD5 :** 20635b6c3cdc7ddc39908665b7aa52fb 
- **SHA-1 :** a17ce7555514d2f60c76ff743e8770bbdbcaefd1
- **SHA-256 :** b4d8b9886fb5cf940661203594df132212d6f1ee17c726444531ec2b281096c2


>Exploit Kit Site Landing Page

- **MD5 :** 17c138ae1dc10d3ff9bbecac48b36f37 
- **SHA-1 :** c15b01eac7fa491d5c1ceb449cca14ac1a11f4db
- **SHA-256 :** 
05673074808f29ae69d05176645fb13484a33975ed29b9578e33f44220f1c392 


<br>


## Key Takeaways \& Learning**



### What I learned from this analysis**

**SWF:** 

<p>The SWF extracts several dynamic parameters (including a target URL, IP, user agent, and an additional URL) from its loaderInfo.parameters. It then constructs an HTTP POST request to the extracted target URL, sending the IP, user agent, and the additional URL as POST data. Finally, it navigates the browser to this URL, potentially opening a new window/tab with an obfuscated target name. This code functions as a flexible redirector or beacon, highly suggestive of use in malvertising or exploit kit delivery chains due to its dynamic external control and data exfiltration. </p>


- Identifying the redirect, identifying the final host, identifying the type of malware and Trojan is an essential case because that matters how you find and what methodlogies you use to track it down.

- Going in deep to extract the various URL embedded in the site helps us know what we are looking for. 


### Mistakes or confusion faced


- Choosing the right value, to inspect matters, and just overview prediction does not matter. Often seeing overview in a site you may definetly take the call saying that 


### New Wireshark techniques used

- N/A for this analysis



### What I would investigate further in a real SOC

- Real soc perspective is where I should rather try to decode what the Malware is all about the behaviour analysis of how the system behaves w.r.t to the malware.


<br>





## References



- MalwareTrafficAnalysis.net exercise page



- Any malware research links (if used)



- Screenshot Link

&nbsp; 















