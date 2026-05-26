# one-modbus

A production-grade Modbus RTU data acquisition gateway for Windows. Runs as a single `.exe` — read from serial devices, serve via HTTP API, store to SQLite, push alerts to WeChat/Email.

Traditional industrial data acquisition requires three separate systems: a data collector, a web visualization platform, and custom development for alerts and reports. **This single .exe replaces all three layers.**

📥 **Download**: [GitHub Releases](https://github.com/dingjiazhi/one-modbus/releases) | [Gitee (China fast)](https://gitee.com/dingjiazhi/one-modbus/releases)

---

## Quick Start

1. Download `modbusrtu_broker.exe`
2. Place `项目变量信息.xlsx` (project variable config) in the same directory — **auto-generates a template if missing**
3. Double-click the .exe, open browser to **http://127.0.0.1:53046/统计**

> See [docs/quick-start.md](docs/quick-start.md) for detailed setup.

---

## Features

| Feature | Description |
|---------|-------------|
| **Multi-port concurrent collection** | Each serial port runs independently in its own goroutine |
| **Batch read optimization** | Multiple variables on the same device packed into one Modbus request |
| **Zero-code configuration** | Fill in an Excel spreadsheet, double-click, done |
| **REST API** | Read any variable value via HTTP |
| **SQLite time-series storage** | Auto logging with web-based chart query |
| **WeChat alerts** | Push to WeChat Work group robot |
| **Email reports** | Scheduled reports + instant alert emails |
| **Remote upgrade** | Upload new .exe via browser, auto-replace and restart |

---

## Remote Data Acquisition (Internet + DTU)

Pair with a **¥99 DTU (serial-to-TCP converter)** and virtual COM software:

```
Site A: 254 meters → RS-485 → DTU(¥99) → Internet →  Virtual COM  →  one-modbus gateway
Site B:  PLCs      → RS-485 → DTU(¥99) → Internet →  (TCP-to-COM)    (real-time polling)
```

---

## Compatibility

- **OS**: Windows 7/10/11/Server (COM port required)
- **Protocol**: Modbus RTU (RS-232/RS-485), function codes 1/2/3/4
- **Devices**: PLCs, smart meters, sensors, VFDs, temperature controllers

---

## Architecture

![Architecture](docs/architecture-en.svg)

---

## License

GNU Affero General Public License v3.0 (AGPL-3.0)
