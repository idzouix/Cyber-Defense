# Email Security Architecture

This architecture separates email accounts by purpose and limits the impact of a compromised account.

```text
                         ┌─────────────────────────┐
                         │     Recovery Email 1    │
                         │   Primary recovery      │
                         │   / emergency account   │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │     Recovery Email 2    │
                         │   Secondary recovery    │
                         │       account           │
                         └────────────┬────────────┘
                                      │
              ┌───────────────────────┼───────────────────────┐
              │                       │                       │
              ▼                       ▼                       ▼
       ┌─────────────┐        ┌─────────────┐        ┌─────────────┐
       │ Bank Email  │        │Personal Email│       │Programming  │
       │             │        │             │        │   Email     │
       └─────────────┘        └─────────────┘        └─────────────┘
                                      │
                                      ▼
                               ┌─────────────┐
                               │ Social Email│
                               └─────────────┘
```

## Account Roles

| Account               | Purpose                                                                | Public?             |
| --------------------- | ---------------------------------------------------------------------- | ------------------- |
| **Recovery Email 1**  | Emergency recovery for the recovery infrastructure                     | ❌ Never             |
| **Recovery Email 2**  | Secondary recovery account                                             | ❌ Never             |
| **Bank Email**        | Banking, financial institutions, insurance, government services        | ❌ Private           |
| **Personal Email**    | Personal communication and everyday services                           | ⚠️ Private          |
| **Programming Email** | GitHub, GitLab, cloud platforms, developer services and certifications | ⚠️ Limited exposure |
| **Social Email**      | Social media, communities and less-trusted services                    | ⚠️ More exposed     |

## Security Principles

* Each account has a **unique password**.
* Recovery accounts are **not used for normal registrations**.
* Recovery accounts should remain as private as possible.
* Enable **MFA/passkeys** wherever supported.
* Store **recovery codes offline**.
* Do not use the same password across accounts.
* Avoid publishing personal email addresses unnecessarily.
* Keep financial accounts isolated from social/developer activity.
* Regularly review account recovery options.
* Treat recovery accounts as **high-value assets** because they can reset other accounts.

## Threat Model

The architecture is designed around **compartmentalization**.

A compromise of one operational email should not automatically compromise every other identity.

```text
Compromised Social Email
        │
        └──> Social accounts at risk
              │
              └──> Other identities remain isolated


Compromised Programming Email
        │
        └──> Developer accounts at risk
              │
              └──> Banking identity remains isolated


Compromised Recovery Email
        │
        └──> HIGH RISK
              │
              └──> Recovery infrastructure must therefore
                   receive the strongest protection.
```

> **Important:** Recovery Email 2 is a potential single point of failure if it can reset all operational accounts. The recovery hierarchy should therefore be protected more strongly than the normal email accounts.





(explain point of having email rocvery + one backup)

Email recovery 1 = Backup recovery
Email recovery 2 = All emails have this email as backup

(explain why each account has its own email)
Emails for : 
- Bank email 
- Social email
- Personnal email
- Programming email
  
each email accounts = attached to the backup n1
each email accounts = its own password (see --password manager--) 

apply MFA (see --MFA--)

Burner emails : 
(explain what is a burner email, when its best to take it, when not, risks  usage etc)
for accounts with no sensitive data / you don't care if it get stolen / compromised (due to risks of a burner email)
examples : for the account chess.com to play chess casually, i get temporary email to create an account 
