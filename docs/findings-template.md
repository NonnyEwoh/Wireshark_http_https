# Findings template

Copy this structure into `reports/findings.md` and replace prompts with your own observed results.

## HTTP capture

- Capture filename (kept locally, not committed):
- Interface used:
- Wireshark display filter:
- Packet/request inspected:
- Which request fields were visible?
- What did the decoded form section show? Describe without including real secrets.
- Screenshot evidence:

## HTTPS capture

- Capture filename (kept locally, not committed):
- Interface used:
- Wireshark display filter:
- Packet type inspected:
- What protocol/record information was visible?
- Was the application payload readable? What did Wireshark show?
- Which metadata remained visible?
- Screenshot evidence:

## Comparison

| Topic | HTTP observation | HTTPS/TLS observation |
|---|---|---|
| Application content | Fill in from your capture | Fill in from your capture |
| Encryption | Fill in from your capture | Fill in from your capture |
| Metadata visible | Fill in from your capture | Fill in from your capture |

## Reflection questions

1. What are the advantages of using HTTPS instead of HTTP?
   - Answer in your own words, based on the lab.

2. Are all websites that use HTTPS considered trustworthy?
   - Answer in your own words, based on the lab.

## Conclusion

Summarize what the packet-level evidence taught you about cleartext HTTP, TLS encryption, and the limits of using HTTPS as a trust signal.

## Limitations

Record anything that affected the experiment, such as different interface names, website changes, TLS version differences, or a capture that did not contain the expected packets.
