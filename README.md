# Smart Home: Local-First Smart Home Stack

A privacy-focused, "Google-free" home automation setup utilizing **Home Assistant** and **Cloudflare Tunnels**. This repository manages the configuration for a local home server to control LSC/Tuya smart devices via Local AES keys, bypassing the public cloud for daily use.

## 🏗 Architecture
This setup uses a "Split-Brain" networking model:
- **Local Control:** A wall-mounted dashboard (Raspberry Pi/Old Tablet) communicates directly with the server via LAN.
- **Remote Access:** Mobile devices connect via an encrypted Cloudflare Tunnel (no open ports required).
- **Device Communication:** Uses the `LocalTuya` protocol to talk to Wi-Fi lights over the local network using extracted AES keys.

## 🛠 Tech Stack
- **Core:** [Home Assistant Container](https://www.home-assistant.io/installation/docker/)
- **Gateway:** [Cloudflare Tunnel](https://www.cloudflare.com/products/tunnel/)
- **Automation:** Python/YAML
- **Frontend:** Lit (Web Components)

## 🚀 Quick Start (Development/Testing)

### 1. Prerequisites
- Docker & Docker Compose installed.
- A Cloudflare account and a registered domain (for remote access).
- Smart Life App (for initial device pairing).

### 2. Environment Setup
Create a `.env` file in the root directory (do **not** commit this to Git):
```bash
CF_TUNNEL_TOKEN=your_cloudflare_token_here
```
