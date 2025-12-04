# Excessive SSH failures

## What this alert means

Someone (or something) is trying lots of different passwords on SSH.
This is normal internet background noise, but we track it anyway.

## What to do

### Immediate actions (first 5 minutes)
1. Check the source IP in the alert
2. Look up the IP in AbuseIPDB or similar
3. Check if fail2ban has already banned them (it should have)

   sudo fail2ban-client status sshd

### If fail2ban hasn't banned them

```bash
# Manually ban the IP
sudo fail2ban-client set sshd banip 203.0.113.42
```

### If this is a distributed attack (many different IPs)
1. Check if they're trying common usernames
2. Consider temporarily blocking SSH access from specific countries (if pattern is clear)
3. Consider moving SSH to a non-standard port (but tell everyone first)
4. Document the attack pattern for future reference

### If the attack succeeds (someone actually gets in)
1. PANIC
2. Actually, don't panic
3. Follow the [Compromised Server](compromised-server.md) runbook
4. Call Nora immediately (even if it's 3am)

## Follow-up
- Review why the attack succeeded (weak password? compromised key?)
- Rotate any potentially compromised credentials
- Consider adding the source to a permanent blocklist
- Update this runbook if we learned something new
