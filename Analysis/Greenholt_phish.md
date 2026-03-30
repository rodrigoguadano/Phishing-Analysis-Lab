# Greenholt Phishing Incident Analysis

## 📌 Incident Overview
A phishing email was identified targeting users by impersonating a legitimate entity. The objective of the attacker appears to be credential harvesting.

---

## 📧 Email Details
- Sender:
- Spoofed domain:
- Subject:
- Date:

---

## 🚩 Initial Indicators
- Suspicious domain (lookalike / typo-squatting)
- Urgent language
- Embedded link redirecting to external site

---

## 📨 Header Analysis
### Key Findings:
- SPF: (pass/fail)
- DKIM: (pass/fail)
- DMARC: (pass/fail)
- Originating IP:
- Return-Path mismatch: Yes/No

### Analysis:
(Explain spoofing or anomalies)

---

## 🔗 URL & Domain Analysis
- URL:
- Uses HTTPS: Yes/No
- Domain age:
- WHOIS findings:
- Redirect behavior:

### Verdict:
(Malicious indicators)

---

## 🌐 Threat Intelligence
- VirusTotal:
- URLScan:
- IP reputation:

---

## ⚠️ Indicators of Compromise (IOCs)
- Malicious domain:
- Sender email:
- IP address:
- URLs:

---

## 🧠 MITRE ATT&CK Mapping
- Tactic: Initial Access
- Technique: Phishing (T1566)

---

## 🔍 Attack Analysis
The attacker used social engineering techniques such as:
- Urgency
- Brand impersonation
- Link obfuscation

---

## ✅ Final Verdict
**Malicious**

### Justification:
(Clear technical reasoning, not generic)

---

## 🛡️ Recommendations
- User awareness training
- Email filtering (SPF, DKIM, DMARC enforcement)
- Block IOCs at SIEM/EDR level
