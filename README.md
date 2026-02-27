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

### 01 - S3 Bucket Private
![01-s3-bucket-private](screenshots/1-s3-bucket-private.png?raw=true)  
Shows the S3 bucket configured with private access.

---

### 02 - Index Uploaded
![02-index-uploaded](screenshots/2-index-uploaded.png?raw=true)  
The `index.html` file uploaded to the private S3 bucket.

---

### 03 - Access Denied
![03-access-denied](screenshots/3-access-denied.png?raw=true)  
Attempting to access the S3 bucket publicly results in Access Denied.

---

### 04 - Nginx Running
![04-nginx-running](screenshots/4-nginx-running.png?raw=true)  
Shows an Nginx server running locally to test access to the site.

---

### 05 - Nginx Default Page
![05-nginx-default-page](screenshots/5-nginx-default-page.png?raw=true)  
Displays the default Nginx welcome page.

---

### 06 - S3 Private Access Denied
![06-s3-private-access-denied](screenshots/6-s3-private-access-denied.png?raw=true)  
Testing private S3 access to confirm public requests are blocked.

---

### 07 - CloudFront Updated Page
![07-cloudfront-updated-page](screenshots/7-cloudfront-updated-page.png?raw=true)  
Shows the static site served via CloudFront.

---

### 08 - WAF Web ACL Basic Setup
![08-waf-webacl-basic-setup](screenshots/8-waf-webacl-basic-setup.png?raw=true)  
Overview of Web ACL settings, priorities, and actions before enabling logging.

---

### 09 - Web ACL Active Rules
![09-webacl-active-rules](screenshots/9-webacl-active-rules.png?raw=true)  
Displays the list of active rules in `Project3-WebACL-2`.

---

### 10 - WAF Access Denied
![10-waf-access-denied](screenshots/10-waf-access-denied.png?raw=true)  
Shows the access denied screen when trying to reach a resource blocked by WAF.

---

### 11 - WAF Logging Active
![11-waf-logging-active](screenshots/11-waf-logging-active.png?raw=true)  
Logging enabled via Firehose stream `aws-waf-logs-Project3` for monitoring requests.

---

### 12 - WAF Block Test
![12-waf-block-test](screenshots/12-waf-block-test.png?raw=true)  
`curl` test confirming that requests from blocked IPs return HTTP `403`.

---

### 13 - WAF Rule Enabled for CloudFront
![13-waf-rule-enabled-cloudfront](screenshots/13-waf-rule-enabled-cloudfront.png?raw=true)  
Shows the BlockMyCurrentIP rule active and associated with the CloudFront distribution.

---

## Notes

- Some sampled requests may take a few minutes to appear in WAF.
- Logging is enabled via Firehose stream `aws-waf-logs-Project3`.
- CloudFront distribution: Created and associated with WAF Web ACL (ID hidden for security)
- Testing via `curl` confirmed blocked IP returns `403`.

---

## Repository Structure

```text
Project3-WAF-Secure-Static-Site/
├── screenshots/
│   ├── 1-s3-bucket-private.png
│   ├── 2-index-uploaded.png
│   ├── 3-access-denied.png
│   ├── 4-nginx-running.png
│   ├── 5-nginx-default-page.png
│   ├── 6-s3-private-access-denied.png
│   ├── 7-cloudfront-updated-page.png
│   ├── 8-waf-webacl-basic-setup.png
│   ├── 9-webacl-active-rules.png
│   ├── 10-waf-access-denied.png
│   ├── 11-waf-logging-active.png
│   ├── 12-waf-block-test.png
│   └── 13-waf-rule-enabled-cloudfront.png
├── index.html
└── README.md
