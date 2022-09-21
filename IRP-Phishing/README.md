# Phishing Playbook

[[_TOC_]]

## Scope
This Playbook covers

## 1. Preparation

<details>
<summary>Expand/Colapse</summary>

- Create and maintain a list of 
    - all domains owned by Company.
        - This can prevent you from taking actions against our own domains
    - all people of can register domains
- Create email template 
    - to notify all employees of ongoing phishing campaing against the organization 
    - to contact hosting companies for domain take down
    - to inform 3rd party to take actions against phishing on there infra (Microsoft, Fedex, Apple, etc.)
- Ensure that:
    - Mail anti-malware/anti-spam/anti-phish solutions are in place.
    - Users know how to report phish
    - Detection exists for office documents spawning processes
        - PowerShell
        - CMD
        - WMI
        - MSHTA
        - Etc.
- Perform Firedrill to ensure all aspects of the Playbook are working
    - After publication
    - At least once a year
    - Test/Validate: 
        - [Customer's Cards](Customers)
        - Internal Contact and Escalation Paths
- Review threat intelligence for 
    - threats to the organisation, 
    - brands and the sector, 
    - common patterns 
    - newly developing risks and vulnerabilities
- Ensure  appropriate  access  to  any  necessary  documentation  and  information, including out-of-hours access, for the following
    - IR Playbgns to highlight information security risks faced by employees, including: 
    - Phishing attacks and malicious emails;
    - Ransomware;
    - Reporting a suspected cyber incident.

### Tool Access and Provisioning

#### Tool1
Please referer to [Tool1 Documentation](../Products/TOOL.md)

#### Tool2
Please referer to [Tool2 Documentation](../Products/TOOL.md)

### Assets List
- A list of assets and owner should exists and be available for the following
    - Customers Assets
        - Owners
        - Contacts
        - Pre authorized actions
    - Company Assets (Including all filiale and business units)
        - Owners
        - Contacts
        - Administrators
        - Pre autorized actions
- Type of assets inventory needed
    - Endpoints
    - Servers
    - Network Equipements
    - Security Appliances
    - Network Ranges
        - Public
        - Private
        - VPN / Out of Band
            - Employees
            - Partners
            - Clients

</details>

## 2. Detect
<details>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Phishing Workflow](Workflows/Phishing-Workflow-Detect.png)

</details>

### Identify Threat Indicators
<details open>
<summary>Expand/Colapse</summary>

#### Alerts
Alerts are be generated by differents systems owned by the Security/SOC team. The main sources for alerts are  
- Tickets
- SIEM 
- Anti-Virus / EDR
- Reports
    - DNS
    - Web Proxy
- Errors from mail servers

#### Notifications
Notifications are comming from external sources usually via email, Teams or phone. The main sources for notifications are  
- Users (internal)
- Recipents of emails (external)
- Third Parties
- ISP
- Mail Providers

</details>

### Indentify Risks Factors
<details open>
<summary>Expand/Colapse</summary>

#### Common
- Credential Theft
- Malware Delivery
- Criminal Activites
    - Blackmail / Ransom

#### Company Specific
- Financial Losses
    - Lost of conctrat
    - Contract not renewed
    - Lower bid to our clients
    - Fines
        - Regulation

</details>

### Data Colletion
This section describe the information that should be collected and documented about the incident  
There is a lot of ressources to help you with that phase [here](../Tools/README.md)
<details open>
<summary>Expand/Colapse</summary>

Domains  
- Reputation
- Registrar
- Owner
- IP
- Multistage / Redirect
- Technologies of the site
    - WordPress
    - Joomla
    - Custom Page (credential phish)

IP  
- Reputation
- Owner
- Geo Localisation
- Other domains on that IP

</detials>

### Categorize
<details open>
<summary>Expand/Colapse</summary>

Determine type of email
- Phish
    - Company Site rip-off
    - Common brand
        - Apple
        - FedEx
        - Netflix
        - Etc.
    - Company 3rd Party
        - O365
        - Other Cloud base solutions
- Spear Phish
- Whaling
- Spam
- BEC
- O365 Forward Rules

</details>

### Triage 
<details open>
<summary>Expand/Colapse</summary>

Determine
- Impact
    - Of the message
    - Financial
    - Data loss
- Scope (Nb of people)
    - Recieved the message
    - Opened the attachments
    - Clicked on the links
    - Submitted information

</details>
</details>
</details>

## 3. Analyze
<details open>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Phishing Workflow](Workflows/Phishing-Workflow-Analyze.png)

</details>

### Verify
<details open>
<summary>Expand/Colapse</summary>

In conjonction with a senior member of the SOC  
- Double check previous datsa
- Rule out False Positive

</details>


### Identify IOCs
<details open>
<summary>Expand/Colapse</summary>

