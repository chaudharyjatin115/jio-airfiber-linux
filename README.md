# Jio AirFiber Linux

> Reverse engineering the JioHome Android application to build a native Linux client for Jio AirFiber.

This project is an attempt to understand how the JioHome Android app communicates with Jio AirFiber devices and to implement an open-source Linux alternative. The repository contains research notes, protocol documentation, helper scripts, and the source code for the client as development progresses.

## Current Status

🚧 Early research.

## Goals

* Reverse engineer the JioHome APK
* Document the communication protocol
* Understand authentication and request flow
* Build a native CLI (`jioctl`)
* Develop a Linux desktop application in the future

## Repository Layout

```text
apk/
├── original/
├── patched/
└── decompiled/

captures/
├── http/
├── mitm/
└── pcap/

docs/
├── notes/
└── protocol/

frida/
ghidra/
scripts/
src/
tests/
```

## Requirements

* Arch Linux
* Android Studio
* Java (JDK)
* Python 3
* Git

Android Studio, JDK and Apktool were already installed when this project was started.

## Installing the Toolchain

### Reverse engineering tools

```bash
sudo pacman -S android-tools
sudo pacman -S jadx
sudo pacman -S ghidra
sudo pacman -S mitmproxy
sudo pacman -S wireshark-qt
sudo pacman -S tshark
sudo pacman -S tcpdump
sudo pacman -S nmap
sudo pacman -S jq ripgrep fd bat fzf tree hexedit
sudo pacman -S clang cmake ninja gcc make
sudo pacman -S rust
sudo pacman -S go
```

### Optional (AUR)

```bash
yay -S burpsuite
yay -S radare2
```

### Allow Wireshark to capture packets

```bash
sudo gpasswd -a $USER wireshark
```

Log out and back in after running the command.

## Python Environment

Python packages should be installed inside a virtual environment.

Create one inside the project:

```bash
python -m venv .venv
```

Activate it:

```bash
source .venv/bin/activate
```

Upgrade pip:

```bash
python -m pip install --upgrade pip
```

Install the required packages:

```bash
python -m pip install \
frida-tools \
objection \
requests \
aiohttp \
websocket-client \
protobuf \
grpcio \
grpcio-tools \
cryptography \
pycryptodome \
rich \
typer
```

Whenever you work on the project, activate the environment first:

```bash
source .venv/bin/activate
```

## Planned Features

* APK analysis
* Protocol documentation
* Authentication implementation
* Client discovery
* Device information
* Connected client list
* Wi-Fi configuration
* Router reboot
* Firewall configuration
* Desktop interface

## Legal

This repository contains original code and documentation only.

No proprietary APKs, source code, or assets are included. If you want to reproduce the research, obtain the JioHome APK yourself and place it in:

```text
apk/original/
```

## Disclaimer

This is an independent research project and is not affiliated with or endorsed by Jio or Reliance Industries Limited.
