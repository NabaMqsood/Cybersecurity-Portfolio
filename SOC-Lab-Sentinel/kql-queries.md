# KQL Queries – Brute Force Detection

## Failed Login Detection

SecurityEvent
| where EventID == 4625
| summarize FailedAttempts = count() by Account, IPAddress, bin(TimeGenerated, 5m)
| where FailedAttempts > 5

## Explanation
- EventID 4625 = Failed login attempt
- Groups by user and IP address
- Detects abnormal login behavior