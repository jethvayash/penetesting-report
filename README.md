# 🛡️ PENETRATION TESTING REPORT

### Footprinting, Reconnaissance & Network Scanning Assessment

<p align="center">
  <img src="https://img.shields.io/badge/Project-Penetration%20Testing-111827?style=for-the-badge&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Focus-Reconnaissance%20%26%20Scanning-C00000?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Platform-Kali%20Linux-E87500?style=for-the-badge&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Tool-Zenmap-0070C0?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Week%2002-Cybersecurity-238F89?style=for-the-badge" />
</p>

> **W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**

---

## 📋 Engagement Overview

This report documents the practical penetration-testing activities completed during **Week 2 of the Cybersecurity Internship at NetworkWalks**, with a primary focus on **reconnaissance, footprinting, DNS intelligence, web technology identification, and local network discovery**.

The assessment was performed within an **authorized and controlled scope**, covering the `networkwalks.com` domain for reconnaissance exercises and a personally owned local LAN for network-scanning activities.

The objective was not to exploit systems, but to understand how a security professional can progressively build an accurate picture of a target environment before deeper security testing begins.

| **Assessment Detail**   | **Information**                                            |
| ----------------------- | ---------------------------------------------------------- |
| **Assessment Type**     | Penetration Testing — Footprinting & Network Scanning      |
| **Program**             | Cybersecurity Internship — NetworkWalks                    |
| **Week / Module**       | Week 02 — W2-PM-FINAL                                      |
| **Assessment Scope**    | `networkwalks.com` + Own Local LAN                         |
| **Authorization**       | ✅ Written authorization / owned systems                    |
| **Primary OS**          | Kali Linux                                                 |
| **Additional Platform** | Windows + Zenmap                                           |
| **Phases Completed**    | Reconnaissance, Footprinting, Network Scanning & Discovery |
| **Remaining Phases**    | Exploitation / Validation / Reporting — In Progress        |

---

# ⚠️ 1. Legal, Ethical & Liability Disclaimer

All security activities documented in this report were performed only against systems for which appropriate authorization had been obtained or systems personally owned by the tester.

The techniques, commands, observations, and tools presented here are intended strictly for **cybersecurity education, authorized security assessment, and research**.

Unauthorized scanning, enumeration, exploitation, or access to systems may violate organizational policies and applicable laws. Security testing should therefore always be performed within a clearly defined scope and with explicit permission.

> **Security principle:** Authorization comes before enumeration, and scope must always be respected.

---

# 🎯 2. Assessment Objectives

The assessment was designed to build practical understanding of the early stages of penetration testing.

### Primary objectives

* Perform passive and active footprinting of an authorized domain.
* Collect publicly available domain and DNS information.
* Identify technologies used by the target web application.
* Inspect HTTP response information.
* Identify the presence of web application security controls.
* Enumerate relevant DNS records.
* Identify devices connected to a personally owned local network.
* Record IP and MAC address information.
* Visualize the discovered network topology.
* Document observations, risks, evidence, and recommendations professionally.

The overall methodology followed a simple progression:

```text
Reconnaissance
      ↓
Footprinting
      ↓
Technology & DNS Enumeration
      ↓
Network Discovery
      ↓
Risk Interpretation
      ↓
Security Recommendations
```

---

# 🔎 3. Assessment Scope

### Target 01 — Authorized Web Domain

**Target:** `networkwalks.com`

The domain was assessed during the footprinting and reconnaissance exercise using multiple Kali Linux utilities.

### Target 02 — Personal Local Network

The second assessment was performed against a **personally owned LAN**, using Zenmap for host discovery and network mapping.

No exploitation was performed as part of these two practical modules.

---

# 🧰 4. Tools & Technologies

| **Tool / Platform** | **Primary Purpose**                               |
| ------------------- | ------------------------------------------------- |
| 🐉 **Kali Linux**   | Security testing and reconnaissance environment   |
| 🪟 **Windows**      | Local network identification and Zenmap execution |
| 🔍 **WHOIS**        | Domain registration and name-server information   |
| 🌐 **WhatWeb**      | Web technology fingerprinting                     |
| 📡 **nslookup**     | DNS resolution and IP identification              |
| 📥 **curl -I**      | HTTP response-header inspection                   |
| 🛡️ **Wafw00f**     | Web Application Firewall identification           |
| 🧭 **DNSRecon**     | DNS record enumeration                            |
| 🗺️ **Zenmap**      | Network discovery and visual network mapping      |
| 💻 **Windows CMD**  | Local IP/subnet/MAC information                   |

---

# 🧪 5. Activities Performed

## 5.1 Footprinting & Reconnaissance

The first phase focused on collecting information that could help establish a technical profile of the authorized target.

