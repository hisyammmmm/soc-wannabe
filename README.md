# SOC Analyst Portfolio

Home lab documenting hands-on detection and response work using **Wazuh SIEM**. Covers both manual investigation workflows and automated response pipelines.

## Goal

Demonstrate an end-to-end SOC analyst workflow (attack simulation → detection → investigation → automated or manual remediation → documentation) using an open-source SIEM stack, with each case mapped to MITRE ATT&CK and (where applicable) relevant compliance frameworks.

## Incident Reports

| # | Title | Focus | Key Techniques |
| --- | --- | --- | --- |
| [001](./brute-force%20detection%20wazuh) | RDP Brute-Force Detection | Manual investigation, account lockout policy validation | T1110, T1531 |
| [002](./virus-total-integration) | Automated Malware Detection & Removal | FIM + VirusTotal + Active Response, zero-touch remediation | T1203, T1070.004, T1485 |
| [003](./Wazuh%20Integration%20for%20Port%20Scan%20Detection%20with%20Suricata%20NIDS) | Port Scan Detection with Suricata NIDS | Suricata NIDS on Wazuh Manager, custom rule for SYN scan detection | T1046 |

## Research / ML

| Project | Focus | Stack |
| --- | --- | --- |
| [bufferbloat-detection-cnn-1d](./bufferbloat-detection-cnn-1d) | Detect bufferbloat from PCAP traffic — EVA flow/flight segmentation + physical per-packet feature extraction → 1D CNN, aggregated by majority voting (thesis project) | `Python 3.10` · `TensorFlow` · `scapy` · `Streamlit` |

## Lab Stack

`Wazuh 4.17` · `Ubuntu Server 24.04 LTS (Manager)` · `Windows 11 (Target Agent)` · `Kali Linux (Attacker)` · `VirtualBox Internal Network`

## Structure

```
soc-wannabe/
├── brute-force detection wazuh/
│   ├── README.md
│   └── images/
├── virus-total-integration/
│   ├── README.md
│   ├── image/
│   └── remove-threat.py
├── Wazuh Integration for Port Scan Detection with Suricata NIDS/
│   ├── README.md
│   └── images/
└── bufferbloat-detection-cnn-1d/   # submodule — 1D CNN bufferbloat detection
```

## Notes

`bufferbloat-detection-cnn-1d` is a git submodule — clone with `git clone --recursive` or run `git submodule update --init` after cloning.

All lab environments run on an isolated VirtualBox internal network with no external routing. Attack simulations use safe, industry-standard test artifacts (e.g. EICAR) rather than live malware. `remove-threat.py` is Wazuh's official active response script from their documentation, included here as part of a documented, defensive lab setup.
