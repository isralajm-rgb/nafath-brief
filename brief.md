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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
