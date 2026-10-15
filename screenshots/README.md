# Screenshot evidence

Store **redacted screenshots only** in this folder. Do not commit raw packet captures.

## Recommended evidence and filenames

1. `01-interface-identification.png` — terminal output showing the selected interface; redact unrelated/private details.
2. `02-http-capture-running.png` — `tcpdump` capture command and confirmation that capture started.
3. `03-http-wireshark-filter.png` — Wireshark with the `http` display filter and relevant test request selected.
4. `04-http-form-fields.png` — decoded HTTP form section, with all sensitive values obscured.
5. `05-https-capture-running.png` — HTTPS capture command and confirmation that capture started.
6. `06-https-tls-filter.png` — Wireshark with `tcp.port == 443` and a TLS Application Data packet selected.
7. `07-https-encrypted-data.png` — protocol tree showing encrypted application data, with private metadata redacted.

Only include screenshots that you actually captured. Do not use example images as if they were your own evidence.

## Evidence index

After adding screenshots, update this table.

| Screenshot | What it demonstrates |
|---|---|
| `01-interface-identification.png` | Replace with your actual observation |
| `02-http-capture-running.png` | Replace with your actual observation |
| `03-http-wireshark-filter.png` | Replace with your actual observation |
| `04-http-form-fields.png` | Replace with your actual observation |
| `05-https-capture-running.png` | Replace with your actual observation |
| `06-https-tls-filter.png` | Replace with your actual observation |
| `07-https-encrypted-data.png` | Replace with your actual observation |