Six Kali Linux tools were used, with each tool providing a different perspective of the target environment.

### 🔹 WHOIS — Domain Intelligence

WHOIS was used to collect publicly available domain registration information and identify relevant domain infrastructure, including registration information and name servers.

**Security relevance:**
Public registration and infrastructure information can contribute to an organization's external attack-surface profile.

---

### 🔹 WhatWeb — Technology Fingerprinting

WhatWeb was used to identify technologies exposed by the target website.

The observed results identified:

* **WordPress 7.0.4**
* **WP Download Manager 3.3.58**
* Additional web-technology information

**Security relevance:**
Technology and version information can help security teams determine what software should be reviewed against known security advisories and configuration requirements.

---

### 🔹 nslookup — DNS Resolution

`nslookup` was used to resolve the target domain and identify its associated IP address.

**Observed result:**

```text
192.232.216.135
```

**Security relevance:**
DNS information helps establish where a public-facing service is hosted and forms part of the external infrastructure profile.

---

### 🔹 curl — HTTP Header Inspection

The `curl -I` command was used to inspect HTTP response headers returned by the website.

The exercise also exposed the WordPress REST API endpoint:

```text
/wp-json/
```

**Security relevance:**
HTTP headers and exposed application endpoints can provide useful information for technology identification and subsequent authorized security review.

---

### 🔹 Wafw00f — WAF Detection

Wafw00f was used to determine whether a Web Application Firewall was present.

**Observed result:**

```text
ModSecurity (SpiderLabs)
```

**Security relevance:**
Identifying protective technologies helps security professionals understand the target's defensive architecture and informs future authorized testing.

---

### 🔹 DNSRecon — DNS Enumeration

DNSRecon was used to enumerate relevant DNS information.

The results provided information relating to:

* Name servers
* Mail servers
* SPF / TXT records
* Service records
* DNS software information

**Security relevance:**
DNS records can reveal relationships between public-facing systems and services, helping defenders understand their externally visible infrastructure.

---

# 🖥️ 5.2 Network Scanning with Zenmap

The second practical activity focused on discovering hosts within a **personally owned local network**.

The assessment process consisted of:

```text
Identify Local IP
        ↓
Determine LAN/Subnet
        ↓
Configure Zenmap
        ↓
Perform Ping Scan
        ↓
Identify Live Hosts
        ↓
Review IP / MAC Information
        ↓
Generate Network Topology
```

The Windows `ipconfig` command was first used to determine the local network configuration.

Zenmap was then configured to scan the appropriate subnet using **Ping Scan**.

### Example live-host results

```text
10.0.0.1
10.0.0.4
10.0.0.19
10.0.0.5
```

The example assessment also identified corresponding MAC-address information and generated a network topology using Zenmap.

> **Note:** Network addresses and host counts shown above represent the documented example results and should be replaced with actual results when this report is submitted for a different network.

---

# 📊 6. Findings & Risk Assessment

The activities produced several observations that are useful from both an offensive-security and defensive-security perspective.

| **ID**   | **Observation**                    | **Evidence**                                            | **Potential Impact**                             | **Risk**      |
| -------- | ---------------------------------- | ------------------------------------------------------- | ------------------------------------------------ | ------------- |
| **F-01** | Web technology information exposed | WordPress and WP Download Manager identified by WhatWeb | May assist software/version reconnaissance       | 🟠 **Medium** |
| **F-02** | Public server IP identifiable      | DNS resolved domain to `192.232.216.135`                | Helps establish public infrastructure location   | 🟡 **Low**    |
| **F-03** | HTTP technical information exposed | HTTP headers and `/wp-json/` observed                   | May assist application fingerprinting            | 🟡 **Low**    |
| **F-04** | WAF technology identifiable        | ModSecurity identified by Wafw00f                       | Reveals defensive architecture information       | 🟡 **Low**    |
| **F-05** | DNS infrastructure visible         | DNSRecon identified DNS/mail/service records            | Can contribute to broader infrastructure mapping | 🟠 **Medium** |
| **F-06** | Multiple local hosts discoverable  | Four example live hosts identified by Zenmap            | Unknown devices may require verification         | 🟠 **Medium** |

### Risk Classification

```text
🔴 Critical
🟠 Medium
🟡 Low
```

### Important Assessment Note

These findings represent **reconnaissance and discovery observations**, not confirmed exploitable vulnerabilities.

For example, identifying a software version, IP address, DNS record, or WAF does **not automatically indicate a security vulnerability**. Additional authorized validation would be necessary before classifying such observations as confirmed vulnerabilities.

---

# 🛠️ 7. Security Recommendations

### 01 — Minimize Unnecessary Technology Disclosure

