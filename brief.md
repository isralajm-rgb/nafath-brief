Version: NAFATH-V1

Track: Cybersecurity

## Overview
A national digital login service must combine security, privacy, and usability to earn citizens' trust. Six fields contribute to this goal. Software standards such as OpenID Connect support secure authentication across services. The Android app must follow the platform's permission model to limit unnecessary access to sensitive data. Networking protections such as DNS over HTTPS help protect DNS queries in transit. AI can flag suspicious logins, but its risks and accuracy must be assessed before deployment and monitored over time. Data protection requirements guide how citizens' personal information is handled. Cybersecurity controls, including phishing-resistant authentication, help defend the login process against account takeover. A weakness in any layer can expose citizens to risk and undermine confidence in the entire service. 
## Software
OAuth 2.0 is an authorization framework that allows third-party applications to obtain limited access to resources using access tokens. However, it does not define standard methods for providing information about a user's authenticated identity. OpenID Connect adds an identity layer on top of OAuth 2.0, allowing applications to verify a user's identity through an ID Token. For a national digital login service, OAuth 2.0 supports delegated access, while OpenID Connect provides the authentication layer.

Resource: OpenID Connect Core 1.0 incorporating errata set 2 - https://openid.net/specs/openid-connect-core-1_0.html
## AI
The NIST AI Risk Management Framework describes trustworthy AI as valid and reliable, safe, secure and resilient, accountable and transparent, explainable and interpretable, privacy-enhanced, and fair with harmful bias managed. For a login-risk model, this means testing for false alerts that lock out genuine citizens, assessing how attackers might evade detection, protecting login data, and assigning clear human accountability. NIST's Govern, Map, Measure, and Manage functions provide a structure for managing these risks throughout the AI lifecycle.

Resource: Artificial Intelligence Risk Management Framework (AI RMF 1.0), NIST AI 100-1 - https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
## Mobile
Android apps run in sandboxes that limit access to other apps' data and protected system resources. When a national login app needs a permission-protected feature, it should request the relevant permission at the appropriate time. For dangerous permissions, Android 6.0 (API level 23) introduced runtime requests, allowing users to grant or deny access. The app should handle denial gracefully and preserve core login functionality wherever possible.

Resource: Request runtime permissions | Android Developers - https://developer.android.com/training/permissions/requesting
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
