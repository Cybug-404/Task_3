# Task_3 Vulnerability Assessment Scan

## 🔍 Objective
Discover common vulnerabilities on localhost.

## 🛠 Tools Used
- Nessus
- Overleaf
- Windows (OS)

## 🧪 Steps Performed
1. Installed Nessus from https://www.tenable.com
2. From the GUI of Nessus, selected an advanced scan
3. Done the advanced scan on localhost[127.0.0.1]
4. Vulnerabilities found and learned their impact and remedial measures
5. Successfully made reporting and documentation 

## 📊 Output
- Open ports: 135,445,49665,49666,49668,49673
- Severities: SMB Signing Not Required, SSL Certificates Cannot Be Trusted, NTLMSSP Network Name Disclosure, WMI Not Available, DCE Services Enumeration, and TLS 1.2 and 1.3 Protocol Detection.

## 🧠 Learnings
-----------------------------------------------------------------------------------------------------------------------------------------|
| PORT | SERVICE      | DESCRIPTION                                     | VULNERABILITY                                                  |
|------|--------------|-------------------------------------------------|----------------------------------------------------------------|
| 135  | RPC          | Remote code execution (RCE)                     | DCE/RPC Interface Exposure (CVE-2021-26414, CVE-2022-26809     |
| 445  | SMB          | SMBv1 allowed remote code execution             | SMBv1 Vulnerability (EternalBlue)  (CVE-2017-0144)             |
| 49665| Dynamic RPC  | Remote desktop GUI access                       | Information Disclosure / Lateral Movement                      |
| 49666| Dynamic RPC  | Remote desktop GUI access                       | Information Disclosure / Lateral Movement                      |
| 49668| Dynamic RPC  | Remote desktop GUI access                       | Information Disclosure / Lateral Movement                      |
| 49673| Dynamic RPC  | Remote desktop GUI access                       | Information Disclosure / Lateral Movement                      |
-----------------------------------------------------------------------------------------------------------------------------------------|

==========================================================================================================================================================================
| # | Finding Name                       | Severity      | Description                                                                                                    |
|---|------------------------------------|---------------|----------------------------------------------------------------------------------------------------------------|
| 1 | SMB Signing Not Required           | Medium        | Remote SMB server does not enforce message signing, making it susceptible to man-in-the-middle (MITM) attacks. |
| 2 | SSL Certificates Cannot Be Trusted | Medium        | The SSL certificate used is not trusted or improperly configured, allowing spoofing or MITM attacks.           |
| 3 | NTLMSSP Network Name Disclosure    | Informational | The system leaks its network name via NTLM authentication over SMB. Useful for fingerprinting.                 |
| 4 | WMI Not Available                  | Informational | Windows Management Instrumentation (WMI) is not accessible via DCOM, limiting remote management.               |
| 5 | DCE Services Enumeration           | Informational | RPC endpoint mapper reveals available services. Can aid in targeted exploitation.                              |
| 6 | TLS 1.2 and 1.3 Protocol Detection | Informational | Confirms use of modern encryption (TLS 1.2/1.3). No vulnerability, but useful for service fingerprinting.      |
===========================================================================================================================================================================
