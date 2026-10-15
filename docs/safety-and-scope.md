# Safety, authorization, and scope

## Authorized environment only

This portfolio exercise is intended for a dedicated CyberOps Workstation VM or another lab environment you own or are explicitly authorized to test. Do not capture traffic on public, workplace, school, or shared networks without written authorization and a defined scope.

## Sensitive data handling

Packet captures can contain much more than the target protocol, including credentials, session cookies, authentication tokens, personal information, DNS queries, and unrelated application traffic.

- Use test accounts and non-sensitive values only.
- Do not use real passwords in demonstrations.
- Do not upload `.pcap`, `.pcapng`, or `.cap` files to a public repository.
- Do not put credentials, cookies, tokens, or personal data in screenshots, Markdown, commit messages, or issue reports.
- Redact sensitive details before adding screenshots.
- If sensitive information was captured accidentally, stop, secure or delete the capture according to your lab rules, and notify the responsible administrator/instructor if required.

## Safe publication review

Before each push:
1. Inspect the staged file list with `git status`.
2. Review screenshots at full size.
3. Search the text files for passwords, tokens, and private identifiers.
4. Confirm that no raw packet captures are staged.
5. Publish only the minimum evidence needed to demonstrate the learning objective.

## Technical caveat

HTTPS protects application content in transit when TLS is correctly negotiated and validated. It does not certify that the website itself is benign, and some metadata may remain visible. Follow applicable lab rules and organizational policies.
