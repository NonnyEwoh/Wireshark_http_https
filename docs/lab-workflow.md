# Lab workflow: HTTP vs HTTPS in Wireshark

## 1. Environment and preparation

The supplied lab specifies a CyberOps Workstation VM and an internet connection. Use the approved lab environment and document any differences in `reports/findings.md`.

Before starting:
- Confirm you have permission to generate and capture the traffic.
- Use only a lab account and non-sensitive test data.
- Ensure the VM clock is correct if the lab browser reports certificate/date errors.
- Create a folder for screenshots and note the date, VM/OS, Wireshark version, and tcpdump version.

## 2. Identify the interface

In a terminal, run:

```bash
ip address
```

Record the interface used by the VM and its address. The original handout uses `enp0s3` as an example; your interface may be different. Use the interface actually present in your environment.

## 3. Capture HTTP traffic

Start a capture in the lab VM, substituting the correct interface if needed:

```bash
sudo tcpdump -i enp0s3 -s 0 -w httpdump.pcap
```

Generate only the lab's intended HTTP test traffic in the browser. Stop the capture with `Ctrl+C`. The capture is written to the current working directory; note its location. Open it in Wireshark.

In Wireshark, apply this display filter:

```text
http
```

Find the relevant HTTP request, then inspect the decoded form fields if present. Record what is visible without copying any real or sensitive credentials into screenshots, notes, or GitHub. The supplied lab uses a demonstration login; do not substitute a real password.

## 4. Capture HTTPS traffic

Start a second capture:

```bash
sudo tcpdump -i enp0s3 -s 0 -w httpsdump.pcap
```

Generate the intended HTTPS browsing activity in the lab browser and stop the capture with `Ctrl+C`. Open the file in Wireshark.

Use the lab's display filter:

```text
tcp.port == 443
```

Select a TLS Application Data packet and inspect the protocol tree. Record what is visible and whether the application payload is readable. Depending on the TLS version and Wireshark version, field labels and the protocol tree may differ from screenshots in the handout.

## 5. Compare and interpret

Use your observations to explain:
- Which application-layer details were readable in the HTTP request?
- What protocol information appears for the HTTPS/TLS packets?
- Whether the encrypted application payload was readable in the capture.
- What metadata may remain visible even when application content is encrypted.
- Why HTTPS improves confidentiality and integrity in transit but does not guarantee that a website is honest or safe.

## 6. Save evidence safely

Use the screenshot naming convention in [`../screenshots/README.md`](../screenshots/README.md). Crop or redact IPs, usernames, browser tabs, cookies, tokens, and unrelated traffic where appropriate.

**Do not commit** `httpdump.pcap`, `httpsdump.pcap`, or other raw packet captures. PCAP files may include credentials, cookies, personal data, and traffic from unrelated applications. If an instructor requires a capture file, use the approved private submission method and review it first.

## 7. Finish and document

- Complete [`../reports/findings.md`](../reports/findings.md) using your actual observations.
- Add screenshot captions and links in [`../screenshots/README.md`](../screenshots/README.md).
- Record unexpected behavior and limitations in `notes/`.
- Commit the documentation and screenshots only after a privacy review.
