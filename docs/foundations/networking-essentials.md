# Networking Essentials

> From packets to platforms: pragmatic networking knowledge.

## OSI Cheat Grid
| Layer | Example | Diagnostic Tool |
|-------|---------|-----------------|
| 7 App | HTTP/gRPC | curl, grpcurl |
| 6 Pres | TLS | openssl s_client |
| 5 Sess | mTLS renegotiation | openssl, envoy stats |
| 4 Trans | TCP/UDP | ss, tcpdump |
| 3 Net | IP routing | ip route, traceroute |
| 2 Data | Ethernet/VLAN | ethtool, arp |
| 1 Phys | NIC / Fiber | ethtool, dmesg |

## Critical Concepts
- Latency vs Throughput vs Jitter
- Head-of-line blocking (HTTP/1.1 vs HTTP/2)
- Connection pooling & ephemeral ports
- TLS session resumption & OCSP stapling
- Anycast vs GeoDNS

## Latency Budget Template
```
Budget(ms): 200 total
- DNS: 20
- TCP + TLS handshake: 40
- Server processing (p95): 60
- Upstream fanout: 40
- Network variance & retries: 40
```

## Tools Workflow
```
# Connection & state table
ss -s
ss -tuna 'sport = :443'

# Packet capture (ring buffer)
sudo tcpdump -nn -i eth0 -w capture.pcap -C 50 -W 5 'port 443'

# TLS cert chain
openssl s_client -connect api.example.com:443 -servername api.example.com </dev/null 2>/dev/null | openssl x509 -noout -dates -issuer -subject
```

## Common Failure Modes
| Symptom | Cause | Validation |
|---------|-------|-----------|
| SYN backlog full | Accept queue saturation | `ss -lnt` | 
| TLS handshake time | Cipher mismatch / latency | `openssl s_time` |
| Intermittent 5xx | Upstream saturation / retries | Correlate upstream metrics |
| Port exhaustion | Short TIME_WAIT + high RPS | `ss -s` + tuning |
| Low throughput | Window scaling / MTU issues | `ip -s link` & pcap |

## Tuning Quick Wins
- Enable BBR where safe
- Right-size `net.core.somaxconn`
- Adjust ephemeral port range for high concurrency
- Enforce TLS1.2+ with modern ciphers

---
**Next:** Git workflow excellence → [Git & Workflow](git-workflow.md)
