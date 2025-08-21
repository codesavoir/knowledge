# Linux Basics

> Practical, operations-focused Linux knowledge for DevOps engineers.

## Process Mastery
- `ps -eo pid,ppid,comm,%cpu,%mem --sort=-%cpu | head`
- Signals: `kill -TERM`, escalate to `kill -KILL`
- Investigate hung process: `strace -p <pid>`
- Cgroups on modern distros control resource limits.

## Filesystem & Storage
- Identify disk usage: `df -h`, `du -sh * | sort -h`
- Inodes exhaustion: `df -i`
- Track file growth: `sudo lsof | grep deleted`
- Extended attributes & ACLs: `getfattr`, `getfacl`

## Networking Essentials
```
ss -tuna | grep :443
sudo tcpdump -nn -i eth0 port 443 -c 50
curl -w "DNS:%{time_namelookup} Connect:%{time_connect} TTFB:%{time_starttransfer}\n" -o /dev/null -s https://example.com
```

## Performance Quick Triage
| Symptom | Toolchain | Action |
|---------|-----------|--------|
| High CPU | `top`, `pidstat`, `perf top` | Identify hot threads |
| IO Wait | `iostat -xz`, `iotop` | Check storage latency |
| Memory Pressure | `free -m`, `vmstat 1`, `sar -r` | Tune swappiness |
| Network Latency | `mtr`, `ss`, `tcpdump` | Path vs service issue |

## Files & Text
- Fast search: `rg pattern`, fallback `grep -R "pattern" .`
- Stream editing: `sed -E 's/foo/bar/g'`
- Column extraction: `awk -F',' '{print $2,$5}' file.csv`

## Users & Permissions
- Principle of least privilege
- `sudoedit` over editing config directly
- Audit recent privilege escalation: `grep COMMAND /var/log/auth.log`

## Systemd Essentials
```
systemctl status myservice
journalctl -u myservice -n 200 -f
systemd-analyze blame
```

## Secure Defaults
- Disable root SSH login, use MFA + short-lived certs
- Patch cadence automation (e.g., unattended-upgrades)
- File integrity monitoring (AIDE / Tripwire)
- Kernel hardening (sysctl, AppArmor/SELinux enforcing)

## Troubleshooting Flow
1. Define blast radius
2. Reproduce & timestamp
3. Correlate metrics ↔ logs ↔ traces
4. Form hypothesis, test quickly
5. Document in runbook / postmortem

---
**Next:** Networking essentials deep dive → [Networking](networking-essentials.md)
