# RADIO SILENCE

**Browser SDR Privacy Shield**

RADIO SILENCE is a privacy-focused browser extension designed to reduce unintended hardware exposure and browser-level device access by selectively blocking sensitive web APIs.

The extension intercepts browser API requests before page JavaScript executes and allows users to enable or disable protection layers individually.

Built with Chrome Manifest V3.

---

## Features

### Shield Controls

RADIO SILENCE can block:

- WebUSB
  - Prevents browser access to USB-connected hardware
  - Useful for reducing exposure to SDR dongles and connected peripherals

- Web Serial
  - Blocks serial device communication
  - Helps protect radio modems and serial-connected hardware

- WebHID
  - Prevents browser interaction with HID devices
  - Reduces access to controllers and custom hardware interfaces

- Web Bluetooth
  - Blocks Bluetooth scanning and device requests
  - Helps reduce nearby hardware discovery surfaces

- WebRTC
  - Blocks RTCPeerConnection access
  - Helps reduce IP leakage and browser communication exposure

- Media Devices
  - Prevents browser access to microphones and cameras
  - Adds another privacy layer against device enumeration

---

## Activity Monitoring

RADIO SILENCE includes:

- Per-tab intercept counters
- Real-time activity logging
- Visual shield health score
- Browser action badge updates
- Persistent privacy configuration storage

---

## Architecture

### Background Service Worker

Responsible for:

- Shield state management
- Intercept counting
- Badge updates
- Activity log storage

### Content Script (MAIN World)

Responsible for:

- Capturing browser API references before page scripts execute
- Installing privacy shield proxies
- Blocking protected API calls

### Content Bridge (ISOLATED World)

Responsible for:

- Configuration synchronization
- Messaging between extension components
- Runtime event forwarding

---

## Installation

### Developer Install

1. Clone repository

```bash
git clone https://github.com/YOUR_USERNAME/radio-silence.git
```

2. Open Chrome

Navigate to:

```
chrome://extensions/
```

3. Enable:

```
Developer Mode
```

4. Click:

```
Load unpacked
```

5. Select the project folder

RADIO SILENCE should now appear in your browser toolbar.

---

## Project Structure

```
radio-silence/
├── manifest.json
├── background.js
├── content.js
├── content-bridge.js
├── popup.html
├── popup.css
├── popup.js
├── README.md
└── LICENSE
```

---

## Permissions

Current permissions:

- storage

Additional permissions may be required depending on future functionality.

---

## Privacy Philosophy

RADIO SILENCE follows a simple principle:

> Sensitive browser APIs should remain under explicit user control.

Modern browsers expose increasingly powerful interfaces to connected hardware.

RADIO SILENCE provides an additional user-controlled protection layer designed to reduce unintended access surfaces.

---

## Future Ideas

- Exportable privacy reports
- Threat scoring
- Fingerprinting detection
- Domain allowlists
- Enhanced telemetry visualization
- Advanced hardware access analytics

---

## Version

Current Version:

```
1.0.0
```

---

## License

MIT License

Or proprietary licensing depending on deployment goals.

---

Built for privacy-conscious users who want stronger visibility and control over browser hardware access surfaces.
