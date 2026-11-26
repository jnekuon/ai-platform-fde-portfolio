# Day 4: SELinux Enforcement, System Logs & `systemd` Troubleshooting

## Objective
Configure permanent SELinux file contexts (`semanage fcontext` + `restorecon`), build and manage a custom `systemd` background service (`fde-ai-worker.service`), and verify runtime logs via `journalctl`.

## Key Commands & Verification
- Verified SELinux `Enforcing` state (`getenforce`, `sestatus`).
- Applied permanent `bin_t` label to `/opt/fde-ai-worker` (`semanage fcontext`, `restorecon -Rv`).
- Created `/etc/systemd/system/fde-ai-worker.service` with automatic restart policy (`Restart=always`).
- Validated active service state and logs via `systemctl status` and `journalctl -u fde-ai-worker`.
