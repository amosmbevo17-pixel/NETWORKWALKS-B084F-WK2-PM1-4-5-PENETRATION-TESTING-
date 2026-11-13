# Footprinting & Network Scanning — Week 2

**Program:** Networkwalks Cybersecurity & Ethical Hacking  
**Batch:** B082F
**Author:** Amos Mbevo  
**Report date:** 13 November 2026  
**Modules covered:** W2-PM1 (Multiple Kali Tools), W2-PM4 (theHarvester), W2-PM5 (Zenmap)

## Project overview

This repository documents the Week 2 practical exercises covering two stages of an authorized penetration-testing workflow:

1. **Footprinting and reconnaissance** against the publicly accessible `networkwalks.com` domain.
2. **Host discovery and network mapping** on the author's own local lab network, `10.0.0.0/24`.

The work demonstrates how publicly available domain and web information can be collected, then how live hosts can be discovered and visualized in a controlled local environment. The detailed report includes the commands used, observations, screenshots, risk discussion, recommendations, and conclusion.

## Main report

The complete 15-page public report has been prepared as the repository's primary document. The sanitized PDF is ready to upload; it is not yet present in the repository.

`PENETRATION_TESTING_NETWORKWALKS_REPORT.pdf`

The public copy masks the MAC address displayed in the Zenmap screenshot on page 10. No technical sections, findings, screenshots, scan details, recommendations, or conclusions are intentionally omitted. The original unmodified report is retained separately by the author.

## Activities and tools

### 1. Footprinting & reconnaissance — W2-PM1

Six Kali Linux tools were used to gather different categories of publicly accessible information:

| Tool | Purpose |
|---|---|
| WHOIS | Review publicly available domain registration details, registrar information, dates, status, and name servers. |
| WhatWeb | Identify web technologies and components; the report records WordPress 7.1.4 and WP Download Manager 3.3.76. |
| Nslookup | Resolve the domain; the report records `192.232.216.135`. |
| cURL (`-I`) | Review HTTP response headers and note the WordPress REST API path `/wp-json/`. |
| Wafw00f | Identify the reported WAF technology, ModSecurity (SpiderLabs). |
| DNSRecon | Enumerate DNS information, including name servers, MX, SPF/TXT, and service-related records. |

### 2. Public information gathering — W2-PM4

**theHarvester** was used independently for passive reconnaissance, focusing on publicly indexed email addresses, employee names, subdomains, hostnames, and associated IP addresses where available.

### 3. Local network discovery — W2-PM5

**Zenmap (Nmap GUI)** was used for host discovery and topology visualization on the author's own local network.

| Item | Recorded configuration |
|---|---|
| Kali Linux IP | `10.0.0.2` |
| Network | `10.0.0.0/24` |
| Subnet mask | `255.255.255.0` |
| Zenmap profile | Ping Scan |
| Hosts reported as discovered | `10.0.0.1` and `10.0.0.2` |

The report includes local network configuration evidence, Zenmap host-discovery output, and a network topology screenshot.

## Risk analysis and recommendations

The report records seven observations and assigns estimated risk levels:

- Exposed web technology information — Medium
- Identifiable server IP address — Low
- Exposed HTTP technical information — Low
- Identifiable WAF technology — Low
- Exposed DNS infrastructure information — Medium
- Public organizational information discoverable — Medium
- Multiple devices discoverable on the local network — Medium

**Important interpretation:** These are reconnaissance and host-discovery observations, not confirmed vulnerabilities. The report explicitly states that no exploitation or vulnerability validation was performed in these modules. Further authorized testing would be required to establish whether any observation represents an exploitable weakness.

The recommendations cover technology and patch management, HTTP header review, DNS security, WAF configuration and monitoring, regular internal discovery, device inventory, network documentation, review of public organizational information, and further testing within an approved scope.

## Repository contents

- `README.md` — project overview, scope, tools, recorded results, and safety notes.
- `PENETRATION_TESTING_NETWORKWALKS_REPORT.pdf` — planned primary document (15 pages; prepared locally, pending binary upload).

## Authorization and responsible use

The report states that activities were performed only on systems and devices for which written permission had been secured or that were owned by the author. The local Zenmap scan was performed against the author's own lab network. This repository is shared for educational and research purposes. Do not use these techniques against systems without explicit authorization.
