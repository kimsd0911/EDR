🛡️ **EDR (Endpoint Detection and Response)**
Endpoint Detection and Response (EDR) is a security solution that provides in-depth protection for endpoints.

Each node represents a process.
The lines connecting nodes represent relationships between them.

**2. Three Core Components of EDR**
Visibility
Detection
Response
2-1. Visibility
EDR provides visibility into endpoint activity, offering complete context for detections.

**3. Detection**
Detection = Signature-based Detection + Behavior-based Detection

**4. Detection Dashboard**
Key fields include:

Time
Severity
Triggering file
Hostname
Username

**5. Response**

**① The Role and Limitations of EDR**
EDR detects processes, files, and user activity on a device, but it is not designed to monitor every threat present in traffic across the entire network.

NDR is used to monitor threats in network-wide traffic.

**② Tools Used Alongside NDR**
IDS/IPS tools are used alongside NDR. In my experience using AhnLab AIPS, when more than 20 logs were generated, I captured the monitoring screen and escalated it to the security team. Using a WAF tool, I separately collected traffic destined for web servers, analyzed response codes and source IP addresses, and reported my findings.

**③ Security Solutions in Practice**
In practice, EDR, NDR, and firewalls are used together.

Alerts from multiple tools are collected in a SIEM for analysis.

**④ Characteristics of EDR**
EDR does not stop every threat, but it is a solution focused on threat prevention.

It is also used to centrally manage multiple devices and is primarily used by organizations. For personal use, installing a firewall is sufficient.

**6. Basic Difference Between AV (Antivirus) and EDR**
AV (Antivirus): Detects basic threats.
EDR: Detects advanced threats.