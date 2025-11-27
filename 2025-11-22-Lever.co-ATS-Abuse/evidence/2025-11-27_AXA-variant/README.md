# Lever.co ATS Abuse – Campaign Variant: AXA Impersonation (27 Nov 2025)

## Summary
Received a second fully authenticated phishing email sent through Lever’s legitimate Mailgun infrastructure (SPF/DKIM/DMARC all pass). The message impersonates “AXA Philippines Paragons Branch” and directs the victim to the exact same phishing site used in the 22 Nov 2025 campaign (hxxps://mandatorybackgroundverification[.]com). This confirms an ongoing, modular campaign abusing real Lever customer accounts.

## Key Findings

- Email originated from the same Lever/Mailgun IP range (159.112.248.213) as the previous incident
- Valid DKIM signature (d=hire.lever.co, selector mx)
- Lever tracking redirect used: t.lever-analytics.com → mandatorybackgroundverification[.]com
- Fraudulent employer: “AXA Philippines Paragons Branch” (no relation to real AXA entities using Lever)
- Phishing domain identical to the 22 Nov campaign: hxxps://mandatorybackgroundverification[.]com/
- Candidate never applied to any AXA-related posting

## Indicators of Compromise (IOCs) – Shared with 22 Nov Incident

- Phishing domain: hxxps://mandatorybackgroundverification[.]com/ (same endpoint)
- Lever Reply-To UUID: 8f432bb2-dc0c-4038-be3b-fb552c2551c3
- Fake employer name: "AXA Philippines Paragons Branch"
- Lever tracking redirect token: ef675a00-b431-4bbf-9180-4738c8a54012

## TTPs & Red Flags (Consistent with Campaign)

- "Mandatory background verification" pretext before interview scheduling
- Urgency phrasing: “Before we can finalize your scheduling” and "shortlisted applicants"
- Lever tracking link used to mask the final malicious destination
- Generic signature (“Regards, Axa”) – no recruiter name or contact
- Re-uses the identical phishing landing infrastructure

## Scale of the Campaign – Updated

- At least two distinct fake employer accounts confirmed (Angelique Horizons LLC + AXA Philippines Paragons Branch)
- Both funnel victims to the same disposable phishing domain
- Indicates a single actor (or closely coordinated group) rotating employer identities while keeping the back-end infrastructure constant

## Lessons Learned (Reinforcement)

- One malicious domain appearing under multiple unrelated “employers” is a strong indicator of coordinated ATS abuse
- Lever tracking redirects (t.lever-analytics.com) can be weaponized by any customer account – legitimate authentication ≠ legitimate intent

## Evidence (redacted)

