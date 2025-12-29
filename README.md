# 🔋 ESP32 Victron MPPT Monitor

<div align="center">

![Victron Energy](https://img.shields.io/badge/Victron-MPPT%20150%2F45-blue?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyIDJMMiAyMkgyMkwxMiAyWiIgZmlsbD0id2hpdGUiLz4KPC9zdmc+)
![ESP32](https://img.shields.io/badge/ESP32-DevKit-red?style=for-the-badge&logo=espressif&logoColor=white)
![ESPHome](https://img.shields.io/badge/ESPHome-2024.12-black?style=for-the-badge&logo=esphome&logoColor=white)
![Home Assistant](https://img.shields.io/badge/Home_Assistant-Compatible-41BDF5?style=for-the-badge&logo=home-assistant&logoColor=white)

**Monitor your Victron MPPT Solar Charge Controller with ESP32**  
*Two modes available: Bluetooth (BLE) or Serial (VE.Direct)*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-1.2.1-green?style=flat-square)](https://github.com/yourusername/victron-esp32)
[![Maintained](https://img.shields.io/badge/Maintained-Yes-brightgreen?style=flat-square)](https://github.com/yourusername/victron-esp32)

[📖 Documentation](#documentation) • [⚡ Features](#features) • [🚀 Quick Start](#quick-start) • [❓ FAQ](#faq)

</div>

---

## 📊 Overview

This project enables **real-time monitoring** of Victron MPPT Solar Charge Controllers using an **ESP32** and **ESPHome**. Monitor your solar production, battery status, and system health directly in **Home Assistant** or via a built-in web server.

### 🎯 Two Monitoring Modes

| Mode | Connection | Sensors | Range | Difficulty |
|------|-----------|---------|-------|------------|
| 🔵 **BLE** | Bluetooth | ~11 | 10m | ⭐ Easy |
| 🔌 **VE.Direct** | Serial Cable | 30+ | Unlimited | ⭐⭐ Medium |

---

## ✨ Features

### 🔵 BLE Mode (Bluetooth)
- 📡 **Wireless monitoring** - No cables needed
- 🔋 **Battery metrics** - Voltage, Current
- ☀️ **Solar metrics** - Power, Estimated Voltage/Current
- ⚡ **Production data** - Yield Today, Total Energy
- 🎯 **MPPT states** - BULK, ABSORPTION, FLOAT detection
- 📱 **Mobile friendly** - Works with VictronConnect app simultaneously

### 🔌 VE.Direct Mode (Serial)
- 🎯 **Full data access** - All available sensors (30+)
- 📏 **Real panel voltage** - Not estimated, actual measurement
- 📊 **Historical data** - Yesterday, Total, Max Power
- 🔧 **Firmware info** - Version, Serial Number
- 📈 **Enhanced metrics** - Day number, detailed tracking
- 🔗 **Reliable connection** - Wired, no interference

### 🌐 Common Features (Both Modes)
- 🕐 **NTP Time Sync** - Automatic time from time.google.com
- 🌍 **AST Timezone** - Atlantic Standard Time (UTC-4)
- ⏰ **12-hour format** - Date display: `12/27/2025 4:12 pm`
- 📊 **Energy Dashboard** - Home Assistant integration ready
- 🌐 **Web Server** - Built-in web interface
- 🔄 **OTA Updates** - Wireless firmware updates
- 📱 **Responsive UI** - Works on desktop and mobile
- 🏠 **Home Assistant** - Native integration via ESPHome

---

## 🎨 Screenshots

### Web Server Interface
```
┌─────────────────────────────────────────┐
│ VICTRON MPPT 150/45                     │
├─────────────────────────────────────────┤
│ Battery Voltage         13.79 V         │
│ Battery Current          1.52 A         │
│ PV Power                  850 W         │
│ PV Voltage              82.45 V         │
│ Yield Today              0.45 kWh       │
│ MPPT State               BULK           │
├─────────────────────────────────────────┤
│ ESP32 INFO                              │
├─────────────────────────────────────────┤
│ Uptime                   2d 5h 23m      │
│ Date                     12/27/2025     │
│                          4:12 pm        │
│ WiFi Signal              -65 dBm        │
│ IP Address               192.168.1.100  │
└─────────────────────────────────────────┘
```

### Home Assistant Dashboard
```
📊 Solar Production: 850 W
🔋 Battery: 13.79 V (1.52 A)
☀️ Today's Yield: 0.45 kWh
📈 Total Production: 125.50 kWh
⚡ Status: BULK Charging
```

---

## 🔧 Hardware Requirements

### Common Components
- ✅ **ESP32 DevKit** (any variant with WiFi)
- ✅ **Victron MPPT** Solar Charge Controller
  - Tested with: SmartSolar MPPT 150/45
  - Should work with: Any Victron MPPT with BLE or VE.Direct
- ✅ **USB Cable** for programming
- ✅ **WiFi Network** (2.4GHz)

### 🔵 BLE Mode Specific
- ✅ **Victron Instant Readout** enabled (via VictronConnect app)
- ✅ **Encryption Key** from VictronConnect app

### 🔌 VE.Direct Mode Specific
- ✅ **VE.Direct Cable** or adapter
- ✅ **JST-PH 2.0 4-pin connector** (optional, for custom cable)
- ✅ Wiring:
  - `ESP32 GPIO16 (RX)` ← `VE.Direct TX (Yellow)`
  - `ESP32 GND` ← `VE.Direct GND (Black)`

---

## 🚀 Quick Start

### 1️⃣ Choose Your Mode

#### 🔵 BLE Mode - Wireless
```bash
# Use this if you want:
✅ Easy installation (no soldering)
✅ Wireless monitoring
✅ Quick setup (5 minutes)
```

#### 🔌 VE.Direct Mode - Wired
```bash
# Use this if you want:
✅ Complete data (30+ sensors)
✅ Real panel voltage
✅ Maximum reliability
```

### 2️⃣ Install ESPHome

```bash
# Install ESPHome CLI
pip3 install esphome

# Or use Home Assistant Add-on
# Settings → Add-ons → ESPHome
```

### 3️⃣ Clone Repository

```bash
git clone https://github.com/yourusername/victron-esp32.git
cd victron-esp32
```

### 4️⃣ Configure Your Device

#### For BLE Mode:
```bash
# Edit maria-victron-ble-v1.2.1-REORGANIZED.yaml
# Update these values:

wifi:
  ssid: "YOUR_WIFI_SSID"
  password: "YOUR_WIFI_PASSWORD"

substitutions:
  smart_solar_mac_address: "AA:BB:CC:DD:EE:FF"  # Your MPPT MAC
  smart_solar_encryption_key: "your_32_char_key"  # From VictronConnect
```

#### For VE.Direct Mode:
```bash
# Edit maria-victron-ve-direct-v1.2.1-REORGANIZED.yaml
# Update these values:

wifi:
  ssid: "YOUR_WIFI_SSID"
  password: "YOUR_WIFI_PASSWORD"

# Hardware connections:
# GPIO16 (RX) ← VE.Direct TX
# GND ← VE.Direct GND
```

### 5️⃣ Flash ESP32

```bash
# First time (via USB)
esphome run maria-victron-ble-v1.2.1-REORGANIZED.yaml

# Or for VE.Direct:
esphome run maria-victron-ve-direct-v1.2.1-REORGANIZED.yaml

# Future updates (OTA)
esphome run your-config.yaml --device 192.168.1.100
```

### 6️⃣ Access Your Device

**Web Server:**
```
http://192.168.1.100
```

**Home Assistant:**
```
Configuration → Integrations → ESPHome
→ Discovered: "Victron ESP32"
```

---

## 📊 Sensor Comparison

### 🔵 BLE Mode Sensors

| Sensor | Description | Unit |
|--------|-------------|------|
| Battery Voltage | Battery terminal voltage | V |
| Battery Current | Charging current | A |
| PV Power | Solar panel power | W |
| PV Voltage (Est) | Estimated panel voltage | V |
| PV Current (Est) | Calculated panel current | A |
| Yield Today | Energy produced today | kWh |
| Energy Produced | Cumulative energy | kWh |
| MPPT State | Charging state | BULK/FLOAT/etc |
| WiFi Signal | ESP32 WiFi strength | dBm |
| Uptime | Device uptime | Formatted |
| ESP32 Date | Current date/time | 12h format |

**Total: ~11 sensors**

### 🔌 VE.Direct Mode Sensors

All BLE sensors **PLUS**:

| Additional Sensor | Description | Unit |
|-------------------|-------------|------|
| Panel Voltage | **Real** panel voltage | V |
| Panel Current | Calculated from V/P | A |
| Yield Yesterday | Yesterday's production | kWh |
| Yield Total | Lifetime production | kWh |
| Max Power Today | Today's peak power | W |
| Max Power Yesterday | Yesterday's peak | W |
| Day Number | Days since last reset | days |
| Charging Mode | Detailed charge state | Text |
| Error | Error code | Number |
| Tracking Mode | MPPT tracking status | Text |
| Firmware Version | MPPT firmware | Text |
| Serial Number | Device serial | Text |

**Total: 30+ sensors**

---

## 📝 Configuration Files

### Project Structure
```
victron-esp32/
├── 🔵 BLE/
│   ├── maria-victron-ble-v1.2.1-REORGANIZED.yaml
│   └── victron-mppt-ble-v1.2.1-REORGANIZED.yaml
├── 🔌 VE.Direct/
│   ├── maria-victron-ve-direct-v1.2.1-REORGANIZED.yaml
│   └── victron-esp32-ve-direct-v1.2.1-REORGANIZED.yaml
├── 📖 docs/
│   ├── BLE_SETUP.md
│   ├── VEDIRECT_SETUP.md
│   └── TROUBLESHOOTING.md
└── README.md
```

### Key Configuration Sections

#### NTP Time Sync
```yaml
time:
  - platform: sntp
    timezone: AST4  # UTC-4
    servers:
      - time.google.com
    update_interval: 4h  # Sync on boot + every 4 hours
```

#### Date/Time Display
```yaml
text_sensor:
  - platform: template
    name: "ESP32 Date"
    # Format: MM/DD/YYYY H:MM am/pm
    # Example: 12/27/2025 4:12 pm
```

---

## 🏠 Home Assistant Integration

### Energy Dashboard Setup

1. **Settings** → **Dashboards** → **Energy**
2. Add Solar Production:
   - **Power:** `sensor.victron_pv_power`
   - **Energy:** `sensor.victron_energy_produced`

### Example Lovelace Card

```yaml
type: entities
title: Solar Monitor
entities:
  - entity: sensor.victron_battery_voltage
    name: Battery
  - entity: sensor.victron_pv_power
    name: Solar Power
  - entity: sensor.victron_yield_today
    name: Today's Yield
  - entity: sensor.victron_mppt_state
    name: Status
  - entity: sensor.esp32_date
    name: Last Update
```

### Automation Example

```yaml
automation:
  - alias: "Solar: High Production Alert"
    trigger:
      platform: numeric_state
      entity_id: sensor.victron_pv_power
      above: 800
    action:
      service: notify.mobile_app
      data:
        message: "☀️ Solar producing {{ states('sensor.victron_pv_power') }}W!"
```

---

## 🔍 Troubleshooting

### 🔵 BLE Mode Issues

**Problem:** No data from MPPT
```bash
Solution:
1. Check MAC address is correct
2. Verify encryption key
3. Enable "Instant Readout" in VictronConnect
4. ESP32 within 10m range
```

**Problem:** Connection drops
```bash
Solution:
1. Reduce distance to MPPT
2. Check for WiFi/BT interference
3. Verify MPPT firmware updated
```

### 🔌 VE.Direct Mode Issues

**Problem:** No serial data
```bash
Solution:
1. Verify wiring: GPIO16 ← TX, GND ← GND
2. Check baud rate: 19200
3. Logger baud_rate MUST be 0
4. Verify VE.Direct cable not damaged
```

**Problem:** Partial data only
```bash
Solution:
1. Check RX buffer size (256 bytes)
2. Verify ESP-IDF framework (not Arduino)
3. Monitor logs for parse errors
```

### Common Issues (Both Modes)

**Problem:** WiFi won't connect
```bash
Solution:
1. Check SSID/password
2. Verify 2.4GHz network (not 5GHz)
3. Check signal strength
4. Try AP fallback mode
```

**Problem:** Time not syncing
```bash
Solution:
1. Verify internet connection
2. Check firewall allows NTP
3. Wait 30 seconds after boot
4. Check logs for "Time synchronized"
```

---

## 📚 Documentation

### Getting Your Encryption Key (BLE)

1. Open **VictronConnect** app
2. Connect to your MPPT
3. Settings → **Product Info**
4. Enable **Instant Readout**
5. Copy the **Encryption Key** (32 characters)

### Getting MAC Address (BLE)

**Option 1: VictronConnect**
```
Settings → Product Info → Bluetooth Address
```

**Option 2: ESP32 Scan**
```bash
# Run BLE scanner
esphome logs your-config.yaml
# Look for "Victron" devices
```

### Wiring Diagram (VE.Direct)

```
VE.Direct Port (RJ12):
┌─────────────┐
│ 1 2 3 4 5 6 │
└─────────────┘
  │ │ │ │
  │ │ │ └─ Pin 4: TX (Yellow) → ESP32 GPIO16 (RX)
  │ │ └─── Pin 3: GND (Black) → ESP32 GND
  │ └───── Pin 2: RX (Not used)
  └─────── Pin 1: Power (Not used)

ESP32:
┌──────┐
│ GPIO │
│  16  ├─ RX ← VE.Direct TX (Yellow)
│  GND ├─ GND ← VE.Direct GND (Black)
└──────┘
```

---

## 🔄 Updates & Versions

### Current Version: 1.2.1

**Features:**
- ✅ NTP time synchronization
- ✅ 12-hour date/time format
- ✅ AST timezone support
- ✅ Reorganized sensor order
- ✅ ESP-IDF framework
- ✅ Enhanced uptime display

### Changelog

**v1.2.1** (2024-12-27)
- Added NTP sync (boot + every 4h)
- Added ESP32 Date sensor
- Reorganized sensor logical order
- Fixed logger encoding issues
- Updated sensor naming conventions

**v1.2.0** (2024-12-26)
- Changed to ESP-IDF framework
- Fixed sensor name issues
- Improved lambda functions

**v1.0.0** (2024-12-25)
- Initial release
- BLE and VE.Direct support

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Development Setup

```bash
# Clone repo
git clone https://github.com/yourusername/victron-esp32.git

# Create feature branch
git checkout -b feature/amazing-feature

# Make changes and test
esphome compile your-config.yaml

# Commit
git commit -m 'Add amazing feature'

# Push
git push origin feature/amazing-feature
```

---

## ⭐ Support

If this project helped you, please ⭐ star it on GitHub!

### Buy Me a Coffee ☕

<a href="https://www.buymeacoffee.com/yourusername" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Credits

- **[ESPHome](https://esphome.io/)** - Amazing framework
- **[Home Assistant](https://www.home-assistant.io/)** - Best home automation
- **[Victron Energy](https://www.victronenergy.com/)** - Excellent solar hardware
- **[KinDR007](https://github.com/KinDR007/VictronMPPT-ESPHOME)** - VE.Direct library
- **[Fabian-Schmidt](https://github.com/Fabian-Schmidt/esphome-victron_ble)** - BLE library

---

## 📧 Contact

- **GitHub:** [@yourusername](https://github.com/yourusername)
- **Email:** your.email@example.com
- **Forum:** [ESPHome Community](https://community.home-assistant.io/)

---

## 🔗 Related Projects

- [Victron MPPT MQTT](https://github.com/example/victron-mqtt)
- [ESPHome Victron](https://github.com/example/esphome-victron)
- [Solar Monitor Dashboard](https://github.com/example/solar-dashboard)

---

<div align="center">

### 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/victron-esp32&type=Date)](https://star-history.com/#yourusername/victron-esp32&Date)

---

**Made with ❤️ for the Solar Community**

![Visitors](https://visitor-badge.laobi.icu/badge?page_id=yourusername.victron-esp32)
![GitHub last commit](https://img.shields.io/github/last-commit/yourusername/victron-esp32?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/yourusername/victron-esp32?style=flat-square)

</div>
