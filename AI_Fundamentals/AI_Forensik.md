AI/ML can improve and support DFIR (Digital Forensik and incident Response)
AI/ML → helps DFIR → faster data analysis + anomaly detection + scalability.

two AI capabilities in digital forensics and incident response (DFIR):
1. Automated Event Timeline Reconstruction
   * The AI acts like a digital detective connecting the dots to rebuild a clear, step-by-step story of an attack.
   * It gathers scattered clues from everywhere—server history, firewall warnings, file modification dates, and app records—and automatically arranges them in exact chronological order
2. Anomaly Detection
   * Security systems can automatically block unusual actions before a hacker causes serious damage.
3. Malware Detection/Analysis 
    * using dynamic analysis 

To use AI without risking a case being dismissed in court, investigators must adapt:
   * On-Premises / Controlled Systems: Instead of using commercial cloud APIs, forensic teams must host open-source or specialized AI models locally on isolated, non-networked machines. This keeps evidence strictly inside the lab.
   * Full Prompt & Output Logging: Every prompt sent to the AI, every parameter used (like temperature or seed numbers), and every intermediate response must be automatically captured and appended to the case's audit log.
   * Human-in-the-Loop Verification: AI outputs should serve as an assistant to point investigators toward original raw evidence, rather than replacing the raw evidence itself. An investigator must manually verify the AI's findings back to the original source file.


embedded macro executing shell commands: 
- A macro is a small automated script or program placed directly inside an everyday document
- Think of it like opening a normal-looking Microsoft Word document or Excel file, but inside that file, there is a hidden code snippet designed to trick your computer.
  1. The Trap: An attacker emails you a document (like a fake invoice). Inside this file, they hide a small script called a macro.
  2. The Execution: When you open the file and click "Enable Content," that hidden script secretly wakes up.
  3. The Shell Command: Instead of doing normal document stuff, the script opens your computer's background command terminal (like PowerShell or CMD on Windows) and types in secret commands.
  4. The Result: Those commands silently tell your computer to download malware, steal your passwords, or give the hacker remote access.