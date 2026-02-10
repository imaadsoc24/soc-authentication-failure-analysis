# soc-authentication-failure-analysis
Simulated SOC investigation detecting a Windows brute-force attack using Wazuh SIEM and Sysmon logs mapped to MITRE ATT&amp;CK.

🚨 Detection Triggered
Wazuh generated alerts based on Windows Event ID:
Event ID
Meaning
4625
Failed Logon Attempt
4624
Successful Logon
Sysmon 11
Suspicious File Creation
🧠 MITRE ATT&CK Mapping
Technique
ID
Valid Accounts
T1078
Brute Force
T1110
Account Access Removal
T1531
📊 Observed Behavior
Multiple failed logins detected
Source: Local machine (127.0.0.1)
Target account: victim123
Authentication package: Negotiate
Status: 0xC000006A (Bad Password)
This pattern indicates a password guessing attack.
🔍 Key Alert (Wazuh)
Logon failure — Unknown user or bad password
Severity Level: 5 → escalated to 10 after multiple attempts
🛡️ Analyst Conclusion
The activity matches a local brute force attack simulation.
Repeated authentication failures followed by successful login confirms credential guessing behavior.
🧯 Recommended Response
Lock account after threshold attempts
Enable account lockout policy
Monitor repeated Event ID 4625
Implement MFA
