
EDR collects activity from endpoints and detects suspicious behavior. A SOC analyst reviews telemetry and IOCs to distinguish legitimate activity from malicious activity, identify the root cause and progression of an attack, and take appropriate response measures—such as isolation—to limit further damage and prevent the attack from spreading.

1. Why Is This Process Suspicious?
To assess whether a process is suspicious, review the following:

    • Process name: Check whether the process name matches a legitimate system process.
    • File path: Check where the process was launched from. Be cautious if it runs from a user-writable location such as Temp, AppData, or Downloads.
    • Parent process: Identify which process launched it.
    • Command line: Analyze the command and arguments used to start it.
    • Digital signature: Check whether the file has a valid digital signature.
    • Behavior: Look for activity such as encoded PowerShell commands, unusual external communications, file creation, or registry modifications.

Example: If Microsoft Word launches PowerShell immediately after a user opens a document, and PowerShell uses an encoded command to communicate with an external server, the behavior may be suspicious.
A single indicator is not enough to conclude that a process is malicious. Assess multiple pieces of evidence together.

2. How Do You Distinguish Legitimate from Malicious Activity?

Distinguish between legitimate and malicious activity by analyzing the process’s execution context and behavior patterns.

Legitimate activity may include:
    • A process launched by a trusted application
    • Execution from a standard installation directory
    • A valid digital signature
    • An execution pattern consistent with normal user activity
    • Expected network communications

Potentially malicious activity may include:
    • An unusual parent–child process relationship
    • Obfuscated or encoded commands
    • Communications with suspicious external IP addresses
    • Unknown files running from a user’s temporary folders
    • Unusual registry modifications or attempts to establish persistence
    • Attempts to access or exfiltrate sensitive data

Example: Running PowerShell is not inherently suspicious. However, if an Office application launches PowerShell and it uses an obfuscated command to download a file from an external server, the activity is more likely to be malicious.

3. How Do You Determine Whether an IP Address or File Hash Is Malicious?
Use indicators of compromise (IOCs) to investigate suspicious IP addresses and file hashes.

IP address investigation:
    • Check the IP address’s detection history on VirusTotal.
    • Review reported malicious activity and reputation on AbuseIPDB.
    • Check the IP’s reputation using Cisco Talos Intelligence.
    • Review firewall and EDR logs for communications with the IP address.
File hash investigation:
    • Calculate the file’s SHA-256 hash.
    • Search for the hash on VirusTotal.
    • Review detections from multiple antivirus engines.
    • Examine the file name, type, detection names, and related analysis.

Example: Calculate the SHA-256 hash of a suspicious executable and search for it on VirusTotal. If multiple security engines detect the same file as malicious and related analysis also shows malicious behavior, the file is more likely to be malicious.

Important considerations:
    • An IP address or hash with no detections is not necessarily safe.
    • Do not rely on VirusTotal results alone to determine whether something is malicious.
    • Consider current threat intelligence alongside observed behavior.

4. How Did the Attack Progress?
Analyze telemetry and process execution records to reconstruct the full attack chain.

Example attack timeline:
    1. Initial access: A user opens an attachment from a malicious email.
    2. Execution: The malicious document launches a PowerShell process.
    3. Defense evasion: The attacker obfuscates commands in an attempt to evade security detection.
    4. Command and control (C2): The compromised endpoint communicates with an external server controlled by the attacker.
    5. Persistence: The attacker attempts to use the registry or another mechanism to ensure the malicious program runs again after a reboot.
    6. Impact: The attacker attempts to deploy ransomware or exfiltrate data.

Analysts use the following data to establish the sequence of events:
    • Process creation events
    • Process termination events
    • Parent–child process relationships
    • Network connection logs
    • File creation and modification events
    • Registry modification events

The MITRE ATT&CK Framework can be used to map observed activity to the corresponding tactics and techniques.

5. What Is the Appropriate Response?
Once malicious activity is confirmed, take steps to prevent the attack from spreading and minimize its impact.

    1. Isolate the endpoint
        ◦ Disconnect the affected endpoint from the network.
        ◦ Help prevent lateral movement to other systems.
    2. Terminate the process
        ◦ Stop the malicious process.
        ◦ Prevent further malicious activity.
    3. Quarantine the file
        ◦ Move the malicious file to quarantine so it cannot run.
        ◦ Decide whether to restore or permanently delete it after analysis.
    4. Block IOCs
        ◦ Block malicious IP addresses and domains using firewalls or other controls.
        ◦ Use file hashes to detect additional copies of the file.
    5. Investigate and document
        ◦ Collect relevant logs and evidence.
        ◦ Determine the attack path and scope of impact.
        ◦ Document the findings and response actions in a report.
        
Important: Automatically isolating a critical business server may disrupt operations. Choose an appropriate response—such as isolation or process termination—based on the system’s importance and the severity of the threat.

Conclusion
EDR collects activity from endpoints and detects suspicious behavior. A SOC analyst reviews telemetry and IOCs to distinguish legitimate activity from malicious activity, identify the root cause and progression of an attack, and take appropriate response measures—such as isolation—to limit further damage and prevent the attack from spreading.

