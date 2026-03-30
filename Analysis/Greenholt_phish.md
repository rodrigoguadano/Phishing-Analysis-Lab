# Phishing Analysis: The Greenholt Phish

## Email Summary
- **From:** "Mr. James Jackson" <info@mutawamarine.com>  
- **To:** webmaster@redacted.org  
- **Subject:** webmaster@redacted.org your: Transfer Reference Number:(09674321)  
- **Date:** 09 Jun 2020 22:58:27 -0700  
- **Attachment:** SWT_#09674321____PDF__.CAB  

**Key Observation:**  
Email claims to provide a SWIFT payment receipt with a file attachment. Suspicious due to mismatched sending IP and failed SPF authentication. Likely phishing attempt.

---

## Email Headers & Authentication
- **Return-Path:** <info@mutawamarine.com>  
- **Sending IP:** 192.119.71.157 (Hostwinds LLC)  
- **SPF Result:** Fail  
- **DMARC Result:** Unknown  
- **Reply-To:** "Mr. James Jackson" <info.mutawamarine@mail.com>  

**Analysis:**  
- Return-Path domain (mutawamarine.com) does not match sending IP
- DMARC not published, email lacks domain policy enforcement  
- Reply-To uses a similar but different domain, possible spoofing  

---

## Domain & URL Analysis
- **Domain:** mutawamarine.com  
- **Registrar / Registrant Info:** PDR Ltd. d/b/a PublicDomainRegistry.com; General Manager, Abu Dhabi, AE  
- **WHOIS Dates:** Registered: 2003-12-15 / Expires: 2026-12-15 / Last Updated: 2025-12-09  
- **Reputation Check:** No security vendors flagged this URL as malicious (VirusTotal)  

**Observations:**  
- Long-registered domain, but sending IP from a hosting provider unrelated to the domain 
- No malware flagged yet, but SPF fail indicates potential spoofing  

**Verdict:** Suspicious / Phishing  

---

## Attachment Analysis
- **Filename / Type:** SWT_#09674321____PDF__.CAB
- **Size:** 400.26 KB
- **Observations:** CAB archive masquerading as a payment receipt; inside, the actual file is a RAR archive, which may contain executables or macros. Typical phishing/malware delivery technique.
- **Potential Risk:** Likely attempts to drop malicious files on victim system  




---

## Indicators of Compromise (IoCs)
- **Domains:** mutawamarine.com, mutawamarine@mail.com  
- **IP Addresses:** 192.119.71.157  
- **URLs:** None embedded  
- **File Hashes (SHA256):** 2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f 
- **Email Addresses:** info@mutawamarine.com, info.mutawamarine@mail.com  

---

## Evidence / Screenshots
- Header screenshot: [Insert screenshot]  
- VirusTotal / URL scan screenshot: [Insert screenshot]  
- Attachment sandbox screenshot: [Insert screenshot]  

---

## MITRE ATT&CK Mapping
| Tactic                     | Technique                                                      |
|-----------------------------|---------------------------------------------------------------|
| Initial Access             | Phishing (T1566)                                              |
| Execution                  | User execution of malicious attachment (T1204)                |
| Credential Access           | Spearphishing for credentials (T1566.001)                     |
| Impact                      | Potential malware delivery / data compromise                  |

---

## Overall Analysis
- Email originates from an IP not authorized by the sending domain  
- DMARC policy missing → lack of enforcement increases phishing risk  
- Attachment is a CAB file disguised as a payment receipt  
- No immediate malware detection via VirusTotal, but classic phishing indicators present  
- Domain appears legitimate by age but sending pattern is suspicious  

**Final Verdict:** Malicious phishing attempt  

---

## Recommendations
- Users should **never open attachments from unknown sources**  
- Verify **SPF/DMARC alignment** before trusting emails claiming financial transactions  
- Sandbox all suspicious attachments before opening  
- Report phishing attempts to internal SOC and relevant abuse contacts  
- Consider **implementing DMARC policy** on your own domains to reduce spoofing
