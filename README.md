# SOC Analyst Portfolio

Home lab documenting hands-on detection and response work using **Wazuh SIEM**. Covers both manual investigation workflows and automated response pipelines.

## Goal

Demonstrate an end-to-end SOC analyst workflow (attack simulation → detection → investigation → automated or manual remediation → documentation) using an open-source SIEM stack, with each case mapped to MITRE ATT&CK and (where applicable) relevant compliance frameworks.

## Incident Reports

| # | Title | Focus | Key Techniques |
| --- | --- | --- | --- |
| [001](./brute-force%20detection%20wazuh) | RDP Brute-Force Detection | Manual investigation, account lockout policy validation | T1110, T1531 |
| [002](./virus-total-integration) | Automated Malware Detection & Removal | FIM + VirusTotal + Active Response, zero-touch remediation | T1203, T1070.004, T1485 |

## Lab Stack

`Wazuh 4.17` · `Ubuntu Server 24.04 LTS (Manager)` · `Windows 11 (Target Agent)` · `Kali Linux (Attacker)` · `VirtualBox Internal Network`

## Structure

```
soc-wannabe/
├── brute-force detection wazuh/
│   ├── README.md
│   └── images/
└── virus-total-integration/
    ├── README.md
    ├── image/
    └── remove-threat.py
```

## Notes

All lab environments run on an isolated VirtualBox internal network with no external routing. Attack simulations use safe, industry-standard test artifacts (e.g. EICAR) rather than live malware. `remove-threat.py` is Wazuh's official active response script from their documentation, included here as part of a documented, defensive lab setup.
