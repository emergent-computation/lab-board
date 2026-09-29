# lab-board — Emergent Computation lab members board · 课题组成员看板

This repository only **hosts** the lab's members-only idea board on GitHub Pages.
The page is a single encrypted file (AES-256-GCM, key from a shared passphrase via
PBKDF2-SHA256); without the passphrase it reveals nothing beyond its approximate size.
本仓库仅用于托管课题组成员看板：页面整体加密，需口令解锁。

- **Source:** viewer and build tool live in the private `lab-tools` repo
  (`labtools/ideas/viewer/`, `labtools/ideas/board.py`); card data lives in the private `lab-hub`.
- **Deploys:** the lab's home server uploads `board.html` to the release `board-latest` and
  dispatches `deploy-board.yml` with the file's sha256; the workflow verifies the hash and
  deploys it with the official Pages actions (SHA-pinned). No plaintext, no secrets here.
- **Passphrase:** shared with members out of band by the PI; never commit it, never paste it
  into issues. Rotation (`labtools ideas board rotate`) protects future snapshots only.
- **Settings (PI):** Pages source = GitHub Actions; environment `github-pages` restricted to
  `main`; org members may not create other Pages sites (all org Pages share one origin).
- **Do not** add other content, scripts or third-party actions to this repository.

Questions / 问题：open an issue in `lab-hub` (members) or contact the PI.
