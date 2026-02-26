Gmail Security Scanner
Personal Portfolio Project - Technical Security Implementation
Overview
The Gmail Security Scanner is a cloud-native Add-on designed to detect and mitigate phishing and social engineering attempts in real-time. By leveraging heuristic analysis of email metadata and content, it provides users with an immediate risk assessment (Green/Yellow/Red) and actionable security insights directly within the Gmail interface.

Key Features
Heuristic Threat Analysis: Scans email bodies for high-pressure keywords and common social engineering patterns.

Link Validation Engine: Identifies insecure http protocols and flags suspicious URL structures.

Attachment Guard: Real-time detection of dangerous file extensions (e.g., .exe, .zip) used for malware delivery.

Persistent Reputation System: Implements a custom "Blacklist" using Google’s PropertiesService, allowing the system to remember and flag repeat offenders.

Dynamic Security Scoring: A weighted algorithm that calculates a risk score (0-100) based on multiple threat vectors.

Technical Stack
Runtime: Google Apps Script (JavaScript ES6+)

APIs: Gmail API & Google Workspace Card Service

Storage: PropertiesService (Key-Value cloud storage for persistence)

Architecture: Event-driven UI that triggers upon email selection.

Installation & Deployment
Open Google Apps Script.

Create a new project named Gmail-Security-Scanner.

Replace the default code with the provided Code.gs and update the appsscript.json manifest.

Important: Enable the Gmail API under the "Services" tab (+).

Click Deploy > Test Deployments.

Install the Add-on and open any email in Gmail to see the scanner in action.

Future Roadmap (Scalability & Advanced Security)
External Threat Intel Integration: Connecting to APIs like VirusTotal or URLScan.io for real-time reputation checks of files and links.

AI/NLP Detection: Implementing Large Language Models (LLMs) to identify sophisticated "Business Email Compromise" (BEC) and spear-phishing attempts.

Organizational Whitelisting: A centralized admin dashboard to manage safe/blocked senders across an entire company domain.

Automated Incident Response: Integration with Slack/Teams to alert security teams when a high-risk threat is detected.

Security & Privacy
Principle of Least Privilege: Uses restricted OAuth scopes (current.message.readonly) to ensure the application only accesses the context of the open email.

Privacy by Design: All processing happens within the user’s secure Google environment.

Zero External Dependencies: The current MVP does not share email data with external servers, ensuring 100% data privacy.
