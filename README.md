# Linux-Auditd-File-Integrity-Monitoring
Linux cybersecurity project using auditd to monitor file changes, analyze audit logs, and investigate simulated attacks.

## Overview

In this cybersecurity project, I used Linux Audit (`auditd`) to monitor protected files and investigate unauthorized file modifications.

I configured audit rules to track write activity, executed simulated attacks, and analyzed the audit logs to determine which files were modified and which processes were responsible.

##  Tools Used

- Ubuntu Linux
- auditd
- auditctl
- ausearch
- Linux CLI

##  File Monitoring

I configured Audit rules to monitor protected files for write activity.

Example:

`bash
sudo auditctl -w "$HOME/project2-main/protected_files/cloudia.txt" -p w -k cloudia
`
<img width="1094" height="242" alt="file monitoring commands" src="https://github.com/user-attachments/assets/ed2f3dde-0c02-4f98-8497-b2a5c99971ed" />


I verified that the monitoring rules were active using:

```bash
sudo auditctl -l
```

## Attack Simulation

Three simulated attacks were executed:

```bash
./attack-a
./attack-b
./attack-c
```

I then searched the Audit logs using:

```bash
sudo ausearch -ts recent -i
```
<img width="1418" height="945" alt="file permission and modifiction" src="https://github.com/user-attachments/assets/42cbab86-9ef4-45be-80cc-58cc12d3c211" />


# Discovery

My investigation identified the following file modifications:

| Attack | Modified File |

| attack-a | cloudia.txt |
| attack-b | oakley.txt |
| attack-b | squeaky.txt |
| attack-c | precipitation.csv |

The audit logs allowed me to connect each modified file to the process responsible for the change.

# understanding i gained

This project helped me understand how Linux auditing can be used during incident response to determine what changed on a system and which process caused the change.

I gained hands-on experience with:

- Linux security monitoring
- File integrity monitoring
- Audit log analysis
- Incident response
- Digital forensics
- Process attribution



#  Key Takeaway

Security monitoring is most useful when it is configured before an incident occurs. Audit logs provide evidence that analysts can use to reconstruct system activity and investigate suspicious changes.



(DO)
