# Windows Event Codes

## Security Audit Log Cleared (Event Code: 1102)
When the audit log is cleared from Windows Event Viewer, the system will generate the event code 1102. It is an event that is typically never seen under normal circumstances. Monitoring and alerting for event code 1102 can be critical in detecting a possible security breach, aid in determining the timeline of an attack, and ensure that host machine logs are not being tampered with. 

We can search in Splunk with the following query:  
`
index="main" host="DESKTOP-ABC123" source="WinEventLog:Security" EventCode="1102"
`


## New User Account Created (Event Code: 4720)
When a new user account is created on a Windows host machine, the system will generate the event code 4720. While the creation of a new user account may be a common and legitimate action, it can also be a possible indicator of unauthorized access and security breach if the new account is not recognized, expected, and/or legitimately authorized. If an attacker is able to gain access to a host, they may create a new local user account to further escalate their privileges or to maintain persistence to the system.

We can search in Splunk with the following query:  
`
index="main" host="DESKTOP-ABC123" source="WinEventLog:Security" EventCode="4720"
`



## Attempt to Reset/Change Account Password (Event Code: 4723, 4724)
When there is an attempt to reset or change an account password, the system will generate the event codes 4723 and 4724 respectively. While resetting and/or changing passwords may be a common and legitimate action, it can also be a possible indicator of a security beach if the actions are attempted by unauthorized individuals. Attackers may attempt to reset/change account passwords to gain unauthorized access, escalate their privlege, maintain persistence, obfiscate log activity, and conduct ransom attacks.

We can search in Splunk with the following query:  
`
index="main" host="DESKTOP-ABC123" source="WinEventLog:Security" (EventCode="4723" OR EventCode="4724")"
`