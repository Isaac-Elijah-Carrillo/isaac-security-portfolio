# MemoryTrap – Security Logging & Detection Lab

## Objective

Design and document structured security logging and detection logic for a production-style mobile SaaS application.

---

## Scope

This lab focuses on identifying security-relevant events, defining structured log schemas, and creating measurable detection rules aligned with SOC workflows.

Some log examples are simulated to represent expected telemetry prior to full SIEM integration.

---

## Security Events Logged

- Authentication failures
- Authentication successes
- Rate limit violations
- Excessive OCR usage
- Authorization failures
- Account creation events

---

## Detection Rules

### Brute Force Detection
Trigger when:
- ≥5 login failures
- From same IP
- Within 10 minutes

### Account Takeover Indicator
Trigger when:
- Multiple failures
- Followed by successful login
- From same IP

### OCR Abuse Detection
Trigger when:
- ≥20 OCR uploads
- Within 5 minutes

---

## SOC Response Workflow

1. Validate alert trigger
2. Correlate related events
3. Review IP reputation
4. Analyze account behavior
5. Escalate if malicious activity confirmed

---

## False Positives

- Users forgetting credentials
- High study activity before exams
- Shared IP environments

---

## Security Value

This lab demonstrates:

- Detection engineering fundamentals
- Structured logging design
- Alert severity classification
- SOC triage thinking
