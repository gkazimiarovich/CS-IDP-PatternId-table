# CS-IDP-PatternId-table
CS IDP PatternId table, with MITRE mapping
| Code   | Name                                             | Description                                                                                                                                                                                                                                                | MITRE ATT&CK Tactic/Technique                                                                          | T-code               |
|--------|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| 51100  | Golden Ticket attack                             | A Golden Ticket was detected (forged Kerberos TGT).                                                                                                                                                                                                        | Credential Access using Steal or Forge Kerberos Tickets: Golden Ticket                                                                         | T1558.001           |
| 51101  | Suspicious protocol implementation (Pass the Hash) | An authentication protocol, such as NTLM, Kerberos, or SMB, occurred with fields indicating that their authentication was used in a Pass the Hash attack.                                                                                                   | Lateral Movement using Use Alternate Authentication Material: Pass the Hash                                                                    | T1550.002           |
| 51102  | Suspicious protocol implementation (NTLM relay)  | An NTLM authentication occurred with fields indicating that their authentication was used in an NTLM relay attack.                                                                                                                                         | Credential Access using Man-in-the-Middle: LLMNR/NBT-NS Poisoning and SMB Relay                                                               | T1557.001           |
| 51103  | Suspicious protocol implementation (valid accounts) | An authentication protocol (NTLM, Kerberos, or SMB) was used in an unusual manner consistent with known attack tools such as Mimikatz or Impacket.                                                                                                         | Initial Access using Valid Accounts: Domain Accounts                                                                                           | T1078.002           |
| 51104  | Anomalous RPC (ZeroLogon)                        | A ZeroLogon exploit attempt was detected.                                                                                                                                                                                                                  | Lateral Movement using Exploitation of Remote Services                                                                                         | T1210               |
| 51105  | Suspicious LDAP search (accounts)                | A user executed a suspicious LDAP search request looking for Kerberos misconfigurations (e.g., Kerberoasting or AS-REP roasting).                                                                                                                           | Credential Access using Steal or Forge Kerberos Tickets: Kerberoasting / AS-REP Roasting                                                      | T1558.003/.004      |
| 51106  | Suspicious LDAP search (Kerberos misconfiguration) | A user executed a suspicious LDAP search request to enumerate AD accounts. Often associated with reconnaissance tools like Bloodhound or Impacket.                                                                                                          | Discovery using Account Discovery: Domain Account                                                                                              | T1087.002           |
| 51108  | Suspicious domain replication                    | A user executed a suspicious domain replication (DRSUAPI) request. Possibly indicates DCSync attempts to steal domain secrets or malicious AD configuration.                                                                                                | Credential Access using OS Credential Dumping: DCSync                                                                                          | T1003.006           |
| 51109  | DC PsExec execution                              | A user executed a PsExec command on a domain controller (DC) for the first time, which could indicate malicious remote code execution with high privileges.                                                                                                | Execution using System Services: Service Execution                                                                                             | T1569.002           |
| 51110  | Anomalous RPC (account discovery)                | A user executed an account discovery DCE/RPC command targeting a domain controller (DC) for the first time.                                                                                                                                               | Discovery using Account Discovery (Domain Accounts)                                                                                            | T1087.002           |
| 51111  | Anomalous RPC (scheduled task)                   | A user executed a scheduled task DCE/RPC command targeting a DC for the first time, possibly indicating attacker persistence or lateral movement.                                                                                                          | Execution using Scheduled Task                                                                                                                 | T1053.005           |
| 51113  | Privilege escalation (user)                      | A user received new privileges. This could be an unwanted or malicious escalation of privileges.                                                                                                                                                           | Privilege Escalation using Valid Accounts                                                                                                      | T1078 (generic)     |
| 51114  | Anomalous RPC (credential access)                | A user executed a credential access DCE/RPC command on a DC for the first time, indicating possible anomalous changes to the DC.                                                                                                                            | Credential Access using Exploitation for Credential Access                                                                                     | T1212               |
| 51114  | Anomalous RPC (remote services)                  | A user executed a remote service DCE/RPC command targeting a DC for the first time, which could indicate malicious remote service manipulation.                                                                                                             | Lateral Movement using Remote Services                                                                                                         | T1021               |
| 51115  | Anomalous RPC (valid accounts)                   | A user executed a valid accounts DCE/RPC command on a DC for the first time, possibly malicious DC configuration.                                                                                                                                          | Discovery using Account Discovery (Domain Accounts)                                                                                            | T1087.002           |
| 51116  | Forged PAC attack                                | A Forged PAC attack was executed in the network, indicating possible malicious lateral movement.                                                                                                                                                           | Credential Access using Exploitation for Credential Access                                                                                     | T1212               |
| 51117  | Suspicious Kerberos ticket reuse                 | A Kerberos ticket generated by one machine was reused by another machine, consistent with Pass the Ticket attacks.                                                                                                                                         | Lateral Movement using Use Alternate Authentication Material: Pass the Ticket                                                                  | T1550.003           |
| 51118  | NTLM relay activity                              | Traffic analysis revealed NTLM credentials were used to attack a different machine than the original target, indicating an NTLM Relay attack.                                                                                                              | Credential Access using NTLM Relay                                                                                                             | T1557.001           |
| 51119  | Password brute force attack (Active Directory)   | A user’s password was repeatedly entered incorrectly from an unusual machine within the domain, suggesting password guessing attempts.                                                                                                                     | Credential Access using Password Guessing                                                                                                       | T1110.001           |
| 51120  | Password brute force attack (web-based)          | A user’s password was repeatedly entered incorrectly from an unusual IP address outside the domain, suggesting external brute force attempts.                                                                                                              | Credential Access using Password Guessing                                                                                                       | T1110.001           |
| 51121  | Credential scanning (Active Directory)           | Multiple failed authentication attempts from the same domain machine in a short timeframe, potentially password spraying.                                                                                                                                    | Credential Access using Password Spraying                                                                                                      | T1110.003           |
| 51122  | Credential scanning (web-based)                  | Multiple failed authentication attempts from the same external IP in a short timeframe, likely password spraying.                                                                                                                                          | Credential Access using Password Spraying                                                                                                      | T1110.003           |
| 51123  | Hidden object discovered                         | A hidden account was discovered. The ACL on the account prevents its discovery by normal AD management searches, potentially an attacker-created backdoor.                                                                                                 | Defense Evasion using Hidden Users (approx. Account Manipulation)                                                                              | T1098 (approx.)     |
| 51124  | Access from IP with bad reputation               | A user accessed the network or cloud from an IP address that has a known history of malicious activity.                                                                                                                                                    | Valid Accounts: Cloud Accounts                                                                          | T1078.004           |
| 51125  | Access from unusual geolocation                  | A user accessed from an unusual or uncommon location. Could indicate stolen credentials or malicious use.                                                                                                                                                 | Valid Accounts: Cloud Accounts                                                                          | T1078.004           |
| 51126  | Access from blocklisted location                 | A user accessed from a blocklisted country or region, possibly indicating stolen credentials.                                                                                                                                                              | Valid Accounts: Cloud Accounts                                                                          | T1078.004           |
| 51127  | Access from multiple locations concurrently      | A user accessed from multiple geographic locations in a short timeframe. Possible stolen credentials used by multiple adversaries.                                                                                                                         | Valid Accounts: Cloud Accounts                                                                          | T1078.004           |
| 51128  | Bronze Bit exploit                               | A constrained delegation flow was performed by an account without sufficient privileges (Bronze Bit attack, CVE-2020-17049).                                                                                                                               | Privilege Escalation using Exploitation for Privilege Escalation                                                                               | T1068               |
| 51129  | Use of stale endpoint                            | An endpoint not used in the last 90 days became active again, possibly indicating malware or a former employee’s old device.                                                                                                                                | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51130  | Use of stale user account                        | A user account not used in 90 days became active again, potentially indicating malicious reuse or a returning former employee.                                                                                                                              | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51131  | Privilege escalation (endpoint)                  | An endpoint received new privileges, indicating potential unwanted or malicious escalation.                                                                                                                                                                | Privilege Escalation using Valid Accounts (Local)                                                                                              | T1078.001 (approx.) |
| 51132  | Unusual access to an application                 | A user accessed an application for the first time, possibly malicious or over-privileged usage.                                                                                                                                                           | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51133  | Suspicious lateral movement                      | A user performed a network login from a machine that does not normally serve remote requests, possibly indicating lateral movement with stolen credentials.                                                                                                | Lateral Movement using Remote Services                                                                                                         | T1021               |
| 51135  | Unusual login to an endpoint                     | A user logged in (interactively or programmatically) to a machine for the first time, possibly indicating stolen credentials or malware-based lateral movement.                                                                                             | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51137  | Unusual service access to an endpoint            | A user requested access to a service on an endpoint for the first time, possibly malicious lateral movement or data theft.                                                                                                                                 | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51139  | Excessive activity from multiple endpoints       | A user performed logins from an unusual number of endpoints. Could be malware spreading or compromised account misuse.                                                                                                                                     | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51140  | Excessive activity to multiple endpoints         | A user performed logins to multiple endpoints in an unusual pattern, possibly lateral movement or over-privileged access.                                                                                                                                 | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51141  | Suspicious machine alteration                    | A machine account was altered in a way that indicates a noPac exploit attempt (CVE-2021-42278/CVE-2021-42287).                                                                                                                                             | Credential Access using Exploitation for Credential Access (often used for Privilege Escalation)                                               | T1068 (approx.)     |
| 51142  | Identity verification timed out                  | A user didn't respond to a policy identity verification request (MFA), possibly indicating malicious credential use or user unawareness.                                                                                                                   | Not applicable                                                                                                                                 | N/A                |
| 51143  | Identity verification denied                     | A user explicitly denied a policy identity verification request (MFA), possibly indicating malicious credential use.                                                                                                                                        | Not applicable                                                                                                                                 | N/A                |
| 51144  | Policy rule match (access)                       | An Identity Protection policy rule was triggered by access.                                                                                                                                                                                                | Not applicable                                                                                                                                 | N/A                |
| 51145  | Policy rule match (federated access)             | An Identity Protection policy rule was triggered by federated access.                                                                                                                                                                                      | Not applicable                                                                                                                                 | N/A                |
| 51146  | Policy rule match (account event)                | An Identity Protection policy rule was triggered by an account event.                                                                                                                                                                                      | Not applicable                                                                                                                                 | N/A                |
| 51147  | Policy rule match (detection)                    | An Identity Protection policy rule was triggered by a detection.                                                                                                                                                                                           | Not applicable                                                                                                                                 | N/A                |
| 51148  | Privilege escalation (Azure service principal)   | An Azure service principal received new privileges, possibly indicating unwanted cloud privilege escalation.                                                                                                                                                | Privilege Escalation using Valid Accounts (Cloud Accounts)                                                                                     | T1078.004           |
| 51153  | Skeleton key attack                              | A domain controller is rejecting recommended crypto algorithms and using weaker RC4, possibly a Skeleton Key attack or misconfiguration.                                                                                                                   | Modify Authentication Process: Domain Controller Authentication                                                                                | T1556 (approx.)     |
| 51155  | Suspicious LDAP search (KrbRelay)                | A user executed a suspicious LDAP search indicating a KrbRelay or KrbRelayUp attempt for privilege escalation.                                                                                                                                             | Privilege Escalation using Exploitation for Privilege Escalation                                                                               | T1068               |
| 51156  | Honeytoken account alteration                    | A honeytoken account was altered (e.g., password reset, enabling a disabled account), indicating a potential exploitation attempt.                                                                                                                          | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51157  | Honeytoken account activity                      | A honeytoken account was used, indicating potentially unauthorized or malicious activity.                                                                                                                                                                 | Valid Accounts: Domain Accounts                                                                                                                | T1078.002           |
| 51158  | OverWatch Identity detection                     | Falcon OverWatch detected malicious activity related to an identity-based event; the underlying detection type varies.                                                                                                                                     | Falcon OverWatch using technique relevant to underlying identity detection                                                                     | Varies             |
| 51159  | Suspicious LDAP search (AD-CS reconnaissance)    | A user executed a suspicious LDAP query enumerating Active Directory Certificate Services configuration, indicating reconnaissance.                                                                                                                         | Discovery using Network Service Discovery                                                                                                      | T1046               |
| 51160  | Anomalous certificate-based authentication       | A user performed an anomalous certificate-based authentication, which might indicate suspicious activity from the source endpoint.                                                                                                                         | Not specified                                                                                                                                 | N/A                |
| 51161  | Anomalous certificate-based auth (user mismatch) | A lower-privileged entity performed an unusual Kerberos certificate-based authentication to a higher-privileged entity, possibly malicious.                                                                                                               | Not specified                                                                                                                                 | N/A                |
| 51162  | Anomalous certificate-based auth (unusual TGS request)  | A user executed a self-request for a Ticket Granting Service (TGS) after a Kerberos certificate-based authentication, possibly malicious.                                                                                                                  | Not specified                                                                                                                                 | N/A                |
| 51163  | Suspicious LDAP search (ML)                      | A user executed a suspicious LDAP query that the ML model deemed high-confidence malicious, often resembling known attack tools or TTPs.                                                                                                                   | Discovery using Account Discovery: Domain Account                                                                                              | T1087.002           |
| 51164  | Suspicious web-based activity (ML)               | A user performed a web-based activity considered anomalous by a machine learning model, possibly compromised credentials.                                                                                                                                  | Initial Access using Valid Accounts: Cloud Accounts                                                                                            | T1078.004           |
| 51165  | Unusual access to a user entity (Kerberoasting)  | An end user accessed the service principal name (SPN) registered to a user account, possibly for Kerberoasting (offline password cracking).                                                                                                                 | Credential Access via Stealing or Forging Kerberos Tickets                                                                                    | T1558.003           |
