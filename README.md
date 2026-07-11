# Automated IP Reputation Checker

An n8n workflow that checks the reputation of an IP address using the VirusTotal API and sends notifications to Slack.

## Features

* User-friendly form input for IP addresses
* VirusTotal API integration
* Automatic malicious IP detection
* Slack notifications for security alerts
* Clean IP confirmation messages

## Workflow Overview

```text
Form Trigger
     ↓
VirusTotal API Request
     ↓
Check Reputation Score
     ↓
 ┌───────────────┬───────────────┐
 │ Reputation < 0 │ Reputation ≥ 0 │
 └───────────────┴───────────────┘
         ↓                 ↓
  Slack Alert      Slack Confirmation
```

## Technologies Used

* n8n
* VirusTotal API
* Slack API
* JSON Workflow Automation

## Setup Instructions

### 1. Import Workflow

Import the `ip-reputation-checker.json` file into your n8n instance.

### 2. Configure VirusTotal

Replace:

```json
{
  "name": "x-apikey",
  "value": "YOUR_API_KEY_HERE"
}
```

with your VirusTotal API key.

### 3. Configure Slack

Create Slack credentials in n8n and connect them to the Slack nodes.

### 4. Activate Workflow

Enable the workflow and start checking IP addresses.

## Example

### Input

```text
8.8.8.8
```

### Output

```text
✅ IP CLEAN!
IP is safe according to VirusTotal.
```

or

```text
⚠️ MALICIOUS IP DETECTED!
Reputation Score: -10
Malicious Detections: 15
```

## Security Note

Do not upload API keys, tokens, or credentials to GitHub.

## Author

David Khoury

Computer Engineering Student
Specializing in Systems & Network Engineering


