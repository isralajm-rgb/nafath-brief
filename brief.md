Version: NAFATH-V1

Track: Cybersecurity

## Overview
A national digital login service allows citizens to access multiple government services using one account, making security and privacy essential. OpenID Connect supports identity verification, while AI can help identify unusual login activity but must be tested and monitored for errors and bias. Android permissions limit an app’s access to sensitive device features and data. DNS over HTTPS protects DNS queries in transit, although it does not secure every part of a user’s online activity. Phishing-resistant authentication helps prevent attackers from stealing login credentials through fake websites. Data protection requirements also guide how citizens’ personal information is collected, stored, and used. These six areas must work together to provide a service that is trustworthy, accessible, and secure. For the Cybersecurity track, a key question is which authentication methods can resist phishing attacks. 
## Software
OAuth 2.0 and OpenID Connect have different purposes. OAuth 2.0 allows an application to obtain limited access to resources with the user's authorization. OpenID Connect adds an identity layer to OAuth 2.0, allowing an application to verify the user's identity through an ID Token. For a national login service, OpenID Connect supports user authentication, while OAuth 2.0 supports delegated access to resources.

Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html
## AI
Before using AI to flag suspicious logins, the authority should manage risks throughout the model's lifecycle. The NIST AI Risk Management Framework provides four functions: Govern, Map, Measure, and Manage. The authority should assess false alarms, missed attacks, bias, and the quality of its data. It should test the model before deployment, monitor performance over time, and provide human review for high-impact decisions.

Resource: NIST AI RMF Playbook - https://www.nist.gov/itl/ai-risk-management-framework/nist-ai-rmf-playbook
## Mobile
Android runtime permissions allow users to decide whether an app can access certain sensitive data or device features. An app should request a runtime permission when it needs access to a feature protected by that permission, and it must handle denial appropriately. A national login app should request only permissions needed for its functions. Minimising unnecessary access reduces privacy risks and limits the potential impact of a compromised app.

Resource: Permissions on Android - https://developer.android.com/guide/topics/permissions/overview
## Networking
DNS over HTTPS (DoH) sends DNS queries and responses through HTTPS, helping protect them from being read or modified by parties monitoring the network path. For users accessing a national login service, this can make DNS activity harder for local network observers to inspect. However, DoH does not hide all browsing activity, prevent phishing by itself, or replace HTTPS protection for the login website.

Resource: RFC 8484: DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484.html
## Cybersecurity
Phishing-resistant MFA is MFA that a fake login page cannot capture and reuse, unlike a typed one-time code. CISA names FIDO/WebAuthn and PKI-based MFA, such as smart cards, as phishing-resistant. Authenticator-app one-time passwords and number-matching push are still phishable, push without number matching is open to push bombing, and SMS or voice codes are vulnerable to phishing, SS7 and SIM-swap attacks. These methods do not qualify.

Resource: Implementing Phishing-Resistant MFA (CISA fact sheet) - https://www.cisa.gov/sites/default/files/publications/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf

Resource: NIST SP 800-63B, Authentication and Authenticator Management - https://pages.nist.gov/800-63-4/sp800-63b/authenticators/ 
## Data
Oman's Personal Data Protection Law establishes requirements for handling personal data. For a national login service, the authority should identify a lawful basis for processing, explain how data will be used, obtain consent where required, and protect stored information against unauthorised access. It should also follow applicable rules on individuals' rights, data retention, and disclosures. The authority must verify the law and its executive regulations before defining its procedures.

Resource: Oman Personal Data Protection Law, Royal Decree 6/2022 - https://qanoon.om/p/2022/rd20220006/
## Misconception in My Track
A common misconception is that all multi-factor authentication (MFA) methods are equally resistant to phishing. However, SMS codes and app-generated one-time passwords can be intercepted through phishing when users enter them on fake login pages. CISA identifies FIDO/WebAuthn as the only widely available phishing-resistant authentication method and also describes PKI-based MFA for suitable environments. This shows that adding a second factor does not automatically prevent phishing; the authentication method itself matters.

Resource: Implementing Phishing-Resistant MFA - https://www.cisa.gov/sites/default/files/2023-01/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf
## Open Question
“How does Article 3(b) of Oman's Personal Data Protection Law apply to a national digital identity service operated by a government authority, and what safeguards govern citizens’ personal data if the processing falls outside the Law’s direct scope?”
