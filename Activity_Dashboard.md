## Activity Dashboard Triage & Prioritization

On the Activity Dashboard, a SOC Analyst prioritizes high-risk alerts over the total volume of new detections to conduct effective alert triage[cite: 3, 4].

![Activity_Dashboard](Activity_Dashboard.png)

* **Priority Alerts**: Highlighted in red, the three `High` severity detections are prioritized for immediate investigation[cite: 3, 6].
* **MITRE ATT&CK Context**: The `Command and Control via Remote...` classification indicates high-risk activity where an internal host attempts to communicate with an external C2 server[cite: 3, 6].
* **Next Investigation Steps**: Click `See detection` to inspect the underlying process tree, command-line arguments, and external network connections to determine whether immediate host isolation is required[cite: 3, 4, 6].