# Lever.co ATS Abuse – Legitimate Email, Malicious Intent (Nov 2025)

## Summary
Received a fully authenticated job-offer email from Lever.co (SPF/DKIM/DMARC all pass) that linked to a fake background-check phishing site. The attack succeeded because the scammer created or compromised a real Lever employer account – not by spoofing email.

## Key Findings
- Email originated from official Lever/Mailgun IP 159.112.248.213  
- Valid DKIM signature (d=hire.lever.co)  
- Reply-To used standard Lever tracking address  
- Fraudulent employer: “Angelique Horizons LLC”  
- Phishing domain: mandatorybackgroundverification.com (unrelated third-party)

## Indicators of Compromise (IOCs)
- Phishing URL: hxxps://mandatorybackgroundverification[.]com/  
- Lever Reply-To UUID: 5a19516a-e437-408a-a3d9-815b0997ca01  
- Fake company name variations: Angelique Horizons LLC, Angelique Horizons

## Scale of the Campaign
- Received 6 near-identical messages within 60 seconds from the same fraudulent Lever account
- Minor variations only in subject line and UUID in Reply-To header
- Indicates automated mass-mailing to all applicants of the fake job posting

## Lessons Learned
Perfect email authentication no longer guarantees legitimacy when attackers abuse legitimate ATS platforms. Background checks should never require candidates to visit random third-party sites or pay upfront fees.

## Evidence (redacted)
- Full headers saved in this repo: `/2025-11-Lever.co-Job-Scam/headers.txt`  
- Screenshots stored in `/2025-11-Lever.co-Job-Scam/screenshots/`

This incident demonstrates practical phishing triage and why account-level abuse of trusted platforms is the current dominant job-scam vector in 2025.
