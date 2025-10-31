# Zero_Day — AI-Driven Insider Threat & Endpoint Behavior Monitoring System  
A hybrid **PHP + MySQLi + Python Machine Learning** security system designed to protect enterprise workstations from insider threats, abnormal system access, or suspicious behavior patterns.  

Zero_Day learns how employees normally use their assigned work computers, monitors real-time behavior patterns, and immediately responds when unusual or malicious activity is detected.  

Built as an internal security automation tool for corporate environments, this platform combines intelligent behavioral analytics, anomaly detection, network monitoring, automated workstation lockdown, and secure admin reporting.

---

## System Concept

Traditional antivirus and firewalls protect against external threats.  
**Zero_Day protects from the inside — by analyzing how each user behaves.**

The system trains a unique machine-learning profile per workstation to track:

- Normal login times  
- Regular software usage  
- Typical file access patterns  
- Typical RAM & CPU behavior  
- Clipboard & keystroke patterns (non-sensitive trend modeling only)  
- Standard task behavior during working hours  

If the system detects any drastic behavioral deviation, such as:

- Unknown program execution  
- Unauthorized resource access  
- Abnormal CPU/IO usage spikes  
- Suspicious command-line activity  
- Night-time access beyond normal hours  
- Irregular login patterns  
- Malware-like behavior  

Zero_Day **auto-locks the PC**, resets the session credentials, quarantines the machine, and alerts the administrator immediately.

---

## Key Features

### Employee Workstation Monitoring
- Behavioral analysis model trained per employee PC  
- Continuous pattern learning during work hours  
- Offline monitoring capability (auto-sync on network return)  
- Auto detection of irregular PC activity  
- Local daemon executes emergency lockdown when triggered

### Machine Learning Intelligence
- Python-based anomaly detection system  
- Pattern recognition & adaptive learning  
- Auto-generated synthetic training data support  
- Real-time anomaly scoring & classification  
- Historical behavior logs for model refinement  

### Local Daemon Agent (Python)
- Installed on each workstation  
- Works online & offline  
- Lockdown triggers executed locally  
- Password/session reset execution on alert  
- Communicates with central server via API  
- Built into a standalone executable (`ZDAgent.exe`)

### Admin Web Console (PHP + MySQLi)
- Real-time system dashboard  
- PC status monitoring (Active / Suspicious / Locked)  
- Logs for behavior alerts, device events, and actions taken  
- Device health monitoring  
- Online alert & push notification system  
- Admin manual override and unlock access  
- Central security configuration  

### Automated Security Response
- PC lock & forced logout  
- Auto reset workstation password  
- Email alert to security admin  
- Device quarantine flag in the dashboard  
- Full event trail for audit  

---

## Architecture Workflow

1. **Agent Training Phase**  
   Python ML learns workstation daily patterns from usage activity

2. **Monitoring Phase**  
   Daemon runs continuously, comparing behavior against learned patterns  

3. **Anomaly Detected**  
   - Model predicts irregular / malicious activity  
   - Confidence threshold exceeded  

4. **Automatic Response**
   - PC locked locally  
   - Login/password reset  
   - Event logged to server  
   - Email sent to administrator  

5. **Admin Review**
   - Re-authentication & unlocking  
   - Investigation panel  
   - Option to retrain model  

---

## Technology Stack

| Component | Technology |
|---------|------------|
| Backend Web | PHP + MySQLi |
| Server | Apache (XAMPP/LAMP) |
| ML Engine | Python (Pandas, Sklearn, etc.) |
| Communication | Flask API + HTTP requests |
| Client Agent | Python → Compiled to `.exe` |
| DB | MySQL |
| Logging | PHP + JSON structured logs |

---

## File & Folder Structure

