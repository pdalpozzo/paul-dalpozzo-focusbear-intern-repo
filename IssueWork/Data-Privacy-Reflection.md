# Paul Dal Pozzo

**Student ID:** s214527809  
**Email:** s214527809@deakin.edu.au  
**Intern Position:** Usability Tester & Bug Hunter  
**Focus Bear Account:** paul_dal_pozzo@hotmail.com  
**Markdown Location:** https://github.com/pdalpozzo/paul-dalpozzo-focusbear-intern-repo/blob/main/IssueWork/Data-Privacy-Reflection.md

# Issue 14

## Research & Learn
### Review Focus Bear’s privacy policy and note key takeaways. (Hint: The privacy policy is available [here](https://www.focusbear.io/privacy-policy).)
- Complies with General Data Protection Regulation (EU) 2016/679
- Provides simple language summaries - very helpful
- Focus Bear is the controller - responsible for processing the data
- Focus Bear is represented in matters of data protection by its designated compliance team and Data Protection Officer, who ensures adherence to all data protection rules.
- Data Collected
  - Identification Data - to confirm your identity - Auth0 and Zoho
  - Social Data - to understand your needs to improve the app - double encrypted
  - Academic & Professional Data - to understand your needs to improve the app - keep it anonymous
  - Commercial and Marketing Data - to send emails and WhatsApp messages about features - contact details are kept secret and only revealed to team members that need to contact you.
  - Technical Data - used to troubleshoot bugs and understand the devices/os they happen on - keep it anonymous
  - Economic, Financial, and Insurance Data - needed for subscription - don't store credit card details, uses Stripe
  - Profile Data - purchases, subscription, feedback and surveys - keep it anonymous
  - Aggregate Data - statistical and demographic information - keep it anonymous
  - Special Category of Personal Data - not intentionally collected - double encrypted
- Collected from user entering the data
- The data is used to deliver and manage the services provided by Focus Bear
- No processing on personal data unless there is a valid legal reason.
- Data is retained for as long as it is needed - statistical data is secure and anonymized.

### What types of data are considered confidential at Focus Bear?
All the data collected is treated as confidential and categorized into specific security tiers:
- **Anonymized data:** Statistical metrics and interaction records.
- **Double encrypted data:** Personal, social, and special category data.
- **Third-party handling data:** Managed via secure external platforms (Auth0, Zoho, Stripe, AWS).


### What are best practices for handling confidential data?
Focus Bear ensures that any high-value data is double encrypted. This is good because it would require two different keys to decrypt the data.  
They also ensure that any data that is keep long term is anonymized so that nothing can be traced back to the user.
Practical intern actions include applying the principle of least access, avoiding local copies, using only approved tools, and ensuring secure sharing.

### How should you respond to a suspected data breach or accidental disclosure of confidential information?
- **As a user:** Contact Focus Bear via the email privacy@focusbear.io to find out what data has been leaked. I could also contact By Data if I feel like I needed more information.
- **As an intern:** Immediately report anomalies and suspected breaches to the supervisor (Jeremy) with evidence, halt ongoing transfers, limit exposure, and cooperate on containment.

## Reflection
### What steps can you take to ensure you handle data securely in your daily tasks?
- Create custom test data. This will allow me to enter edge-cases as well as find issues.
- Obtain proper consent and permission for any data utilized.
- Restrict usage to only data necessary for the assigned task.
- Encrypted data must stay encrypted. Never let it be stored unencrypted at any point.
- Only access data that I am allowed to access. Report any misuse of data to a supervisor.

### How should you store, share, and dispose of sensitive information safely?
***Store***
- never store high-risk financial data
- use secure, pre-approved identity management platforms like Auth0
- store aggregate and/or statistical data anonymously

***Share***
- only share personal data with verified, trusted third party service providers in accordance to the GDPR
- ensure third-party vendors act on the data as they are contracted to, and nothing more
- enforce strict transmission protocols

***Dispose***
- erase personal data immediately once its purpose of collection is complete
- completely delete data when a user exercises their legal 'Right to Erasure'
- long-term statistical data must be rigorously minimized and completely anonymous

### What are some common mistakes that lead to data privacy issues, and how can they be avoided?
***Linking sensitive data***  
- Separate data so that personal data can not found
- Don't link data

***Unauthorised processing***  
- Restrict processing strictly to the original collection purpose.

***Failing to recognize or report a data breach***  
- Learn to spot anomalies early. 
- Report a suspected breach immediately as it must be handled, evaluated and managed rapidly.

## Task
### Identify at least one habit or practice you can adopt to improve data security in your role.
I will consistently test and verify that data handling adheres to policy standards, such as double encryption or full anonymization, which is increasingly vital in the AI era.

### Document at least one key learning or security measure you will implement.
I will implement two-factor authentication (2FA) for all account logins across applications and websites I use.
