# Access matrix

Last updated: 4 Dec 2025

## SSH access

| Server   | Nora | Ponder | Moist | Dev Team       | Notes                          |
|----------|------|--------|-------|----------------|--------------------------------|
| app-01   | ✓    | ✓      | ✗     | read-only logs |                                |
| app-02   | ✓    | ✓      | ✗     | read-only logs |                                |
| db-01    | ✓    | ✗      | ✗     | ✗              | Production database, Nora only |
| proxy-01 | ✓    | ✓      | ✗     | ✗              |                                |
| misc-01  | ✓    | ✓      | ✗     | ✗              | Contains monitoring, logs      |

## Cloud provider admin access

| Person | Role         | MFA Enabled | Notes                              |
|--------|--------------|-------------|------------------------------------|
| Nora   | Owner        | ✓           |                                    |
| Ponder | Admin        | ✓           | Can create resources               |
| Moist  | Billing only | ✓           | Can see costs, can't change things |

## Application admin access

| System         | Nora | Ponder | Moist | Dev Team  |
|----------------|------|--------|-------|-----------|
| Production app | ✓    | ✓      | ✗     | ✗         |
| Staging app    | ✓    | ✓      | ✗     | ✓         |
| Database admin | ✓    | ✗      | ✗     | ✗         |
| Monitoring     | ✓    | ✓      | ✓     | read-only |
| Log analysis   | ✓    | ✓      | ✗     | read-only |

## Review schedule

This document is reviewed monthly on the first Monday.

Access is revoked immediately upon staff departure (we've only had one person leave, but better safe than sorry).
