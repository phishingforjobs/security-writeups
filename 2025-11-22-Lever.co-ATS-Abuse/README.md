# Lever.co ATS Abuse – Legitimate Email, Malicious Intent (Nov 22, 2025)

## Summary
Received a fully authenticated next-stage interview email from Lever.co (SPF/DKIM/DMARC all pass) that linked to a fake background-check phishing site. The attack succeeded because the scammer created or compromised a real Lever employer account – not by spoofing email.

## Key Findings
- Email originated from official Lever/Mailgun IP 159.112.248.213  
- Valid DKIM signature (d=hire.lever.co)  
- Reply-To used standard Lever.co tracking address  
- Fraudulent employer: “Angelique Horizons LLC”  
- Phishing domain: hxxps://mandatorybackgroundverification[.]com (unrelated third-party)
- Phishing domain currently online (as of Nov 24, 2025)
- **Candidate never applied to any Angelique Horizons posting** — the fraudulent job was advertised under a different title/company name on FlexJobs solely to harvest applicant data for this phishing campaign

## Indicators of Compromise (IOCs)
- Phishing URL: hxxps://mandatorybackgroundverification[.]com/
- Lever Reply-To UUID: 5a19516a-e437-408a-a3d9-815b0997ca01  
- Fake employer name: Angelique Horizons LLC (and variations)

## TTPs & Red Flags (Tactics, Techniques, and Procedures)
- Requests mandatory “background verification” via third-party site before any interview
- Uses urgent language (“shortlisted for the interview stage”)
- Refers vaguely to “the remote position” instead of the actual job title applied for
- Sends multiple near-identical emails within seconds (automated mass-mailing)

## Scale of the Campaign
- Received 6 near-identical messages within 60 seconds from the same fraudulent Lever account
- Minor variations only in subject line and UUID in Reply-To header
- Indicates automated mass-mailing to all applicants of the fake job posting

## Lessons Learned
- Perfect email authentication no longer guarantees legitimacy when attackers abuse legitimate ATS platforms
- Background checks should never require candidates to visit random third-party sites or pay upfront fees
- Always verify the hiring company’s real domain and official career page before clicking any “verification” links

## Evidence (redacted)
- Raw email headers: [headers.txt](headers.txt)
- 6 similar emails, one selected: ![Inbox + email body](screenshots/01-inbox+email.png)
- Phishing site appears in Google search: !["mandatory background verification" search](screenshots/02-google-listing-phishing-domain.png))
- Phishing site landing page (captured 2025-11-25 via VPN-protected private tab; full content observed at time of visit, including TransUnion impersonation and $29.95 fee prompt):
  ![Phishing landing page – full scroll](screenshots/03-phishing-landing-page-full.png)

This incident demonstrates practical phishing triage and why account-level abuse of trusted platforms is the current dominant job-scam vector in 2025.
