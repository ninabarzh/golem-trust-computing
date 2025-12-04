# Runbook: Suspicious outbound connection

## What to do

1. Identify which server and which process
2. Check if this is expected (new integration? API call?)
3. If unexpected, check the process:

   ```
   ps aux | grep [process-id]
   lsof -p [process-id]  # See what files it has open
   ```
   
4. If the process is suspicious:
   - Kill it: `sudo kill -9 [process-id]`
   - Check for persistence: `sudo find /etc -name "*[suspicious-name]*"`
   - Follow the [Compromised Server](compromised-server.md) runbook
