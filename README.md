# Wireshark Lab: Examining HTTP and HTTPS Traffic

A portfolio-ready documentation project based on the lab **“Using Wireshark to Examine HTTP and HTTPS Traffic.”** It guides you through capturing traffic with `tcpdump`, inspecting it in Wireshark, recording observations, and presenting evidence on GitHub.

> **Scope and safety:** Perform captures only in your own lab VM or on networks and systems for which you have explicit authorization. HTTP captures can expose submitted form data. Use only the lab's intended test account and never capture real passwords, session cookies, personal data, or unrelated traffic. Do not commit raw `.pcap` files or credentials to GitHub.

## Learning objectives

- Capture traffic into PCAP files using `tcpdump`.
- Inspect HTTP requests and form fields in Wireshark.
- Inspect HTTPS/TLS traffic and identify encrypted application data.
- Compare what is visible in HTTP and HTTPS captures.
- Document methods, evidence, observations, and limitations in a reproducible portfolio.

## Repository map

```text
.
├── README.md
├── .gitignore
├── .github/
│   └── workflows/
│       └── portfolio-check.yml
├── docs/
│   ├── lab-workflow.md
│   ├── safety-and-scope.md
│   └── findings-template.md
├── screenshots/
│   ├── README.md
│   └── .gitkeep
├── captures/
│   └── README.md
├── reports/
│   ├── README.md
│   └── findings.md
└── notes/
    └── README.md
```

## Quick start

1. Create a new GitHub repository, for example `wireshark-http-https-lab`.
2. Upload or push this folder's contents to that repository.
3. Read [`docs/safety-and-scope.md`](docs/safety-and-scope.md) before capturing traffic.
4. Follow [`docs/lab-workflow.md`](docs/lab-workflow.md) in your CyberOps Workstation VM or an equivalent authorized lab.
5. Save your own screenshots in `screenshots/`, complete `reports/findings.md`, and update the README with your actual results.
6. Review every file before pushing. Keep raw packet captures and sensitive data out of the repository.

## Lab workflow at a glance

| Stage | Action | Evidence to save |
|---|---|---|
| 1 | Identify the lab network interface | Screenshot showing interface names/IPs, with unrelated details redacted |
| 2 | Capture the lab's HTTP session with `tcpdump` | Screenshot of capture command and stopped capture; do not expose sensitive data |
| 3 | Open the capture in Wireshark and filter `http` | Screenshot showing relevant request and decoded form section, using only lab test data |
| 4 | Capture the lab's HTTPS session | Screenshot showing capture command and stopped capture |
| 5 | Filter TLS traffic with `tcp.port == 443` | Screenshot showing TLS/Application Data and encrypted data |
| 6 | Compare and write findings | Completed `reports/findings.md` |

## Key concepts

- **HTTP:** Traffic is not encrypted by HTTP itself; request details may be readable in a packet capture.
- **HTTPS:** HTTP is protected by TLS in transit. A capture can still reveal metadata such as IP addresses, ports, packet sizes, and timing, while application payload is generally encrypted.
- **Important limitation:** HTTPS does not prove that a website is trustworthy. It provides a protected connection to the site identified by the certificate, subject to correct validation and configuration.

## Deliverables checklist

- [ ] Method and environment recorded in `docs/lab-workflow.md` or report notes.
- [ ] Screenshots named and explained in `screenshots/README.md`.
- [ ] HTTP and HTTPS observations recorded in `reports/findings.md`.
- [ ] Reflection questions answered in your own words.
- [ ] No raw PCAPs, passwords, cookies, tokens, or personal information committed.
- [ ] Repository reviewed in GitHub after upload.

## Suggested GitHub portfolio description

> Captured and compared HTTP and HTTPS traffic in an authorized lab using tcpdump and Wireshark. Documented capture commands, display filters, packet-level observations, screenshots, and security implications, with a focus on why HTTP exposes application data and how TLS protects it in transit.

## Source lab

This project follows the supplied lab handout, **“Lab - Using Wireshark to Examine HTTP and HTTPS Traffic”** (Cisco Networking Academy, copyright notice in the supplied handout). This repository is a student documentation scaffold; record your own lab results rather than presenting template text as completed experimental evidence.
