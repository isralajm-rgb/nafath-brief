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
DNS over HTTPS (DoH), specified in RFC 8484, sends DNS queries and responses over an HTTPS connection. This helps protect DNS lookups from passive observation and tampering along the path to the resolver, while TLS authenticates the DoH server. However, the resolver can still see the queries, and DoH does not hide the user's IP address from the resolver or guarantee that DNS answers are correct. It also does not replace DNSSEC.

Resource: RFC 8484: DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484.html
## Cybersecurity
A common misconception is that all multi-factor authentication (MFA) methods are phishing-resistant. CISA identifies FIDO/WebAuthn and public key infrastructure (PKI)-based MFA, such as smart cards, as phishing-resistant options. In contrast, authenticator-app one-time passwords and number-matching push remain vulnerable to phishing, while push approvals without number matching are vulnerable to push bombing. SMS and voice codes are vulnerable to phishing, SS7, and SIM-swap attacks. Therefore, adding a second factor does not automatically make authentication phishing-resistant.

Resource: Implementing Phishing-Resistant MFA - https://www.cisa.gov/sites/default/files/2023-01/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf 
## Data
Oman's Personal Data Protection Law sets obligations for controllers handling personal data, including obtaining explicit consent where required, notifying individuals in writing before processing, protecting confidentiality, appointing a personal data protection officer, and maintaining processing records. Controllers must also notify the Ministry and affected individuals of qualifying data breaches. Processing specified sensitive data, including biometric data, generally requires a Ministry permit. However, Article 3(b) excludes certain processing by state bodies exercising legally prescribed competences, so its applicability to a national login service requires verification.

Resource: Royal Decree 6/2022 Issuing the Personal Data Protection Law (Consolidated) - https://decree.om/2022/l20220006/
## Misconception in My Track
A common misconception is that all multi-factor authentication (MFA) methods are equally resistant to phishing. However, SMS codes and app-generated one-time passwords can be intercepted through phishing when users enter them on fake login pages. CISA identifies FIDO/WebAuthn as the only widely available phishing-resistant authentication method and also describes PKI-based MFA for suitable environments. This shows that adding a second factor does not automatically prevent phishing; the authentication method itself matters.

Resource: Implementing Phishing-Resistant MFA - https://www.cisa.gov/sites/default/files/2023-01/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf
## Open Question
“How does Article 3(b) of Oman's Personal Data Protection Law apply to a national digital identity service operated by a government authority, and what safeguards govern citizens’ personal data if the processing falls outside the Law’s direct scope?”