Review externally visible web technologies and determine whether unnecessary implementation details can be reduced.

### 02 — Maintain Software & Plugin Updates

Keep CMS platforms, plugins, and related components regularly updated and review them against applicable security advisories.

### 03 — Review HTTP Response Headers

Evaluate exposed response headers and remove unnecessary technical information where appropriate.

### 04 — Audit DNS Records

Regularly review DNS records to confirm that only required services and information are publicly exposed.

### 05 — Maintain WAF Protection

Keep the existing WAF protection properly configured, monitored, and tuned according to the organization's security requirements.

### 06 — Perform Regular Internal Discovery

Conduct authorized internal network discovery to maintain visibility over active devices.

### 07 — Investigate Unknown Devices

Any unidentified or unexpected device discovered on the network should be verified and investigated.

### 08 — Maintain Updated Network Documentation

Keep IP allocations, devices, network segments, and topology documentation current.

### 09 — Enforce Authorized Testing

All reconnaissance and scanning activities should operate under a documented scope, authorization, and defined testing window.

---

# 🧠 8. Key Learning Outcomes

This assessment provided practical exposure to the first stages of a penetration-testing methodology.

### 🔍 Reconnaissance

I learned how publicly available information can be collected systematically before attempting deeper security testing.

### 🌐 DNS Intelligence

I learned how DNS records can reveal information about an organization's externally visible services and infrastructure.

### 🧩 Technology Fingerprinting

I learned how tools such as WhatWeb can identify technologies exposed by a web application.

### 🛡️ Defensive Technology Identification

I learned how Wafw00f can help identify the presence of a Web Application Firewall.

### 🖥️ Network Discovery

I learned how Zenmap can be used to identify active hosts within an authorized local network.

### 🗺️ Network Visualization

Creating a topology helped convert raw discovery results into a more understandable representation of the network.

### 📝 Security Documentation

Most importantly, I learned that professional cybersecurity work is not only about running tools. Findings must be interpreted, documented, evidenced, and translated into practical security recommendations.

---

# 📸 9. Evidence & Documentation

All screenshots collected during the practical exercises should be maintained in the repository's `screenshots/` directory.

Recommended evidence structure:

```text
screenshots/
├── 01_whois.png
├── 02_whatweb.png
├── 03_nslookup.png
├── 04_curl.png
├── 05_wafw00f.png
├── 06_dnsrecon.png
├── 07_zenmap.png
└── 08_zenmap_topology.png
```

### Evidence Coverage

| **Evidence**             | **Activity**                                     |
| ------------------------ | ------------------------------------------------ |
| `01_whois.png`           | Domain registration / infrastructure information |
| `02_whatweb.png`         | Web technology fingerprinting                    |
| `03_nslookup.png`        | DNS resolution                                   |
| `04_curl.png`            | HTTP response-header inspection                  |
| `05_wafw00f.png`         | WAF detection                                    |
| `06_dnsrecon.png`        | DNS enumeration                                  |
| `07_zenmap.png`          | Local network discovery                          |
| `08_zenmap_topology.png` | Network topology                                 |

---

# ✅ 10. Conclusion

During Week 2 of my **Cybersecurity & Ethical Hacking Internship**, I completed practical activities focused on **footprinting, reconnaissance, DNS enumeration, web technology identification, and network discovery**.

The reconnaissance exercise demonstrated how multiple security tools can be combined to build a structured understanding of a target's externally visible infrastructure. WHOIS, WhatWeb, nslookup, curl, Wafw00f, and DNSRecon each provided a different type of intelligence, showing why no single reconnaissance tool provides a complete picture.

The network-scanning exercise using Zenmap provided practical experience in identifying live hosts, reviewing IP and MAC information, and representing discovered devices through network topology.

This assessment reinforced an important penetration-testing principle:

> **A strong security assessment begins with understanding the environment before attempting to exploit it.**

The exercises also highlighted the importance of authorization, evidence collection, accurate risk interpretation, and professional reporting.

Overall, this practical work strengthened my understanding of the **early phases of penetration testing** and established a foundation for more advanced vulnerability assessment and security-testing activities in subsequent exercises.

---

# 🔐 11. Ethical Security Statement

This project was created for **authorized cybersecurity training and educational purposes**.

All testing activities must remain within the approved scope of the target environment. The techniques demonstrated in this report should never be used against systems, networks, applications, or devices without explicit authorization.

**Learn ethically. Test responsibly. Document professionally.**

---

<p align="center">

### 🛡️ CYBERSECURITY • RECONNAISSANCE • NETWORK SECURITY • ETHICAL HACKING

**Week 02 | Penetration Testing Practical Assessment**

</p>
