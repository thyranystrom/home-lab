# INCIDENT REPORT #1

## Alert summary
Wazuh dashboard triggered an alert with rule level 10, with Wazuh ID 40111/MITRE ATT&CK ID T1110.001 (Brute force) with sub-technique password guessing, indicating multiple failed login attempts targeting the root-user from IP 192.168.56.107.

- **Attack type:** SSH Brute Force 
- **MITRE technique:** T1110.001 (Password guessing)
- **Rule level:** 10 (high)
## Timeline
- The attack happened at May 10 2026, 18:43:15
- Wazuh alert triggered: May 10 2026, 18:43:30
and the IP was blocked shortly afterwards using iptables 
## Source information
- Source ip: 192.168.56.107, 
The activity originated from the Kali Linux attacker VM within my isolated lab environment. 
## Target Information
- Target ip: 192.168.56.108
- Target user: root
## Detection method
It was detected using Wazuh threat hunting events dashboard, and filtering the rule level to 10 and up to see more severe events, and authentication logs showed multiple failed login attempts via ssh.
## Severity
It was severity level 10 (high) indicating multiple user generated errors, the activity was directed at the root thus making it more serious, but none of the login attempts were successful.
## Mitigations
**Short term:**
- Blocked the source-ip using iptables
  
**Long term:**
- Activate MFA
- Implement fail2ban
- Disabling direct root ssh access


