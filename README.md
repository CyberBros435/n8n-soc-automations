# n8n SOC Automations

Small automation workflows built in n8n for SOC/security tasks — no heavy coding, drag-and-drop nodes with API integrations.

## 1. IP Reputation Checker
**File:** `IP_Reputation_Checker.json`

Checks any IP against AbuseIPDB and flags it Malicious or Clean.

**Flow:** Manual Trigger → Set IP → HTTP Request (AbuseIPDB API) → IF (score > 50) → Alert / Clean

**Tools:** n8n, AbuseIPDB API

**Sample output:**
- Clean IP → `✅ Clean - Score: 0`
- Malicious IP (Tor exit node) → `⚠️ MALICIOUS - Score: 100`

**How to use:**
1. Import JSON into n8n
2. Add your AbuseIPDB API key in HTTP Request node headers
3. Set target IP in "Set Target IP" node
4. Execute workflow
