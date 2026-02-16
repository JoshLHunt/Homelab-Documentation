# Active Directory Hardening Notes

This document outlines defensive considerations identified while building and testing the AD lab environment.

---

## Kerberos Security Considerations

### Observed Risk
- Weak service account passwords increase Kerberoasting risk
- Lack of pre-authentication allows AS-REP roasting

### Defensive Controls
- Enforce strong service account password policies
- Disable pre-authentication exemptions
- Monitor abnormal TGS requests
- Implement tiered admin model

---

## Credential Hygiene

### Observed Risk
- Password reuse increases lateral movement success
- Overprivileged user accounts widen attack paths

### Defensive Controls
- Least privilege enforcement
- Privileged Access Workstations (PAWs)
- Account tier separation
- Regular credential audits

---

## Network Segmentation

### Observed Risk
- Flat networks simplify attacker movement
- Unrestricted SMB traffic enables relay attacks

### Defensive Controls
- VLAN segmentation
- Firewall enforcement between tiers
- Disable SMBv1
- Enforce SMB signing where appropriate

---

## Logging & Monitoring

### Key Events to Monitor
- Event ID 4769 (Kerberos service ticket requests)
- Event ID 4624 (Logon events)
- Excessive failed authentication attempts

---

## Summary

Understanding attack methodology improves defensive architecture design.

This lab reinforces that offensive security knowledge must translate into measurable defensive improvements.
