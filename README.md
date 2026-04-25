# Remote Dev Stack

A composition of Tailscale, Chrome Remote Desktop, macOS Screen Sharing, and tmux that makes a Mac Mini reachable from any device anywhere — including a phone — with persistent shell sessions so an AI coding agent (Claude Code) keeps running between connections.

> *This repo is a public overview. The running code is private.*

---

## What it is

Most "remote access" setups fall down in two places: they require the target machine to have a public address (insecure, clunky), and they drop work when the connection drops. This stack fixes both. Tailscale gives every device a private mesh address; tmux lets Claude Code run uninterrupted on the Mac Mini while a phone or laptop attaches and detaches at will.

## What it does

- **Mesh networking via Tailscale** — no port forwarding, no public exposure; every device has a private stable address
- **Terminal on a phone** — SSH into the Mac Mini, attach to a tmux session running Claude Code, issue commands, detach, come back hours later
- **Desktop sharing via Chrome Remote Desktop** — full GUI when a terminal isn't enough
- **Native macOS Screen Sharing** for other Macs on the mesh
- **Durable agent sessions** — the agent keeps running even when the user is offline

## Software

| Layer | Tech |
|---|---|
| Network mesh | Tailscale |
| Terminal persistence | tmux |
| Remote GUI (cross-platform) | Chrome Remote Desktop |
| Remote GUI (Mac ↔ Mac) | macOS Screen Sharing |
| Agent | Claude Code running inside the tmux session |

## What this demonstrates

- **Practical zero-trust networking** — no exposed ports, no VPN appliance, just a mesh
- **Durable agent sessions** — AI coding work is decoupled from the client device's connection state
- **Cross-platform reach** — same stack works from Mac, PC, iPad, and phone

## Stack

![Tailscale](https://img.shields.io/badge/Tailscale-000000?style=flat&logo=tailscale&logoColor=white)
![tmux](https://img.shields.io/badge/tmux-1BB91F?style=flat&logo=tmux&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-000000?style=flat&logo=apple&logoColor=white)

---

Part of the AIOS portfolio. See the [profile README](https://github.com/mikecutillo) for the full system map.
