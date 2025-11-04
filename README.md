# Threat-Intelligence
This repository holds information about my threat intelligence project on Globe Media News (Globe Media News is a Decoy name used for a real website in order to protect the information of the original company). This project displays usage of different tools to carryout threat intelligence.


### Globe media News (portal.globemedia.news) is a globally trusted media outlet facing rising risks of credential harvesting and misinformation sites masquerading as official subdomains. They’ve commissioned us the C25-03 team, an in‐house OSINT team for a passive reconnaissance engagement to map their external footprint, identify any “stale” or forgotten assets, and provide an executive summary of our findings.


### Scope and Rules of Engagement

- Target domain: portal.globemedia.news and subdomains
-	Passive only: no vulnerability scans, brute‐force, password trials
- Signed “OSINT Rules of Engagement & Checklist” (see image 1ai: [OSINT RULE](https://raw.githubusercontent.com/FaithOnosoneTech/Threat-Intelligence/ce9854de683230994b2507323da7b6d89eac9cb2/1ai..png) and image 1aii: [Signed CHECKLIST](https://raw.githubusercontent.com/FaithOnosoneTech/Threat-Intelligence/ce9854de683230994b2507323da7b6d89eac9cb2/1aii..png)


### Discovery Using Google Dorks
- URL list with dork used =  `Site: portal.globemedia.news “Interesting URL”` (see image 2ai: [Interesting URL](https://raw.githubusercontent.com/FaithOnosoneTech/Threat-Intelligence/d7b519f340c1ab9ad5851705c080e70fa839bf32/2ai..png))

  
### Discovery Using Harvester And Shodan

- **TheHarvester**: enumerate subdomains & any public e‐mail patterns: This was done in the terminal of Kali VM using the command: ***`theHarvester -d portal.globemedia.news -b all --shodan -l 1000 -f portal.globemedia.news.txt`*** (see images 3ai: [Output](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/3ai..png?raw=true)  & 3aii: [Subdomains and Public E-mails](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/3aii..png?raw=true))

- **Shodan free** to pull IP, port, and banner data: This was done by searching `portal.globemedia.news` on www.shodan.io on search engine (see images [3bi](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/3bi..png?raw=true), [3bii](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/3bii..png?raw=true), [3biii](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/3biii..png?raw=true) & [3biv](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/3biv..png?raw=true) for results).


### Maltego Visualization
- Import domain/IP list into Maltego Community Edition
•	Graph relationships: `Domain ↔ IP ↔ any harvested e‐mail artifacts`
•	Exported graph image (PNG) (graph image not uploaded as it contains company's vital information)


### Validation
-	DNS lookup / ping each subdomain (15) generated via the harvester using the command:
    - ***`nslookup subdomain`*** (see images [4ai](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/4ai.png?raw=true) & [4aii](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/4aii..png?raw=true) for result)
    - ***`ping -c -4 subdomain`*** (see images [4ai](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/4ai.png?raw=true) & [4aii](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/4aii..png?raw=true) for result).

    or

    do this by first saving the entire subdomains in a file via nano using python code. Then run the commands:
 	
    ***`nano check_domains.sh`***  and
 	
    ***`./check_domains.sh > portal.globemedia.news-subdomains results.txt`***

- Discover and Mark entries as `“Live” vs. “Stale/Unresolved”` (see screenshots [4bi](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/4bi..png?raw=true) & [4bii](https://github.com/FaithOnosoneTech/Threat-Intelligence/blob/main/4bii..png?raw=true) for result)
    

    

    





















