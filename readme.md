<h1 align="center">🔎 Nmap Cheatsheet & Notes</h1>
<p align="center">My personal notes while learning network scanning & enumeration with Nmap 🛰️</p>

---

## 📌 Scan Types

| Command       | Description                 |
|---------------|-----------------------------|
| `-sS`         | 🔍 SYN Scan (Stealthy)       |
| `-sU`         | 📡 UDP Scan                  |
| `-sV`         | 🧪 Detect service versions   |
| `-O`          | 🧠 Detect OS info            |
| `-A`          | ⚡ Aggressive scan (OS, version, traceroute, scripts) |

---

## 🔊 Verbosity Levels

| Command  | Description               |
|----------|---------------------------|
| `-v`     | Verbose output            |
| `-vv`    | Extra verbose             |
| `-V`     | Nmap version (not verbosity) |

---

## 🕒 Timing Templates

| Option | Timing Level |
|--------|---------------|
| `-T0`  | 🐢 Paranoid (very slow & stealthy) |
| `-T1`  | 🐌 Polite       |
| `-T2`  | 🚶 Normal       |
| `-T3`  | 🏃 Aggressive   |
| `-T4`  | 🚀 Fast         |
| `-T5`  | ⚠️ Insane (very noisy) |

> ⚠️ High timing templates are faster but much noisier!

---

## 🗂️ Output Options

| Command          | Output Type       |
|------------------|------------------|
| `-oN output.txt` | 📝 Normal format |
| `-oG output.gnmap` | 🔍 Greppable format |
| `-oA scanname`   | 📦 All formats (.nmap, .xml, .gnmap) |

---

## 🎯 Port Scanning

- `-p <port>` → Scan specific ports (e.g. `-p 22`, `-p 21,22,80`)
- `-p 1-1000` → Scan port range
- `-p-` → Scan **all** 65535 ports

---

## 🧬 NSE Scripting Engine

### ✅ Basic Usage

- Run script: `--script=<script-name>`
- Run multiple: `--script=script1,script2`
- Run vuln scan: `--script=vuln`

### 📚 NSE Categories:

| Type       | 🔎 Description                          |
|------------|------------------------------------------|
| `safe`     | Doesn’t affect target                  |
| `intrusive`| Might cause disruption                 |
| `vuln`     | Looks for vulnerabilities              |
| `exploit`  | Tries to exploit                       |
| `auth`     | Attempts to bypass login/auth          |
| `brute`    | Brute-force credentials                |
| `discovery`| Network/service info gathering         |

📖 **More scripts**: [nmap.org/book/nse-usage.html](https://nmap.org/book/nse-usage.html)  
💡 NSE Scripts are written in **Lua** (same scripting as Roblox!)

---

## 🧰 Script Discovery

```bash
cd /usr/share/nmap/scripts/
grep "smb" /usr/share/nmap/scripts/script.db
