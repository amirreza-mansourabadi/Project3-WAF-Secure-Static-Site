# Project 3: Secure Static Site with AWS WAF

This project demonstrates securing a static website hosted on CloudFront using AWS WAF. It includes creating Web ACLs, managed rules, IP blocking, and logging.

## Project Overview

- Host a static website on CloudFront  
- Configure AWS WAF Web ACLs for security  
- Add custom rules and managed rule sets  
- Block specific IP addresses  
- Enable logging with Amazon Data Firehose  
- Test WAF protection  

## Steps Completed

1. Created a Web ACL: `Project3-WebACL-2`  
2. Added rules:  
   - `BlockMyCurrentIP` (custom IP block)  
   - AWS Managed Rules:  
     - Amazon IP Reputation List  
     - Common Rule Set  
     - Known Bad Inputs Rule Set  
3. Enabled logging via Firehose stream: `aws-waf-logs-Project3`  
4. Tested blocked IP requests using `curl`  
5. Verified CloudFront returns `403` for blocked IPs  
6. Took 13 screenshots documenting each step  

## Screenshots

### 01 - WAF Intro  
![01-waf-intro](screenshots/01-waf-intro.png)  
AWS WAF console landing page showing an overview of Web ACLs, rules, and managed rule groups.  

### 02 - Web ACL List  
![02-webacl-list](screenshots/02-webacl-list.png)  
List of Web ACLs in the account. `Project3-WebACL-2` is highlighted as the active Web ACL.  

### 03 - BlockMyIP Rule  
![03-blockmyip-rule](screenshots/03-blockmyip-rule.png)  
Custom IP block rule to prevent a specific IP from accessing the website.  

### 04 - WAF Rule Builder  
![04-rule-builder](screenshots/04-rule-builder.png)  
Rule builder interface for defining statements such as IP sets, headers, or query string inspection.  

### 05 - WAF Rule JSON Editor  
![05-rule-json](screenshots/05-rule-json.png)  
Editing complex rule logic using the JSON editor for nested statements.  

### 06 - WAF IP Set Creation  
![06-ipset](screenshots/06-ipset.png)  
Creation of an IP set referenced in the custom block rule.  

### 07 - WAF Managed Rules  
![07-managed-rules](screenshots/07-managed-rules.png)  
AWS managed rule groups added to the Web ACL to protect against bots, bad inputs, and IP reputation threats.  

### 08 - Web ACL Basic Setup  
![08-webacl-setup](screenshots/08-webacl-setup.png)  
Overview of Web ACL settings, rule priorities, and actions before enabling logging.  

### 09 - Active Rules  
![09-active-rules](screenshots/09-active-rules.png)  
List of active rules in `Project3-WebACL-2` with priorities and actions.  

### 10 - WAF Access Denied  
![10-access-denied](screenshots/10-access-denied.png)  
Shows access denied when attempting to view a resource blocked by WAF.  

### 11 - Firehose Logging Enabled  
![11-firehose-logging](screenshots/11-firehose-logging.png)  
Logging enabled via Amazon Data Firehose stream `aws-waf-logs-Project3` for monitoring requests.  

### 12 - WAF Block Test (403)  
![12-waf-block-test](screenshots/12-waf-block-test.png)  
`curl` test confirming requests from blocked IPs return HTTP `403`.  

### 13 - Sampled Requests / Logs  
![13-sampled-requests](screenshots/13-sampled-requests.png)  
WAF sampled requests interface showing requests matching rules for verification.  

## Notes

- Sampled requests may take a few minutes to appear in WAF.  
- Logging is enabled via Firehose stream `aws-waf-logs-Project3`.  
- CloudFront distribution: `<your distribution ID>`  
- Testing via `curl` confirmed blocked IP returns `403`.  

## Repository Structure

```text
Project3-WAF-Secure-Static-Site/
├── screenshots/
│   ├── 01-waf-intro.png
│   ├── 02-webacl-list.png
│   ├── 03-blockmyip-rule.png
│   ├── 04-rule-builder.png
│   ├── 05-rule-json.png
│   ├── 06-ipset.png
│   ├── 07-managed-rules.png
│   ├── 08-webacl-setup.png
│   ├── 09-active-rules.png
│   ├── 10-access-denied.png
│   ├── 11-firehose-logging.png
│   ├── 12-waf-block-test.png
│   └── 13-sampled-requests.png
└── README.md
