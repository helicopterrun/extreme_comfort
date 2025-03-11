# Multi-Zone HVAC Control Blueprint with Dew Point Priority & Logging

## 📌 Overview
This **Home Assistant automation blueprint** synchronizes multiple HVAC units while prioritizing:
- **Comfortable temperature & humidity levels**
- **Dew point-based Dry Mode activation**
- **Hysteresis to prevent frequent mode switching**
- **Multi-room agreement before mode switching**
- **Extensive logging for debugging**

## 🏗️ Entities Required
| Entity | Type | Purpose |
|--------|------|---------|
| `climate.living_room` | `climate` | HVAC unit for Living Room |
| `climate.bedroom` | `climate` | HVAC unit for Bedroom |
| `sensor.living_room_temp` | `sensor` | Temperature sensor for Living Room |
| `sensor.bedroom_temp` | `sensor` | Temperature sensor for Bedroom |
| `sensor.living_room_humidity` | `sensor` | Humidity sensor for Living Room |
| `sensor.bedroom_humidity` | `sensor` | Humidity sensor for Bedroom |
| `binary_sensor.living_room_occupancy` | `binary_sensor` | Detects if Living Room is occupied |
| `binary_sensor.bedroom_occupancy` | `binary_sensor` | Detects if Bedroom is occupied |
| `input_boolean.living_room_link` | `input_boolean` | Links Living Room to shared outdoor unit |
| `input_boolean.bedroom_link` | `input_boolean` | Links Bedroom to shared outdoor unit |
| `input_select.default_mode` | `input_select` | Default mode when no rooms call for heat/cool |

## ⚙️ Setup Instructions
1. **Install the Blueprint**
   - Copy the `.yaml` file into your Home Assistant `blueprints/automation` directory.
   - Reload automations.

2. **Configure Required Entities**
   - Ensure all climate, sensor, and binary sensor entities are available.

3. **Set Up the Default Mode**
   - Navigate to **Settings → Automations & Scenes → Blueprint Automations**.
   - Choose the default mode (`fan_only`, `dry`, `off`).

4. **Customize Hysteresis**
   - Set a **hysteresis delay** (e.g., 15 min) to prevent mode switching too quickly.

## 📝 How It Works
- **Mode is determined based on room requests** (heat/cool/dry).
- **Dew point calculations** determine when Dry Mode should override cooling.
- **Logging system tracks all mode changes**.
- **Hysteresis prevents rapid mode toggling**.

## 📊 Logging
- Mode changes will appear in **Home Assistant notifications**.
- Includes **dew point readings**, **requested heating/cooling counts**, and **default mode info**.

## 🎯 Future Enhancements
- Add **adaptive scheduling** based on time of day.
- Integrate **outdoor weather data** to predict mode changes.

---

This README provides **everything needed to deploy & understand** the blueprint! 🚀  
Would you like any additional documentation before finalizing?
