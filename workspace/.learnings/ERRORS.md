
## [ERR-20260312-001] browser_executable_path_mismatch

**Logged**: 2026-03-12T10:16:18Z
**Priority**: medium
**Status**: resolved
**Area**: config

### Summary
OpenClaw browser.executablePath pointed to chrome-linux64 on arm64 host, but installed Playwright Chromium lived under chrome-linux

### Error
```
Error: browser.executablePath not found: /home/node/.cache/ms-playwright/chromium-1208/chrome-linux64/chrome
```

### Context
- Browser tool failed to start built-in browser
- Actual binary existed at /home/node/.cache/ms-playwright/chromium-1208/chrome-linux/chrome
- Fixed main config and backup config files, then refreshed hash baselines

### Suggested Fix
Prefer auto-detection or validate executablePath against the real Playwright install path before saving config

### Metadata
- Reproducible: yes
- Related Files: /home/node/.openclaw/openclaw.json, /home/node/.openclaw/.config-baseline.sha256, /home/node/.openclaw/security-baselines/skill-mcp-baseline.sha256

### Resolution
- **Resolved**: 2026-03-12T10:16:18Z
- **Commit/PR**: n/a
- **Notes**: Updated browser.executablePath to /home/node/.cache/ms-playwright/chromium-1208/chrome-linux/chrome and verified browser tool launches.

---
