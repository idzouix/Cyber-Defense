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

apply MFA  : 
- Remove phone as 2FA (explain why)

(more : see --MFA--)
- remove loging using phone number / google invite

Backup codes : get them stored in password manager (see --password manager--) or in separate usb keys / handwritten

-- remove third party associated app from the google account (on main accounts, we could have at least 30 accounts dependend on it : see --accounts--

## Burner emails : 
(explain what is a burner email, when its best to take it, when not, risks  usage etc)
for accounts with no sensitive data / you don't care if it get stolen / compromised (due to risks of a burner email)
examples : for the account chess.com to play chess casually, i get temporary email to create an account 

## Privacy
(explain meta datas to falsify if not needed etc), remove cards payement saved, remove "connect with google" attached accounts -see Privacy--

## Email Hygine :
explain positives (less phishing, etc)

## Accounts :
(see --accounts--)

##   Ultimate Conclusion : 
If you need to create an account, create your unique hardened email for that unique account. if the email is not important and you don't care the risks use a burner email.
