<h1> E-Mail Analysis Tool </h1> 

<p> Developed a Python-based parser to extract sender details, IP addresses, message IDs, and attachments from email headers. Automated IOC extraction and implemented IP defanging for safer analysis. Used AI-assisted development to accelerate scripting and focused on customizing logic and testing against real samples. </p>

<h2>E-Mail Analyzer Tool Features</h2>

1. Basic Information Extracter
2. Header Analysis
3. Threat Intelligence

<h3> 1. Basic Information Extractor</h3>

- From and To Address Parser
- Reply-To extractor
- Date of Message Delivery
- IP Extraction (To and From)
- Subject extractor
- Message-ID extractor
- Attachment existing or no?

<h3> 2. Header Analysis </h3>

* DKIM Analysis
* SPF Analysis
* DMARC Analysis
* Originating IP sOURCE:

<h3> 3. Threat Intelligence </h3>

**3.1 URL:**

* URL Extraction and Defang
* WhoIsLookup
* Domain Age Check
* URL Reputation

**3.2 IP Check**

* IP reputation check
* GeoIP location
* ASN lookup

**3.3 Attachment Analysis**

* Attachment Name
* Attachment Type (ZIP, PDF, Double Extension, HTML, eml, etc)
* Attachment Hashes
* Hash Threat Score Detection
* Password Protected Achieve Detection


