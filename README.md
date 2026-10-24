# 📟 Codex Pager 4G

**A retro-inspired, standalone wireless pager for AI agent notifications, usage monitoring, and human approvals.**

> The AI works. The pager calls. The human decides.

[中文文档](README.zh-CN.md)

## Overview

Codex Pager 4G is an open-source hardware and software project that brings the classic pager into the age of AI agents.

Built around an ESP32-based microcontroller, the device combines a retro pager-style enclosure with modern wireless connectivity, a color display, physical buttons, and audible notifications.

It is designed to act as a dedicated companion for Codex and potentially other AI agents, allowing users to monitor activity, receive notifications, and respond to permission requests without constantly checking their computers.

**Project status:** Concept & Planning

**Project initiated:** October 24, 2026

## Key Features (Planned)

### 📊 Real-Time Usage Dashboard

- Display remaining 5-hour and weekly usage limits.
- Show the next usage reset time and countdown.
- Display usage status at a glance.
- Automatically refresh information when available.

### 🔔 Pager-Style Notifications

Classic three-beep pager alerts for important events:

| Event | Display | Notification |
|---|---|---|
| Usage exhausted | 😐🤲 | Three-beep alert |
| Usage reset | 😋 | Three-beep alert |
| Permission requested | 🥺 | Three-beep alert |
| Permission denied | 😭 | Visual feedback |
| Task completed | ✅ | Configurable notification |
| Agent error | ⚠️ | Warning notification |

Events and expressions may be customized in future versions.

### ✅ Physical Permission Controls

The device is designed to support human-in-the-loop agent workflows.

- Review pending permission requests.
- Approve or deny requests using physical buttons.
- Display the command or action being requested.
- Require explicit user confirmation.
- Redirect complex or potentially dangerous requests to the computer for detailed review.

**Permissions are never automatically approved by the pager.**

### 📡 Wireless Connectivity

The planned device supports two connectivity options:

- **Wi-Fi:** Built-in wireless networking through the ESP32 microcontroller.
- **4G LTE:** An optional integrated cellular modem with a SIM card slot for standalone mobile connectivity.

The goal is to provide notifications and status monitoring even when the user is away from their computer or local Wi-Fi network.

Cellular modem selection, network compatibility, and power consumption will be evaluated during development.

### 🎨 Retro Hardware Design

- Classic 1990s pager-inspired appearance.
- Custom 3D-printed enclosure.
- Compact color display supporting emoji graphics.
- Physical navigation and confirmation buttons.
- Retro-style buzzer.
- Rechargeable battery.
- Portable, pocket-friendly form factor.

## Proposed Hardware

| Component | Planned Specification |
|---|---|
| Main controller | ESP32-S3 |
| Display | Color TFT / IPS display |
| Wireless | 2.4 GHz Wi-Fi |
| Cellular | 4G LTE modem with SIM card slot |
| User input | Physical buttons |
| Audio | Buzzer |
| Power | Rechargeable lithium battery |
| Enclosure | Custom 3D-printed pager shell |

Specifications are preliminary and subject to change.

## System Architecture

```text
        AI Agent / Codex
                |
                v
       Companion Service
                |
         Wi-Fi / Internet
                |
        +-------+-------+
        |               |
       Wi-Fi          4G LTE
        |               |
        +-------+-------+
                |
           ESP32-S3
                |
     +----------+----------+
     |          |          |
   Display    Buzzer     Buttons
     |                     |
   Status              Approve /
   & Emoji               Deny
```

The companion service will manage agent integration, status synchronization, notification delivery, and authenticated approval requests.

## Design Principles

1. **Human in control:** The user retains final authority over agent actions.
2. **Information at a glance:** Important status information should be available immediately.
3. **Notify only when necessary:** Avoid unnecessary interruptions.
4. **Portable and independent:** Support operation away from the host computer.
5. **Secure by design:** Authenticate commands, reject stale requests, and prevent accidental approvals.
6. **Retro appearance, modern functionality:** Preserve the charm of classic pagers without sacrificing usability.

## Development Roadmap

- [x] Project concept and initial requirements
- [ ] Hardware component selection
- [ ] ESP32 display prototype
- [ ] Physical buttons and buzzer
- [ ] Usage dashboard
- [ ] AI agent integration
- [ ] Permission request handling
- [ ] Wireless notification delivery
- [ ] 4G LTE modem integration
- [ ] Battery and power optimization
- [ ] 3D-printed enclosure
- [ ] Portable prototype testing
- [ ] Initial hardware release

## Important Notes

This project is in the early planning stage. Hardware configurations, APIs, feature availability, and software architecture are subject to change.

Some proposed features depend on supported interfaces provided by AI agent software. Integration capabilities will be verified during development.

Codex Pager 4G is an independent experimental project and is not an official OpenAI product.

## Project Philosophy

Traditional pagers helped people stay reachable without remaining next to a telephone.

Codex Pager 4G explores a similar idea for AI agents:

**Let the agent work independently, and notify the human when attention or authorization is required.**

📟 **Beep. Beep. Beep. The agent needs you.**