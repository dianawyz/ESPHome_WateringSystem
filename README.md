# ESPHome Watering System

An automated plant watering system built with ESP32 and ESPHome, featuring soil moisture monitoring, manual control, and Home Assistant integration.

## Hardware

### Schematics

### Bill of Materials (BOM)

| Component | Description | Price (RON) |
|-----------|-------------|-------------|
| ESP32 | Microcontroller board | 38 |
| DHT11 | Air humidity and temperature sensor | 10 |
| HW-080 | Soil moisture sensor | 4 |
| Water Pump | 12V water pump | 30 |
| Relay | Single channel relay module | 49 |
| Breadboard | - | 10 |
| 9V Battery | Power supply for water pump | 20 |
| **Total** | | **161** |

## Software

The project is organized as an ESPHome configuration file (`project.yaml`) that defines:

- **Sensors**: 
  - DHT11 on GPIO15 for temperature and humidity monitoring
  - HW-080 on GPIO34 (ADC) for soil moisture measurement (0-100%)
  
- **Actuators**:
  - Water pump relay on GPIO23 (hidden from UI)
  
- **Manual Control**:
  - "Water Plant" button triggers 3-second watering cycle
  - Updates last watering timestamp
  
- **Automatic Watering**:
  - Checks soil moisture every 4 days
  - Waters plant for 3 seconds if moisture drops below 50%
  
- **Integration**:
  - Home Assistant API for remote monitoring and control
  - WiFi connectivity for OTA updates
  - Timestamp tracking for watering events

## Testing and Results

The system was successfully deployed and tested over an extended period. All original project objectives were achieved:

### System Installation and Sensor Monitoring

[ESPHome Installation](/logs.png)

The ESPHome firmware was successfully connected to the ESP32 with stable WiFi connectivity and Home Assistant integration. The console logs shows:

- **Soil Moisture Sensor**: Successfully reading analog values and converting to percentage (52-59% range during testing)
- **DHT11 Sensor**: Accurate temperature (22.2°C) and humidity (59%) measurements 
- **Network Connectivity**: Stable connection with proper DNS resolution and over-the-air (OTA) update capability

### Long-term Performance Monitoring

[Sensor History Graph](/graph.png)

The 24-hour monitoring graphs demonstrate:

1. **Soil Moisture Tracking**: The system successfully monitors soil moisture levels, showing variations between 50-60% with clear spikes indicating watering events. The sensor accurately captures moisture changes over time.

2. **Ambient Temperature**: Stable temperature readings around 20-22°C throughout most of the monitoring period.

3. **Ambient Humidity**: Consistent humidity tracking ranging from 35-60%, showing expected daily variations in the environment.

### Home Assistant Dashboard Integration

[Garden Dashboard](/homeAssistant.png)

The Home Assistant mobile interface provides a clean, intuitive dashboard for monitoring and controlling the watering system.

### Achievements

**Automated Watering Logic**: Successfully implemented time-based (4-day interval) and threshold-based (50% moisture) watering triggers  
**Manual Control**: Water Plant button provides on-demand 3-second watering cycles  
**Home Assistant Integration**: Full integration achieved with control capabilities  
**Data Logging**: Continuous timestamp tracking and data visualization   

The system operates reliably as an autonomous plant care solution, successfully meeting all design specifications while providing comprehensive monitoring through Home Assistant.

## Demo




