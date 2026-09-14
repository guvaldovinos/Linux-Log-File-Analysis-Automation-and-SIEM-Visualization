<h1>🐧 Linux Log Analysis, Automation & SIEM Visualization</h1>

---

<h2>🧠 Description</h2>
This lab demonstrates a progressive SOC (Security Operations Center) log analysis workflow — starting with manual log review, moving to automated detection with Python, and finishing with SIEM-based visualization in Splunk.
This task simulates how a SOC Analyst's tooling matures from manual triage to scaled, automated monitoring, using a real-world Linux authentication log dataset (LogHub).

---

<h2>🖥️ Environment</h2>

* Dataset: Linux_2k.log (LogHub Linux authentication logs)
* Tools: VS Code, Python 3.x, Excel/Google Sheets, Splunk Enterprise (free trial)
* OS: Windows
---

<h2>⚙️ Steps Completed</h2>

**Objective 1 — Manual Log Analysis**
1. Downloaded the Linux_2k.log dataset from LogHub.<img width="2532" height="1256" alt="Screenshot 2026-09-13 154935" src="https://github.com/user-attachments/assets/0ded1da4-a5b7-4d07-a7a9-22462a1f46b8" />

2. Reviewed the first 40 lines of the log file in VS Code.<img width="2549" height="1366" alt="Screenshot 2026-09-13 155003" src="https://github.com/user-attachments/assets/89aea17c-7c46-4bba-ba34-b543ee721a44" />

3. Identified suspicious entries: repeated failed logins, unknown/invalid users, and abnormal system alerts. Organized findings into a table in Excel to spot patterns.<img width="931" height="574" alt="Screenshot 2026-09-13 200019" src="https://github.com/user-attachments/assets/e1a31264-2e9f-478d-ab6e-85c13c473e11" />

5. Short SOC-style report:

---


**Objective 2 — Automating Log Analysis (Python)**
1. Wrote a Python script (`log_analysis.py`) to scan log lines 200-500 for suspicious keywords: "Failed password," "authentication failure," "user unknown," and "invalid user."<img width="2541" height="1282" alt="Screenshot 2026-09-13 173950" src="https://github.com/user-attachments/assets/1efb6990-55a3-4875-b361-cd4231419f3f" />

2. Ran the script to automatically flag and print suspicious entries with their event type.<img width="2558" height="1305" alt="Screenshot 2026-09-13 174122" src="https://github.com/user-attachments/assets/35c0995e-5061-473b-ba81-93cf54b11f60" />

3. Extended the script to export all flagged entries to a structured CSV file (`suspicious_logs.csv`) for further analysis.<img width="2547" height="1360" alt="Screenshot 2026-09-13 175823" src="https://github.com/user-attachments/assets/dba2ca26-ceb9-4843-b4b3-38e34c190faa" />

4. Opened the file in Excel <img width="1210" height="1118" alt="Screenshot 2026-09-13 175934" src="https://github.com/user-attachments/assets/fbe69bb8-279b-4e6d-ac8c-df98727fb256" />

---


**Objective 3 — Log Analysis & Visualization with Splunk (SIEM)**
1. Installed Splunk Enterprise (free trial) and created an admin account.
   <img width="2518" height="1252" alt="Screenshot 2026-09-13 182546" src="https://github.com/user-attachments/assets/bbbbaac3-3f10-4906-9e79-d4c1c6cf3d4c" />

2. Uploaded the Linux_2k.log file via Settings → Add Data → Upload, configuring source type, host, and index.

<img width="2522" height="1231" alt="Screenshot 2026-09-13 182735" src="https://github.com/user-attachments/assets/f3b2517c-b9b5-457e-a9c6-f7b21233b88f" />


<img width="2529" height="1250" alt="Screenshot 2026-09-13 182901" src="https://github.com/user-attachments/assets/e01e374f-2a79-450a-b0aa-d3fe8b8496a2" />

<img width="2477" height="1251" alt="Screenshot 2026-09-13 182943" src="https://github.com/user-attachments/assets/11918130-722e-48bd-8fef-1974a633707d" />

<img width="2532" height="1240" alt="Screenshot 2026-09-13 183035" src="https://github.com/user-attachments/assets/00a5c892-e4e8-4b48-bc44-3ff3ee70898e" />
<img width="2524" height="1228" alt="Screenshot 2026-09-13 183148" src="https://github.com/user-attachments/assets/a0b04d64-bf88-40a4-8244-be197e88419f" />


3. Queried the indexed logs using SPL to filter authentication-related events:<img width="2539" height="1257" alt="Screenshot 2026-09-13 183405" src="https://github.com/user-attachments/assets/82faf0d4-099f-43b5-9219-be60eb9106e1" />


4. Reviewed results across four views — **Events**, **Patterns**, **Statistics**, and **Visualization** — to identify and confirm a brute-force pattern targeting the root account.


<img width="2505" height="1245" alt="Screenshot 2026-09-13 183623" src="https://github.com/user-attachments/assets/2781f73f-5f5c-4f4c-b308-4dc5beb03a13" />

<img width="2533" height="1128" alt="Screenshot 2026-09-13 183721" src="https://github.com/user-attachments/assets/8f3e5bd1-c369-45f3-b3a7-42fef240fdd9" />
<img width="2556" height="1206" alt="Screenshot 2026-09-13 185202" src="https://github.com/user-attachments/assets/265f8a24-50e4-4528-94db-83f6bf3826f7" />
<img width="2551" height="1235" alt="Screenshot 2026-09-13 185439" src="https://github.com/user-attachments/assets/88a4840c-f974-4295-874e-e96c2e998069" />

<h2>📊 Findings</h2>

**Manual & Automated Analysis**
* Repeated failed login attempts targeting the `root` account from IP addresses `218.188.2.4` and `220.135.151.1`
* Multiple "user unknown" entries, indicating attackers probing random usernames
* One "ALERT exited abnormally" event, flagged for further investigation




<h2>🧩 Key Skills Demonstrated</h2>

* Manual log review and SOC triage fundamentals
* Python scripting for automated log parsing and CSV export
* Splunk Enterprise setup, log ingestion, and indexing
* SPL (Search Processing Language) querying for authentication events
* Using Events, Patterns, Statistics, and Visualization views to identify and confirm attack patterns at scale
* Correlating manual, automated, and SIEM-based findings into a single investigative workflow






