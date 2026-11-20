## Activity Dashboard Triage & Prioritization

Activity dashboard에서 SOC Analyst는 전체 New detections 수보다 실제 위협도가 높은 Alert를 우선 선별해 Triage를 수행합니다[cite: 4].

![Activity_Dashboard](Activity_Dashboard.png)

* **Priority Alert**: 빨간색으로 표시된 `High` Severity 경보 세 건을 최우선 조사 대상으로 분류합니다[cite: 4, 7].
* **MITRE ATT&CK Context**: `Command and Control via Remote...` 항목은 내부 Host가 외부 C2 인프라와 통신을 시도하는 고위험 행위를 의미합니다[cite: 4, 7].
* **Investigation Step**: `See detection`을 클릭해 상세 Process, Command Line, 외부 통신 대상을 확인하고 Host Isolation 여부를 판단합니다[cite: 4, 7].