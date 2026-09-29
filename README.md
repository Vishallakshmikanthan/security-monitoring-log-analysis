# 🛡️ Security Monitoring & Log Analysis — Live SOC Simulator

An interactive, retro Windows 98-themed live Security Operations Center (SOC) simulation environment. This project demonstrates how modern security analysts collect telemetry, normalize multi-source logs, query SIEM platforms, correlate events across domains, and reconstruct an incident timeline from raw alerts to incident response.

---

## 🖥️ Live Demonstration Preview

Built entirely with standard vanilla web technologies (HTML, CSS, JavaScript) inside a single lightweight file, featuring:
- **Authentic Windows 98 UI**: Beveled windows, draggable interface, taskbar, start menu, CRT monitor scanline overlay, and nostalgic styling.
- **Presentation Mode**: Fullscreen/high-contrast layout designed for security demonstrations, workshops, and lectures.
- **Zero Dependencies**: Self-contained client-side application with no external libraries or remote API requirements. Runs instantly in any modern web browser.

---

## 🔍 Simulation Workflow (10-Stage Pipeline)

The simulator steps through the full lifecycle of a security detection & analysis workflow:

| Stage | Name | Description |
| :---: | :--- | :--- |
| **00** | **System Ready** | Initializes SOC monitoring console, telemetry log collectors, and detection engines. |
| **01** | **Log Collection** | Ingests raw telemetry across multiple disparate security sources (VPN, Active Directory, Sysmon/EDR, Firewall/DNS). |
| **02** | **Normalization** | Demonstrates raw log parsing into unified schema fields (e.g. `user.name`, `host.name`, `source.ip`, `@timestamp`). |
| **03** | **SIEM Ingestion** | Interactive SIEM console with full search, tabular view, and sample queries in **Splunk SPL** and **Microsoft Sentinel KQL**. |
| **04** | **Detection** | Evaluates a **Sigma-style detection rule** against the incoming event stream to trigger alert conditions. |
| **05** | **Event Correlation** | Multi-factor correlation linking Identity + Host + Source IP + Temporal Proximity + Ordered Kill Chain Sequence. |
| **06** | **High-Priority Alert** | Dispatches a prioritized alert with incident details and triage actions. |
| **07** | **Investigation** | Opens parallel investigation tools: Timeline reconstructor, Sysmon/EDR viewer, Zeek-style network logs, and case notes. |
| **08** | **Timeline Reconstruction** | Guided analyst checklist verifying identity consistency, host involvement, time boundaries, and MITRE ATT&CK alignment. |
| **09** | **Analyst Conclusion** | Synthesizes findings, confirms suspicious activity, and documents analysis rationale and uncertainties. |
| **10** | **Response / Next Action** | Execute simulated incident response actions (evidence preservation, credential review, host telemetry collection, containment escalation). |

---

## 🛠️ Security Technologies & Standards Simulated

This simulator incorporates conceptual workflows and syntaxes from industry-standard tools:
- **Telemetry & Endpoint Detection**: Sysmon (`EventID 1`, `EventID 4728`), EDR process creation tracking, Identity/VPN audit records.
- **Network Analysis**: Zeek-style connection logs (`conn.log`), DNS query logs (`dns.log`), and Wireshark packet capture visualization.
- **SIEM & Search Queries**:
  - **Splunk**: Search Processing Language (SPL) aggregation queries.
  - **Microsoft Sentinel**: Kusto Query Language (KQL) time-window correlation queries.
- **Detection Engineering**: Sigma YAML rule specifications.
- **Framework Alignment**: MITRE ATT&CK mapping (Credential Access, Privilege Escalation, Execution, Command & Control).

---

## 🚀 Getting Started

### Prerequisites
- Any modern web browser (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari, Brave, etc.)
- No installation, node packages, or servers required!

### Running the Simulator
1. Clone this repository:
   ```bash
   git clone https://github.com/Vishallakshmikanthan/security-monitoring-log-analysis.git
   cd security-monitoring-log-analysis
   ```
2. Open `index.html` (or `soc_windows98_simulation.html`) directly in your web browser:
   - On Windows: Double-click `index.html` or run:
     ```powershell
     Start-Process index.html
     ```
   - On macOS:
     ```bash
     open index.html
     ```
   - On Linux:
     ```bash
     xdg-open index.html
     ```

---

## 🕹️ Controls & Navigation

- **Start Simulation**: Begins ingestion of security telemetry.
- **Next Step**: Steps sequentially through each stage of the analysis pipeline.
- **Auto Play**: Automatically plays through the initial detection stages (Stages 1 through 6) at timed intervals.
- **Show Evidence**: Opens deep-dive windows for Authentication, EDR, and Network evidence.
- **Investigate**: Jumps straight to the analyst investigation workbench.
- **Interactive Highlighting**: Click any `USER`, `HOST`, or `SOURCE IP` value in the SIEM or correlation views to highlight related events across all open windows.
- **Presentation Mode**: Click `PRESENTATION MODE` on the toolbar or press `View > Presentation Mode` for enlarged text and focused window layout.

---

## ⚠️ Synthetic Data Disclaimer

All events, IP addresses (e.g. `203.0.113.45`, `198.51.100.25` using [RFC 5737](https://datatracker.ietf.org/doc/html/rfc5737) documentation ranges), user accounts, hosts, and domain names used within this simulator are **100% synthetic**. No malicious code is executed, and no external network requests are dispatched.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
