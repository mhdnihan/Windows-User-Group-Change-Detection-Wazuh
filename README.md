# Windows-User-Group-Change-Detection-Wazuh
Investigation -- Windows User Group Change Detection 


Windows User Group Change Detection — Wazuh

Objective

Detect changes involving Windows user/group membership and investigate the associated Wazuh alert.

Test Activity

A temporary local user account was created during a controlled account-management security test.

The account-management activity generated a user/group-related Windows Security event.

Wazuh Detection

* Rule ID: 60160
* Level: 5
* Description: Domain user group changed
* System Event Id: 4729
* MITRE ATT&CK: T1484
* MITRE TACTIC: Defense Evasion, Privilege Escalation
* MITRE TECHNIQUE : DOMAIN POLICY MODIFICATION 

Investigation

The group-related alert was reviewed in the context of the other account-management alerts generated at approximately the same time.

The timing and account information can be used to correlate this event with the original administrative activity.

SOC Relevance

Changes to user or privileged group membership can be security-sensitive because group membership can affect a user’s permissions.

An analyst should investigate:

* Who made the change?
* Which account was affected?
* Which group was modified?
* Was the change authorized?
* Were other related account changes observed?

Key Learning

Identity and access events should be investigated together rather than in isolation. Group membership changes can provide important context when investigating potential privilege-related activity.

Result: Wazuh detected the user/group-related Windows Security event.
