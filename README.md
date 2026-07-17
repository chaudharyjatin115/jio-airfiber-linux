# Jio AirFiber Linux

> Reverse engineering the JioHome Android application to build an open-source Linux client for Jio AirFiber devices.

This repository documents my research into how the JioHome app communicates with Jio AirFiber hardware. The long-term goal is to develop a native Linux utility that provides the same functionality without requiring the official Android application.

Along the way, this repository serves as a place to document protocols, APIs, research notes, and implementation progress.

## Goals

* Analyze the JioHome Android application.
* Document the communication protocol.
* Understand authentication and device management.
* Build a native Linux CLI.
* Develop a graphical Linux client.

## Current Status

The project is currently in the research phase.

### Roadmap

* [ ] Analyze the APK
* [ ] Document network traffic
* [ ] Reverse engineer authentication
* [ ] Identify local and cloud APIs
* [ ] Investigate native libraries
* [ ] Implement `jioctl`
* [ ] Develop a desktop interface

## Repository Structure

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

## Tooling

* Android Studio
* ADB
* JADX
* Apktool
* Frida
* Ghidra
* Wireshark
* mitmproxy
* Python

## Motivation

I didn't like to rely on an Android application for basic device management if the functionality can be implemented through documented and interoperable protocols.

This project exists to understand those protocols and build an open-source alternative.

## Progress

### Day 1

* Still in research phase
## Legal

This project is intended for research and interoperability with hardware owned by the user.

This repository does **not** include proprietary source code, assets, or binaries from the JioHome application. Only original code, documentation, and independently derived observations are published.

Users are responsible for ensuring their use of this project complies with applicable laws, license agreements, and terms of service.

## Contributing

Contributions are welcome.

If you've identified undocumented endpoints, protocol behavior, or implementation improvements, feel free to open an issue or submit a pull request with enough detail for others to reproduce your findings.

## Vision

The end goal is a native Linux utility similar to:

```bash
jioctl login
jioctl status
jioctl clients
jioctl wifi enable
jioctl wifi disable
jioctl reboot
jioctl firewall
jioctl speedtest
```

with a graphical interface planned for the future.

## Disclaimer

This is an independent open-source research project and is **not affiliated with, endorsed by, or sponsored by Jio or Reliance Industries Limited**.

All trademarks, product names, and logos are the property of their respective owners.
