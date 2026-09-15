# phishing-awareness-project
A cybersecurity awareness project focused on identifying phishing attacks, analyzing common phishing techniques, and educating users on how to recognize and prevent phishing threats.
# Phishing Email Detection & Awareness System

## Project Overview

This project was created as part of Cyber Security Task 2. The objective is to analyze phishing email samples, identify common phishing indicators, classify email risk, and create awareness guidelines to help users recognize and avoid phishing attacks.

The project uses publicly available cybersecurity repositories containing real and educational phishing email samples.

---

## Tools Used

### 1. GitHub

Used to:
- Access publicly available phishing email repositories
- Collect sample email evidence
- Store and publish the final project
- Maintain the project documentation

### 2. Phishing Email Samples

The following repositories were used as reference sources:

- rf-peixoto/phishing_pot
  - Collection of real phishing samples
  - Used as the primary source for actual email evidence

- autinerd/phishing-mail-examples
  - Educational phishing email examples
  - Used to understand common phishing email structures and header patterns

- sadat1971/Phishing_Email
  - Labeled phishing and non-phishing email dataset
  - Used as a reference for email classification

- Phishing-Database/Phishing.Database
  - Phishing domain and URL threat-intelligence database
  - Used as a reference for suspicious URLs/domains

- Click2Hack/Phishing-Email-Detection-Using-Machine-Learning
  - Optional machine-learning reference for phishing email detection

### 3. Email Header Analysis

Email headers were examined to identify:
- Sender information
- Reply-To address
- Return-Path
- Sending server
- SPF authentication
- DKIM authentication
- DMARC authentication

### 4. URL and Domain Analysis

Suspicious URLs and domains were examined for:
- Domain mismatch
- Unusual or unrelated domains
- Suspicious URL structure
- Possible impersonation
- Threat-intelligence indicators

Suspicious URLs were kept defanged using formats such as:

`hxxps://example[.]com`

This prevents accidental opening of potentially malicious websites.

### 5. Microsoft Word / PDF

Used to prepare the final:
- Phishing email evidence document
- Detection and awareness report
- Analysis findings
- Prevention guidelines

---

# Analysis Approach

The phishing emails were analyzed using the following process.

## Step 1 — Collect Sample Emails

Phishing email samples were obtained from publicly available cybersecurity repositories.

The primary real samples used in this project were:

- `sample-10.eml` — Microsoft account unusual sign-in email
- `sample-12.eml` — Binance immediate verification email

The samples were used only for cybersecurity education and analysis.

---

## Step 2 — Examine Email Headers

Important header fields were examined, including:

- From
- Reply-To
- Return-Path
- Received
- Sender IP
- SPF
- DKIM
- DMARC

Header inconsistencies can indicate that an email is impersonating a legitimate organization.

For example, a message may display a trusted company name while using an unrelated sender or reply address.

---

## Step 3 — Inspect the Email Content

The email body was checked for common phishing indicators such as:

- Urgent language
- Fear or account-lock threats
- Requests for verification
- Requests for personal information
- Generic greetings
- Suspicious buttons or links
- Brand impersonation
- Short deadlines

---

## Step 4 — Analyze Links and Domains

Links contained in the emails were inspected as text without opening suspicious destinations.

The following characteristics were checked:

- Does the URL belong to the claimed organization?
- Is the domain unrelated or suspicious?
- Does the URL attempt to imitate a trusted service?
- Is the domain present in phishing threat-intelligence sources?

Suspicious URLs were defanged to prevent accidental activation.

---

## Step 5 — Identify Phishing Indicators

Multiple indicators were considered together instead of relying on a single suspicious feature.

Examples include:

| Indicator | Meaning |
|---|---|
| Sender mismatch | Sender may not belong to claimed organization |
| Reply-To mismatch | Replies may be redirected to attacker |
| SPF failure/absence | Sender authorization cannot be verified |
| DKIM failure/absence | Message signature is missing/invalid |
| DMARC failure | Domain authentication policy failed |
| Urgency | Attempts to make the user act without thinking |
| Account threat | Uses fear of suspension or loss |
| Suspicious URL | May lead to credential theft or malware |
| Brand impersonation | Uses a trusted company to appear legitimate |

---

## Step 6 — Classify Risk

Each analyzed email was classified into one of the following categories:

### SAFE
No significant phishing indicators were identified.

### SUSPICIOUS
Some unusual characteristics were identified, but there is not enough evidence to confidently classify the email as phishing.

### PHISHING
Multiple strong indicators show that the email is likely attempting to deceive the recipient.

The repository samples analyzed in this project were classified as **PHISHING** because they contained multiple independent indicators.

---

## Step 7 — Document the Evidence

The findings were documented in a structured evidence report containing:

- Email subject
- Sender information
- Header findings
- Authentication results
- Suspicious URL/domain information
- Phishing indicators
- Risk classification
- Sanitized email excerpts
- Source repository

Sensitive information and unnecessary live malicious content were not re-hosted.

---

## Step 8 — Create Awareness Guidelines

Based on the analysis, users should:

- Check the sender address carefully
- Be suspicious of urgent requests
- Avoid clicking unexpected links
- Verify the website/domain before entering credentials
- Never share passwords or OTPs through email
- Contact the organization using an official website or known phone number
- Report suspicious emails to the security/IT team
- Delete or quarantine confirmed phishing emails

---

# Sample Findings

## Sample 1 — Microsoft Account Email

**Source:** `phishing_pot/email/sample-10.eml`

**Classification:** PHISHING — HIGH RISK

Important indicators:
- Microsoft branding/impersonation
- Suspicious sender domain
- Reply-To address mismatch
- SPF/DKIM authentication anomalies
- DMARC error
- Unusual sign-in security alert

---

## Sample 2 — Binance Verification Email

**Source:** `phishing_pot/email/sample-12.eml`

**Classification:** PHISHING — CRITICAL RISK

Important indicators:
- Immediate verification request
- Account/withdrawal threat
- 72-hour deadline
- SPF/DKIM authentication anomalies
- DMARC failure
- Suspicious unrelated destination URL

---

# Safety and Ethics

This project is intended only for cybersecurity education and awareness.

- No phishing campaign was conducted.
- No credentials were collected.
- Suspicious URLs were not intentionally opened.
- URLs were defanged where appropriate.
- Sensitive information was redacted.
- Complete live phishing emails were not re-hosted unnecessarily.
- The analysis was performed for defensive security awareness.

---

# Project Structure

```text
phishing-email-detection-awareness/
│
├── README.md
│
├── report/
│   └── Phishing_Detection_Awareness_Report.pdf
│
├── samples/
│   ├── source_sample_10_microsoft.txt
│   ├── source_sample_12_binance.txt
│   └── task_sample_account_lock.txt
│
└── evidence/
    ├── source_sample_10_evidence.txt
    ├── source_sample_12_evidence.txt
    └── README.md
