# SPL Queries

index=security_logs action=failed_login
| stats count by user, src_ip
| where count > 5

## Explanation
- Filters failed login events
- Counts attempts per user and IP
- Detects brute-force behavior