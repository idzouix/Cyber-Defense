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
       ┌─────────────┐        ┌──────────────┐        ┌─────────────┐
       │ Bank Email  │        │Personal Email│        │ Programming │
       │             │        │              │        │   Email     │
       └─────────────┘        └──────────────┘        └─────────────┘

```

## Recovery Emails
(explain point of having email rocvery + one backup)

Email recovery 1 = Backup recovery
Email recovery 2 = All emails have this email as backup

## Emails
(explain why each account has its own email)
Emails for : 
- Bank email 
- Social email
- Personnal email
- Programming email
  
each email accounts = attached to the backup n1
each email accounts = its own password (see --password manager--) 

apply MFA (see --MFA--)

## Burner emails : 
(explain what is a burner email, when its best to take it, when not, risks  usage etc)
for accounts with no sensitive data / you don't care if it get stolen / compromised (due to risks of a burner email)
examples : for the account chess.com to play chess casually, i get temporary email to create an account 

## Accounts :
(see --accounts--)
