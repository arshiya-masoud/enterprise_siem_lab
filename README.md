# Enterprise SIEM Lab — Offline Demonstration

## Project status
This repository contains an **offline educational demonstration** of a basic SIEM workflow. It is **not a completed/live Wazuh deployment**. The included events are synthetic sample data created for testing and learning.

## Objective
Demonstrate a simplified security-monitoring workflow: review sample authentication events, count repeated failed logins, generate a demonstration alert, and recommend an analyst follow-up.

## Technologies
- Python 3.10+
- Python standard library (`collections`, `json`, `pathlib`)
- Wazuh is the intended SIEM platform for a future live implementation, but this script does not connect to Wazuh.

## Files
- `siem_demo.py` — runnable analysis and simple detection rule.
- `requirements.txt` — states that no third-party dependencies are needed.
- `YourName_ProjectReport.docx` — project documentation template/report.
- `demo_events.json` — generated when the script runs; contains synthetic events and demo alerts.
- `YourName_ProjectName.ipynb` — notebook version of the demonstration.

## Run
1. Install Python 3.10 or newer.
2. Open a terminal in this folder.
3. Run:
   ```bash
   python siem_demo.py
   ```
4. The script prints event counts and any demo alerts, and creates `demo_events.json`.

No `pip install` command is required because the script uses only the Python standard library.

## Detection logic
The demo flags a source IP when it appears in at least three synthetic `failed_login` events. This is a simple illustrative rule, not a production detection rule and not equivalent to Wazuh's native detection engine.

## Limitations and next steps
- Events are synthetic and do not represent real activity from a user's Windows or Ubuntu machine.
- No Wazuh server, agent, indexer, or dashboard is configured by this script.
- For a full project, deploy Wazuh, enroll a Windows/Linux agent, collect real lab telemetry, validate a custom Wazuh rule, and replace simulated results with actual screenshots and findings.
- Do not upload credentials, private keys, or sensitive logs.

## Dataset
There is no external dataset. The sample events are embedded in `siem_demo.py` and are explicitly synthetic.
