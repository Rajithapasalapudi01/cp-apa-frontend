# CloudSentinel — Cloud Security Posture & Attack-Path Analysis Frontend

This is the **frontend-only** implementation for the academic project:

**Cloud Security Posture and Attack-Path Analysis**

The frontend is intentionally built with **sample/demo data**. It does not connect to AWS, Prowler, ScoutSuite, Checkov, Terraform, CloudTrail, or a database yet.

## 1. Requirements

Install these first:

- Node.js LTS
- VS Code (recommended)
- A modern browser: Chrome / Edge / Firefox

Check installation:

```bash
node --version
npm --version
```

## 2. Run the project

Open the project folder in VS Code.

Open VS Code Terminal:

```bash
npm install
npm run dev
```

Vite will display a local address similar to:

```text
http://localhost:5173/
```

Open that address in your browser.

## 3. Login

This is demo mode.

Use any non-empty username and password.

The login page uses:

```text
Username: admin
Password: admin123
```

The values are not sent to a backend.

## 4. Frontend pages

- `/login` — Login
- `/dashboard` — Security overview
- `/accounts` — Cloud environment/accounts
- `/resources` — Resource inventory
- `/findings` — Security findings
- `/attack-paths` — Attack-path graph
- `/remediation` — Remediation workflow
- `/policies` — Policy guardrails
- `/monitoring` — Events and alerts
- `/reports` — Report generation UI
- `/settings` — Settings
- `/help` — Project guide

## 5. What is already implemented

### Dashboard
- Security posture score
- Critical/high/medium/low findings
- Resource count
- Remediation count
- Posture trend
- Severity chart
- Recent findings
- Top attack paths

### Findings
- Search/filter UI
- Severity filters
- Status filters
- Prowler / ScoutSuite / Checkov labels
- Finding table
- Severity/status badges

### Attack Paths
- Attack-path graph UI
- Entry → weakness → identity → impact flow
- Detected path list
- Path details
- Project explanation callout

### Remediation
- Remediation status cards
- Remediation table
- Terraform/IaC workflow visualization

### Policy Guardrails
- Checkov/custom policy table
- Passed/failed results
- Guardrail explanation

### Monitoring
- Event volume
- Active alerts
- Security event table

### Reports
- Report types
- Generate/download UI

## 6. Important: this is frontend phase only

Do NOT put AWS credentials in this React frontend.

Later, the backend should provide APIs such as:

```text
GET /api/dashboard
GET /api/accounts
GET /api/resources
GET /api/findings
GET /api/attack-paths
GET /api/remediation
GET /api/policies
GET /api/events
POST /api/assessments/run
GET /api/reports
```

Then the frontend's sample arrays in `src/main.jsx` can be replaced with API calls.

## 7. Recommended next project phase

After your sir approves the frontend:

1. Build backend API
2. Add database
3. Connect authentication
4. Connect AWS lab account
5. Execute Prowler
6. Execute ScoutSuite
7. Execute Checkov against Terraform
8. Store normalized findings
9. Build attack-path analysis
10. Connect remediation workflow
11. Add CloudTrail/log ingestion
12. Generate real reports
13. Re-run assessments and show before/after posture

## 8. Project safety

Use only your authorized academic cloud lab.

The intended architecture is:

```text
React Frontend
       ↓
Backend API
       ↓
Database
       ↓
Assessment / Analysis Services
       ↓
AWS Academic Lab
       ↓
Prowler / ScoutSuite / Checkov / CloudTrail
```
