# Overload

A Python-based network stress testing tool featuring Layer 2, Layer 4, and Layer 7 attack methods for authorized security testing.

> [!WARNING]
> This project has been archived and is no longer actively maintained. While the source code remains available, no new features, bug fixes, or updates are planned.
>
> This project no longer reflects the current goals and interests behind its development, so future development has been discontinued.

<p align="center">
  <img src="img/preview.gif" alt="Overload Preview">
</p>

---

## Features

* Layer 7 attacks: HTTP, HTTP Proxy, Slowloris, and Slowloris Proxy.
* Layer 4 SYN Flood support on POSIX systems.
* Layer 2 ARP Spoof and Disconnect attacks.
* Cross-platform support for Windows, Linux, and Termux.
* Automatic retrieval of public proxies for proxy-enabled methods.
* Interactive terminal interface.

---

## Requirements

* Python 3.10 or newer.
* `make` (recommended) or Poetry.

> [!TIP]
> Using `make` automatically creates the virtual environment, installs the required dependencies, and simplifies the setup process.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/goncalopolido/overload
```

Navigate to the project directory:

```bash
cd overload
```

If `make` is available:

```bash
make setup
make run
```

Otherwise:

```bash
curl -sSL https://install.python-poetry.org | python3
poetry install --without dev
poetry run python3 overload.py
```

> [!IMPORTANT]
> On Windows, ensure Python is added to your `PATH` during installation. Otherwise, the commands above will not work.

---

## Platform Support

| Platform | Supported |
|:---------|:---------:|
| Windows | Yes |
| Linux | Yes |
| Termux | Yes |

> [!NOTE]
> Layer 2 and Layer 4 attack methods require a POSIX-compatible operating system such as Linux.

---

## Attack Methods

### Layer 7

* **HTTP**: Sends a large number of HTTP GET requests to exhaust the target.
* **HTTP Proxy**: HTTP attack performed through public proxies.
* **Slowloris**: Opens and maintains slow HTTP connections to exhaust the server's available connection pool.
* **Slowloris Proxy**: Slowloris attack performed through public proxies.

### Layer 4

* **SYN Flood**: Exploits the TCP three-way handshake by creating large numbers of half-open connections.

### Layer 2

* **ARP Spoof**: Performs ARP poisoning to position the attacker between two hosts on the local network.
* **Disconnect**: Temporarily prevents a selected device from accessing the local network.

> [!WARNING]
> Proxy-enabled methods rely on public proxies retrieved through ProxyScrape. Their availability, speed, reliability, and anonymity cannot be guaranteed.

---

## Disclaimer

> [!CAUTION]
> This project is intended only for testing systems that you own or are explicitly authorized to assess. Do **not** use it against third-party systems.

The tool performs **DoS** attacks, not **DDoS** attacks. Its effectiveness depends on the target's infrastructure and security mechanisms. Modern protections such as DDoS mitigation services, load balancers, SYN Cookies, and similar technologies may significantly reduce or completely prevent the effectiveness of some attack methods.

The authors assume no responsibility for misuse of this software or for any consequences resulting from its use.
