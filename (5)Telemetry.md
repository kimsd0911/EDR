Endpoint Telemetry(Summary)

Telemetry is event data collected to help observe and analyze activity on a system. In endpoint security, this includes records of processes run on PCs or servers, network connections, file changes, and other events. Rather than judging an activity as malicious based on a single event, analysts should correlate related events—such as process execution, network connections, and file changes—to understand the broader context.

![(5)Telemetry)]((5)Telemetry.png)

Commonly Collected Data
    • Which user or account launched a process
    • Which process was launched
    • Whether the parent process is expected

Practical Analysis Workflow
    1. Establish the timeline: Identify when the incident began and which endpoints are involved.
    2. Examine processes: Review parent–child relationships, the account used, file paths, and command lines.
    3. Correlate events: Check related network connections and file or registry changes.
    4. Expand the scope: Determine whether the same indicators appear on other endpoints.
    5. Validate and document: Assess whether the activity is legitimate, and record the evidence supporting the assessment and any actions taken.

When Investigating Suspicious Activity
    • Look for processes launched from unfamiliar paths or by unexpected parent processes.
    • Gather related events into a timeline and verify whether the activity was part of an authorized change.