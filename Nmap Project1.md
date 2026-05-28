# Nmap Network Scanning Project

## Project Overview
This project demonstrates the use of Nmap for performing basic network scanning and host discovery. The purpose of this project is to gain hands-on experience with network reconnaissance techniques and understand how Nmap identifies hosts, ports, and running services.

---

## Project Objective
The main objective of this project is to:

- Learn the basics of network scanning
- Identify local system IP address
- Discover active hosts
- Identify open ports
- Understand service detection
- Gain practical experience with Nmap

---

## Tools Used
- Nmap
- Windows Command Prompt (CMD)
- VS Code
- GitHub

---

# Step 1: Identifying Local IP Address

## Command Used

```bash
ipconfig
```

## Screenshot
![IP Config](<Screenshots/ip config.png>)

## Purpose
The `ipconfig` command was used to identify the local IPv4 address and network configuration details before performing Nmap scans on the local network.

## Findings
- Identified local IPv4 address: `192.168.1.3`
- Detected default gateway: `192.168.1.1`
- Observed subnet mask and wireless network adapter information

## What I Learned
- How to identify local network configuration using `ipconfig`
- Understanding the role of IPv4 address, subnet mask, and default gateway
- Importance of identifying target network details before network scanning

---

# Scan 1: Ping Scan (Host Discovery)

## Command Used

```bash
nmap -sn 192.168.1.0/24
```

## Screenshot

![Ping Scan](<Screenshots/Ping Scan.png>)

## Purpose
This scan was performed to discover active devices available on the local network without scanning ports.

## Findings
- Detected multiple active hosts within the `192.168.1.0/24` network range
- Identified live systems including `192.168.1.1`, `192.168.1.3`, `192.168.1.4`, `192.168.1.5`, `192.168.1.7`, and `192.168.1.10`
- Observed MAC addresses and host response latency information

## What I Learned
- How to perform host discovery using Nmap
- Understanding active hosts and network availability
- Importance of reconnaissance before detailed network scanning
---

# Scan 2: Fast Port Scan

## Command Used

```bash
nmap -F 192.168.1.3
```

## Screenshot

![Fast Port Scan](<Screenshots/Fast Port Scan.png>)

## Purpose
This scan was performed to quickly identify commonly used open ports on the target system without scanning all available ports.

## Findings
- Detected open ports including `135`, `139`, `445`, `3306`, and `8080`
- Identified associated services such as `msrpc`, `netbios-ssn`, `microsoft-ds`, `mysql`, and `http-proxy`
- Observed that 95 TCP ports were closed on the target host

## What I Learned
- How fast port scanning works using Nmap
- Importance of identifying open ports and running services
- Understanding how services communicate through specific ports
---

# Scan 3: Service Version Detection

## Command Used

```bash
nmap -sV 192.168.1.3
```

## Screenshot
![Service Version Detection](<Screenshots/Service Version Detection.png>)


## Purpose
This scan was performed to identify services running on open ports and detect their versions on the target system.

## Findings
- Detected services including `msrpc`, `netbios-ssn`, `mysql`, `http`, and `http-proxy`
- Identified service versions such as `MySQL`, `LabVIEW HTTPD`, and `Embedthis HTTP`
- Observed that the target system was running a Windows operating system

## What I Learned
- How service version detection works using Nmap
- Importance of identifying running services and software versions
- Understanding basic enumeration and service analysis techniques

---

# Scan 4: OS Detection

## Command Used

```bash
nmap -O 192.168.1.3
```

## Screenshot
![OS Detection](<Screenshots/OS Dectection.png>)

## Purpose
This scan was performed to identify the operating system running on the target machine using OS fingerprinting techniques.

## Findings
- Detected the target operating system as `Microsoft Windows 11`
- Identified OS details including `Windows 11 24H2 - 25H2`
- Observed open ports, running services, and network distance information

## What I Learned
- How Nmap performs OS fingerprinting
- Importance of operating system detection in reconnaissance
- Understanding how network and OS information can be gathered from a target system

---

# Scan 5: Aggressive Scan

## Command Used

```bash
nmap -A 192.168.1.3
```

## Screenshot
![Aggressive Scan](<Screenshots/Aggresive Scan.png>)

## Purpose
This scan was performed using the `nmap -A` command to gather detailed information about the target system (`192.168.1.3`). The aggressive scan enabled **OS detection, service version detection, script scanning, and additional network enumeration** to identify running services and system details.

---

## Key Findings
- The target host was active and reachable with very low latency (`0.00077s`), indicating it is likely on the same local network.
- **7 open ports** were identified: `135`, `139`, `445`, `3306`, `3580`, `8080`, and `8090`.
- Windows-related services such as **MSRPC, NetBIOS, and SMB** were detected on ports `135`, `139`, and `445`.
- A **MySQL database service** was found running on port `3306`, but access was restricted (`MySQL unauthorized`).
- HTTP services were detected on ports `3580` and `8080`, including **NI Service Locator** and **Embedthis HTTP server**.
- Nmap identified the target operating system as **Microsoft Windows 11 (24H2 - 25H2)**.
- SMB security analysis showed that **message signing was enabled and required**, improving security against certain attacks.
- The scan reported **0 network hops**, meaning the device is located within the same network.

---

## What I Learned
- How to perform an **Aggressive Scan** using `nmap -A`.
- How to identify **open ports and running services** on a target system.
- How **OS detection and version detection** work in Nmap.
- How to analyze **HTTP services and database services** from scan results.
- Importance of **SMB security configurations** such as message signing.
- How detailed reconnaissance helps in understanding a target system during cybersecurity assessments.

---

## Challenges Faced
Initially, understanding Nmap commands and interpreting scan outputs was challenging. With practice, it became easier to understand scan results and identify different scan purposes.

---

## Key Takeaways
- Learned how to identify local IP address
- Understood host discovery using Nmap
- Learned fast port scanning
- Practiced service version detection
- Learned OS detection and aggressive scanning
- Improved practical cybersecurity skills

---

## Conclusion
This project helped me understand the basics of network scanning using Nmap and improved my practical knowledge of reconnaissance techniques in cybersecurity.