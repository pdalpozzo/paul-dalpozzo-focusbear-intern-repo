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
- by Data is the representative - represents Focus Bear in matters of data protection
- by Data is the Data Protection Officer - makes sure Focus Bear follows the data protection rules
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
I guess all the data collected is considered confidential. But they seem to be in tiers on what measures are taken. There is
- Anonymized data - mostly statistical and records of interactions with the team or application.
- Double encrypted data - personal and social data
- Third-party handling data - Auth0, Zoho, Stripe, AWS - they have their own secure data handling

### What are best practices for handling confidential data?
Focus Bear ensures that any high value confidential data is double encrypted. This is good because it would require two different keys to decrypt the data.  
They also ensure that any data that is keep long term is anonymized so that nothing can be traced back to the user.

### How should you respond to a suspected data breach or accidental disclosure of confidential information?
As a user - I could contact Focus Bear via the email privacy@focusbear.io to find out what data has been leaked. I could also contact by Data if I feel like I needed more information.
As an intern - I would contact Jeremy immediately. Show him evidence of why I suspect a data breach. This is a serious matter and he would need to take control on it.

## Reflection
### What steps can you take to ensure you handle data securely in your daily tasks?
- As a tester and bug hunter, I could create my own set of test data. This will allow me to enter edge-cases as well as find issues.
- I should get consent and permission the data I would use for the task.
- I should only use the data that is necessary for my task
- Encrypted data should stay encrypted. Never let it be stored unencrypted at any point.
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
- erase personal data immediately once is purpose of collection is complete
- completely delete data when a user exercises their legal 'Right to Erasure'
- long-term statistical data must be rigorously minimized and completely anonymous.

### What are some common mistakes that lead to data privacy issues, and how can they be avoided?
***Linking sensitive data***  
- Separate data so that personal data can not found
- Don't link data

***Unauthorised processing***  
- Only process the data for the purpose it was collected. 

***Failing to recognize or report a data breach***  
- Learn to spot anomalies early. 
- Report a suspected breach immediately as it must be handled, evaluated and managed rapidly.

## Task
### Identify at least one habit or practice you can adopt to improve data security in your role.
I should always test and ensure that data is following the standards in the policy. Double encrypting data or making it completely anonymized. I have not really done much of this in my past and it is becoming more important as AI becomes stronger and more skilled. It is a must learn skill.

### Document at least one key learning or security measure you will implement.
For my log in, I will start using 2FA where possible. This will be for every site or application I sign up to.