- Validate hashes
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](Tools/README.md#hybrid-analysis)
- Validate links
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](../Tools/README.md#hybrid-analysis)
    - [URLScan](../Tools/README.md#urlscan)
- ID subject, attachments, from addr
- ID other addresses, domains, IPs
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](../Tools/README.md#hybrid-analysis)
    - [Talos Intelligence](../Tools/README.md#hybrid-analysis)
- Search Threat Intel sources
    - [VirusTotal](../Tools/README.md#virus-total)
    - [Hybrid Analysis](../Tools/README.md#hybrid-analysis)
    - [Talos Intelligence](../Tools/README.md#hybrid-analysis)
- Disk forensics on recipient's endpoint

</details>

### Scan Enterprise
<details open>
<summary>Expand/Colapse</summary>

- Update spam filter
- Update FW, IDS, etc. rules w/ IOCs
- Search all mail forders for IOCs
- Search endpoints for IOCs w/ EDR

</details>

### Update Scope
<details open>
<summary>Expand/Colapse</summary>

- Update lists of
    - affected recipient addresses
    - affected endpoints
    - affected enclaves
    - affected business units

</details>

### Update Scope
<details open>
<summary>Expand/Colapse</summary>

- Update lists of
    - affected recipient addresses
    - affected endpoints
    - affected enclaves
    - affected business units

</details>

### Scope Validation
<details open>
<summary>Expand/Colapse</summary>

Have all the machines been identified? 
If you find futher traces of phishing or new IOCs go back through this step.  

When you are done identifying all compromised:  
- Hosts
- Mailboxes

And investigated all:  
- URLs
- Domains
- IP
- Ports
- Files
- Hash

Go to the next phase <Contain/Eradicate>

</details>

</details>


## 4. Contain / Eradicate
<details open>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Phishing Workflow](Workflows/Phishing-Workflow-Contain_Eradicate.png)

</details>

### Block
<details open>
<summary>Expand/Colapse</summary>

- Update Spam Filters
- Update FW, Proxy, etc. rules
- Blackhole DNS
- Submit to thrid parties
    - [Google Safe Browsing](https://safebrowsing.google.com/safebrowsing/report_general/)
    - Web Filter Vendor
    - etc.

</details>

### Validate User's Actions
<details open>
<summary>Expand/Colapse</summary>

- Have emails been read
- Have attachments been opened
- Have links been clicked

</details>

### Malware Infection?
<details open>
<summary>Expand/Colapse</summary>

If there was malicious attachments that were openned we need to assume the endpoint(s) was/were infected by a malware.  
Please continue to the [Malware Playbook](../IRP-Malware/README.md)  

</details>

### Delete Emails
<details open>
<summary>Expand/Colapse</summary>

- Delete From Users' Inboxes
    - Spam Tool
    - Email Admin Console
    - Cloud & On-Prem
- Delete Downloaded Attachments
    - EDR, SIEM, etc. to scan enterprise

</details>

### Close Monitoring
<details open>
<summary>Expand/Colapse</summary>

- Monitor for 
    - Related incoming messages
    - Internet connections to IOC
    - New files that matches hashes identified

</details>


### All Affected Endpoints Contained?
<details open>
<summary>Expand/Colapse</summary>

If all affected endpoints have been contained, you can go to the next phase, otherwise continue bellow.  

</details>

### New IOC Discovered?
<details open>
<summary>Expand/Colapse</summary>

If there was new IOC discovered, go back to the [Analyze Phase](README.md#3-analyze)
</details>
</details>

## 5. Recover
<details open>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Phishing Workflow](Workflows/Phishing-Workflow-Recover.png)

</details>

### Update Defenses
<details open>
<summary>Expand/Colapse</summary>

Determine which of the following rules needs to be removed and which needs to stay in the following list:  
- Spam Filters
- Firewall Rules
- EDR 
    - ban hashes
    - ban domains
    - Containment
- Proxy Block

</details>

### All Affected Endpoints Recovered?
<details open>
<summary>Expand/Colapse</summary>

If all affected endpoints have been contained, you can go to the next phase, otherwise continue bellow.  

</details>

### Validate Countermeasures
<details open>
<summary>Expand/Colapse</summary>

Determine if legitimate elements are blocked by:  
- Spam Filters 
- Proxy
- Firewall
- EDR

If so, go back to [Update Defenses](README.md#update-defenses)
Otherwise go to the next phase <Post Incident>

</details>
</details>

## 6. Post Incident
<details>
<summary>Expand/Colapse</summary>

### Workflow
<details open>
<summary>Expand/Colapse</summary>

![Phishing Workflow](Workflows/Phishing-Workflow-Post%20Incident.png)

</details>

### Incident Review
<details open>
<summary>Expand/Colapse</summary>

- What worked
- What didn't work

</details>

### Update Mode of Operations
<details open>
<summary>Expand/Colapse</summary>

Update the following documents as requiered:  
- Policies
- Processes
- Procedures
- Playbooks
- Runbooks

Update Detetion Rules in:  
- SIEM
- Anti-Spam
- Malware Gataway
- EDR
- Other security solution

</details>

### Review Defensive Posture
<details open>
<summary>Expand/Colapse</summary>

- Schedule review of newly introduced rules in6 months
- Are the following still applicatble
    - Spam Filter Rules
    - Firewall Rules
    - Proxy Rules for C2
    - AV / EDR custom Signatures
    - IPS Signatures

</details>

### User Awareness Training
<details open>
<summary>Expand/Colapse</summary>

- Ensure that the user receives Phishing training
    - How to recognize Phish
    - How to report Phish
    - Danger of following links
    - Danger of opening attachments
    - Danger of compliying with scammers requests

</details>

</details>

# References

This Playbook was built using the following references:  
https://www.dfir.training/index.php?option=com_jreviews&format=ajax&url=media/download&m=14tt1&1600804844570  
https://www.gov.scot/publications/cyber-resilience-incident-management/  
https://github.com/certsocietegenerale/IRM/tree/master/EN  
https://www.incidentresponse.com/playbooks/  
https://ayehu.com/cyber-security-incident-response-automation/top-5-cyber-security-incident-response-playbooks/  
https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf  