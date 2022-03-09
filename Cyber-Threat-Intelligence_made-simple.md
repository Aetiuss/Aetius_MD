> This article is composed of the notes I have taken reading this paper:
> https://nsfocusglobal.com/wp-content/uploads/2017/01/SANS_Whitepaper_Threat_Intelligence__What_It_Is__and_How_to_Use_It_Effectively.pdf

---
# Cyber Threat Intelligence explained
A three step process.
## 1. Acquiring Knowledge
>**Gaining knowledge on the threats that could potentially target one organization through available data points**
- Your knowledge is acquired through on the field data related to intrusion
- The data can be collected through different data points
### Internal Threat Intelligence
- Data about incidents already underwent by the enterprise has to be collected
	- exploit kits
	- malware infections
	- other daily issues that could seem irrelevant
- Organizing it into meaningful content -> Profile of org environment 
- Can be collected on 
	- SIEM 
- Data corresponds to
	- System logs
	- Incident details
### External Threat Intelligence
- How to chose your sources
	- What is its data fidelity level ?
	- Can the org follow up with the intel provider ?
		- Frequency
		- Information types
		- Amount of context associated
	- How is the info provided ?
	- Is the info provided relevant to org/industry ?
	- Is info provided relevant to org operations ?
#### Data subscriptions/feeds
- Ex
	- Emails (hourly,daily,weekly,...)
	- Subscriptions providing indicators lists (JSON,CSV,...)
	- APIs with the help of scripts to extract info (Database,Website,...)
	- Special Release (Public report form provider,...)
	- Open-Source (OSINT,...)
#### Commonality 
- Ex
	- Industry groups (Information Sharing & Analysis Center ISAC, ...)
	- Geographic localization
#### Governmental and Law enforcement relations
- Ex
	- InfraGard =  partnership with FBI and the private sector to share info
	- Law enforcement can provide info but after evidence that breach has occurred in org
#### Crowd-sourced Platforms
- Hubs between multiple types of entities
- Can provide anonymous access
## 2. Determining your Relevant Threats (by finding the relations between Knowledge and your Organization)
>**To process the acquired knowledge you need to *find the relations* between it and your org by using contextual info=> relevant threats to your business**
### Combining External & Internal sources
- | External                      | Internal                   |
| ----------------------------- | -------------------------- |
| What you don't know           | What you know              |
| How you may be attacked       | How you have been attacked |
| What you should be protecting | What you are protecting    |
- Beforehand 
	- TI implementation defined
	- TI Sources identified
	- Expectations set
- Then make TI *actionable*
	- Incorporate into security posture
	- Use TI to help drive investigations/responses
	- Look into the past to possibly find things that were overlooked before TI (**Internal TI**)
	- Look into the future (**External TI**)
## 3. Actioning your knowledge of those Relevant Threats
>**Exploiting this knowledge on relevant threats to *act* (respond/combat/mitigate)**
### Incorporate TI into Security Posture
- Security Posture = what the business needs to protect 
	- -> policies/procedures/controls to implement
- TI will help org to identify 
	- areas which attackers are the most likely to target
	- potentially critical assets that were not considered as vulnerable

### Using TI to help drive Investigations & Response
- Incorporate it inside Incident Response IR team's daily activities
	- -> act on TI info to detect compromises & better protect environment
	- During incident -> better understanding of threat actor & how attack is conducted
### Using TI to look into the Future
- TI help teams identify changes in attacks and trends of attackers Tactics Technics and Procedures TTP
- Doing that will enable proactive actions
