# Runbook: Compromised server (the one we hope never to use)

## Immediate actions

1. Isolate the server (firewall rules to block all traffic)

   ```
   sudo ufw default deny incoming
   sudo ufw default deny outgoing
   ```
   
2. Take a snapshot/image (for forensics)
3. Don't shut down yet (preserves memory for analysis)
4. Start documenting everything in an incident doc

## Assessment
1. Check recent commands: `history`
2. Check running processes: `ps auxf`
3. Check network connections: `netstat -tunap`
4. Check scheduled tasks: `crontab -l` for all users
5. Check for new user accounts: `cat /etc/passwd`
6. Check SSH authorized_keys for all users

## Containment
1. Rotate all credentials that server had access to
2. Check logs for lateral movement to other servers
3. Inform customers if data might be affected (legal requirement)

## Recovery
1. Provision fresh server from known-good image
2. Deploy using Ansible playbook (ensures clean state)
3. Restore data from backups (after verifying backups aren't compromised)
4. Update security controls based on how they got in

## Learning
1. Write post-incident review (no blame, just learning)
2. Update defences to prevent recurrence
3. Consider if we need better monitoring
4. Update this runbook
