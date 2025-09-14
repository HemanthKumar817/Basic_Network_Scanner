# Network Scanner

A simple, command-line tool for discovering and analyzing hosts on a network. It supports ICMP (ping), TCP port scanning, and ARP discovery so network administrators and security professionals can quickly check host availability, open ports, and devices on a local subnet.

---

## Key Features

* **ICMP (Ping) Scan** — Check whether hosts respond to ping.
* **TCP Port Scan** — Probe TCP ports to find open services.
* **ARP Network Discovery** — Find devices on the local LAN using ARP.
* **Flexible Scan Types & Timeouts** — Choose which scan(s) to run and adjust timeouts.
* **Port Ranges & Lists** — Scan individual ports, lists (e.g. `80,443`), or ranges (e.g. `1-1024`).
* **Detailed Output** — Human-readable results with helpful details for each host.

---

## Requirements

* Python 3.6+
* [Scapy](https://scapy.net/) (2.5.0+)
* Root / Administrator privileges for low-level packet operations

Install required packages with:

```bash
pip install -r requirements.txt
```

---

## Quick Start

1. Clone the repository:

```bash
git clone https://github.com/yourusername/network-scanner.git
cd network-scanner
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run a basic scan:

```bash
python src/main.py <target> [options]
```

### Examples

* Scan a single host using all scan types (default):

```bash
python src/main.py 192.168.1.1
```

* Run only an ICMP ping scan:

```bash
python src/main.py 192.168.1.1 -t icmp
```

* Scan specific ports (comma-separated):

```bash
python src/main.py 192.168.1.1 -p 80,443,8080
```

* Scan a range of ports:

```bash
python src/main.py 192.168.1.1 -p 1-1000
```

* Discover devices on a subnet using ARP:

```bash
python src/main.py 192.168.1.0/24 -t arp
```

---

## Command Line Options

* `target` — IP address or network (required)
* `-t, --type` — Scan type: `all`, `icmp`, `tcp`, `arp` (default: `all`)
* `-p, --ports` — Ports to scan (e.g., `80,443` or `1-1000`)
* `-T, --timeout` — Timeout (seconds) for individual probes (default: `2`)

---

## Project Structure

```
network-scanner/
├── src/
│   ├── main.py         # CLI entry point
│   └── scanner.py      # Scanning logic
├── tests/              # Unit / integration tests
├── docs/               # Documentation and diagrams
├── assets/             # Images (put hero.png here)
├── requirements.txt    # Python dependencies
└── README.md           # You are here
```

---

## Security & Legal

This tool performs active network scanning. Follow these rules:

* **Only scan networks and hosts you own or have explicit permission to test.**
* Be aware that scanning can trigger IDS/IPS alerts or violate policies.
* Elevated privileges are required; run responsibly.

---

## Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/my-scan`)
3. Make changes and commit (`git commit -m "Add X"`)
4. Push and open a Pull Request

---

## License

This project is released under the MIT License. See the `LICENSE` file for details.

---
