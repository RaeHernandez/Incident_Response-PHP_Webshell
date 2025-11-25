# Incident Response Case Study: PHP Web Shell Remediation

## Overview
- Real-world malware incident handled during internship  
- PHP web shell discovered in a WordPress plugin  
- Skills: detection, analysis, remediation, verification, hardening

## Detection
- SiteGround alert identified a new unauthorized PHP file: `/wp-content/plugins/wp-compat/wp-compat.php`  
- **Screenshot placeholder:** alert header (redacted)

## Indicators of Compromise (IOCs)
- Unexpected new file inserted  
- Obfuscated PHP code (`eval`, `base64_decode`)  

## Analysis / MITRE
- Persistent web shell → T1505.003  
- Unauthorized admin access → T1078  
- File modification & hiding → T1564  

## Remediation & Verification
- Removed malicious file and reinjection code  
- Updated WordPress core, plugins, and themes  
- Reset admin credentials  
- SiteGround confirmed malware removal  
- **Screenshot placeholder:** verification scan (redacted)

## Hardening & Prevention
- Plugin integrity monitoring implemented  
- Educated site owner on plugin hygiene and supply chain risk  

## Impact / Skills Demonstrated
- End-to-end incident response workflow: detection → analysis → remediation → verification → closure  
- Real-world vulnerability handling and APT-style response

## Repository Files
- `Incident Response Case Study_PHP Web Shell Remediation.pdf` – Full portfolio-ready report  


