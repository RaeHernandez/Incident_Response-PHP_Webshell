# Incident Response Case Study: PHP Web Shell Remediation
## Overview
During my internship, I responded to a **real malware incident** detected on a WordPress site. The malicious PHP file demonstrated APT-style tactics including persistence, obfuscation, and potential privilege escalation. This case highlights my skills in detection, analysis, remediation, and web application security improvement.

## Technical Environment
- **CMS:** WordPress  
- **Hosting:** SiteGround  
- **PHP Version:** 7.x/8.x  
- **Tools:** SiteGround file manager, WordFence, browser devtools, grep search  
- **Frameworks:** MITRE ATT&CK mapping, vulnerability management  

## Detection / Alert
- **Trigger:** Received official SiteGround malware notification:  

> “Malicious code was detected on newly uploaded/edited files that are part of your website. The permissions of the detected files were changed automatically to prevent further infection. Files must be cleaned within 3 days to avoid suspension.”

- The alert identified a **new, unauthorized PHP file** in the plugin directory:  
  `/wp-content/plugins/wp-compat/wp-compat.php`  
- Redacted screenshots can show the **alert header and folder structure** without exposing company information.

## Indicators of Compromise (IOCs)
- **Unexpected new file inserted** in plugin directory  
- File permissions temporarily changed by hosting provider  
- Obfuscated PHP code (`eval`, `base64_decode`)  
- Unauthorized admin-level actions logged  

## Analysis
- Identified **persistent web shell** with reinjection mechanism.  
- **MITRE ATT&CK Mapping:**

| Behavior | Technique |
|----------|-----------|
| Obfuscated PHP web shell | T1505.003 – Web Shell |
| Persistence via plugin load hooks | T1547 – Boot or Logon Autostart Execution |
| Unauthorized admin access | T1078 – Valid Accounts |
| File modification & hiding | T1564 – Hide Artifacts |

## Remediation
1. Maintenance mode activated  
2. Full file & database backup  
3. Removed malicious plugin file & reinjection code  
4. Verified plugin integrity  
5. Updated WordPress core, plugins, themes  
6. Reset admin credentials  
7. Full scan for additional IOCs  

## Verification & Closure
- After remediation, the site owner requested a **SiteGround scan** to confirm removal.  
- SiteGround confirmed:  

> “We are happy to inform you that the recent site scan you have requested found NO malicious code on your website. The previously open malware case is now closed in our system.”

- This step demonstrates successful removal, validation, and closure of the incident.

## Hardening & Prevention
- Implemented **plugin integrity monitoring** and scheduled weekly scans  
- Educated site owner on **plugin hygiene** and **supply chain risk**  

## Impact
- Complete removal of malicious PHP payload  
- Restored site integrity & reduced attack surface  
- Applied structured incident response methodology similar to APT-style analysis  
- Skills highlighted: detection, analysis, remediation, reporting, and security hardening  

## Lessons Learned
- Structured incident response is critical in real-world environments  
- Mapping attacker behavior to MITRE ATT&CK improves analysis  
- Automated alerts aid early malware detection  
- Documentation and communication are key in remediation
