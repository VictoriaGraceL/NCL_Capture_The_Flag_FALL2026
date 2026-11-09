# Cyber Command — Team Investigation Portfolio

**Viktoriia Lavrenchuk · collaborative CTF work with ChatGPT · November 2026**

A GitHub-ready record of 15 challenge investigations: packet analysis, cryptography, password auditing, logs, binary data, radio decoding, SMB permissions and partially completed tasks. This repository documents the work; it does not claim every answer was accepted by the scoreboard.

## Start here

- [Challenge index and status](docs/INDEX.md)
- [Screenshot-by-screenshot guide](docs/SCREENSHOTS.md) — 19 original captures with explanations and limitations
- [Password-cracking write-up](docs/challenges/password-audit.md)
- [Contributions and evidence policy](docs/CONTRIBUTIONS.md)
- [Original team PDF](reports/Cyber_Command_Team_Handoff.pdf) — historical snapshot; later SMB/firewall updates are in Markdown
- [Validation results](results/VALIDATION.md)

## Repository layout

- `docs/challenges/`: detailed write-ups, answers and reproduction notes.
- `docs/screenshots/`: one annotated explanation per screenshot.
- `screenshots/`: unchanged original screenshots with ordered filenames.
- `evidence/`: supplied challenge datasets; no unrelated personal files.
- `scripts/`: reconstructed offline verifiers/decoders, explicitly labeled by scope.
- `results/`: freshly reproduced outputs and reports.
- `reports/`: original PDF handoff.
- `MANIFEST.sha256`: integrity hashes for packaged files.

## Run offline checks

From the repository root, use Python 3.10+:

```bash
python -m pip install -r requirements.txt
python scripts/verify_password.py
python scripts/verify_merkle.py 5 42d9bf34bffe15cb8c09a9352d16b35f02213bec2f2e35420e5e7553ccb518db
python scripts/decrypt_electron.py
python scripts/decrypt_mailbox.py
python scripts/decode_radio.py
```

Radio decoding also needs the `ffmpeg` executable on PATH. PDF text extraction optionally uses `pdftotext`. These programs read local evidence; they do not connect to challenge servers.

## Use on GitHub

Unzip, inspect the files, and upload the contents of `cyber-command-writeups/` into your chosen repository. Nothing has been published automatically. Start privately if you are still checking whether the event permits publishing its datasets and solutions; this archive includes challenge flags, provided lab credentials, screenshots and original assets. No license is asserted over third-party challenge material.

## What is and is not verified

A hash match or authenticated decryption proves a local result, not scoreboard acceptance. Missing screenshots and transient original scripts are disclosed. Failed commands are documented as failed, and incomplete tasks remain open. Reconstructed tools are not falsely presented as the exact original command history.
