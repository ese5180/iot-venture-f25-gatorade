[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/9GQ6o4cu)

# IoT Venture Pitch

## ESE5180: IoT Wireless, Security, & Scaling

**Team Name:** Gatorade

| Team Member Name | Email Address       |
|------------------|---------------------|
| James Steeman | [jsteeman@seas.upenn.edu](jsteeman@seas.upenn.edu) |
| Joaquin Revello Lerena | [joaquinr@seas.upenn.edu](joaquinr@seas.upenn.edu) |
| Chirag Satapathy | [csat28@seas.upenn.edu](csat28@seas.upenn.edu) |

**Weekly Meeting:** Wednesday 7pm

**GitHub Repository URL:** [https://github.com/ese5180/iot-venture-f25-gatorade](https://github.com/ese5180/iot-venture-f25-gatorade)

## Concept Development

### Product Function

Our smart HVAC system will integrate permanent sensors at key nodes throughout ductwork to continuously monitor air quality, VOC, humidity, then alert operators to deploy an AI-guided mobile robot for chemical-free cleaning using UV-C sterilization and adaptive brushing to achieve 99.99% pathogen elimination. The sensor network will predict contamination issues and guide operators to exact problem locations, while the lightweight bot will provide superior cleaning results in 30 minutes versus 2-3 hours for competitors. This intelligent system will deliver better performance at lower cost by combining continuous monitoring with smart operator guidance for targeted, efficient cleaning.

### Target Market & Demographics

**Who will be using your product?**

- Facility managers at commercial buildings (offices, hospitals, schools, retail)
- HVAC technicians who will operate the AI-guided cleaning bot
- Building maintenance staff monitoring the sensor network dashboard
- Property managers overseeing multiple buildings

**Who will be purchasing your product?**

- Commercial building owners (office buildings, shopping centers, hotels)
- Healthcare facility administrators (hospitals, clinics, care facilities)
- Educational institutions (universities, school districts)
- Property management companies managing multiple commercial properties
- Data center operators requiring precise environmental control

**Where in the world would you deploy your product?**

- Primary markets: North America (US, Canada) - strict indoor air quality regulations
- Secondary markets: Europe (UK, Germany, Nordic countries) - high environmental standards
- Growth markets: Australia, Japan, Singapore - advanced building management adoption
- Future expansion: Major commercial centers in developing markets (Dubai, Hong Kong, major Chinese cities)

**How large is the market you're targeting?**

- Global HVAC services market: ~$200 billion annually
- Building management systems: ~$20 billion annually
- Indoor air quality monitoring: ~$5 billion annually growing 8%+ yearly
- Serviceable addressable market: ~$15-25 billion (commercial buildings with centralized HVAC)

- Target segment (50,000+ sq ft commercial): ~$8-12 billion annually

**How much of that market do you expect to capture?**

- Year 1-2: 0.01% = $1-2 million (pilot customers, proof of concept)
- Year 3-5: 0.1% = $10-25 million (regional expansion, established product)
- Year 5-10: 1-2% = $100-250 million (national presence, market leadership)
- Long-term potential: 5-10% = $500M-$1.2B (dominant platform with international expansion)

**What competitors are already in the space?**

Direct Competitors

- Teinnova Multibot - Professional duct cleaning robots ($50K+ equipment)
- JettyRobot S - Industrial pipeline inspection/maintenance ($100K+ systems)

Indirect Competitors

- Traditional HVAC cleaning services - Manual cleaning companies
- Smart building management systems - Johnson Controls, Honeywell, Siemens
- Indoor air quality monitors - Airthings, PurpleAir, Awair
- Smart HVAC filters - 3M Filtrete, Nordic Pure smart filters

#### Key Differentiation

No existing competitor combines continuous sensor monitoring with AI-guided mobile cleaning and chemical-free UV-C sterilization in a comprehensive building health management platform.

### Stakeholders

We have reached out to several stakeholders, including emailing EOS at UPenn, and submitting web contact forms for LG and Hitachi, but have not solidified any individual stakeholder at this point.

![alt text](image.png)

Since we believe the current idea of our product will be more directed towards HVAC companies and building managment than maintenance staff, we continuing to reach out to additional companies (through sales departments) for feedback on our idea.

### System-Level Diagrams

#### Sensor Node

![alt text](images/5180_Sensor_Node.drawio.png)

#### Gateway

![alt text](images/5180_Gateway.drawio.png)

#### Robot

We will start by leveraging an existing robot and prototyping on top/hacking the robot to add cleaning functionality. Below is a very simple diagram indicating our added peripherals, which we will first attempt to power from the robot's power architecture, but add external battery/power management if necessary.

![alt text](images/5180_Robot.drawio.png)

### Security Requirements Specification

#### Security Overview

The system will ensure data, communications, and firmware integrity are protected from tampering, eavesdropping, and unauthorized access. Security measures particularly focus on safeguarding the gateway and nodes, which are in continuous operation and not always being observed.

#### Security Definitions, Abbreviations

- OTA: Over the air firmware updates
- GUI: Graphic User Interface

#### Security Functionality

| Requirement ID | Requirement Title | Description | Rationale |
|----------------|-------------------|-------------|-----------|
| SEC 01 | Gateway Firmware Integrity | Gateway shall run only firmware from signed OTA updates, and shall securely store keys | The gateway acts as a bridge between the sensor node mesh network and the cloud (data portal etc.), and compromise here could expose the client's network and leave them vulnerable to attacks and breaches |
| SEC 02 | Autheticate Nodes | Each sensor node shall authenticate in the mesh network using unique key/certification and ignore messages from tampered systems | This prevents unauthorized devices from disrupting the mesh or tampering with the data at the hardware level. It also protects from counterfit devices being added to our network |
| SEC 03 | Data Encryption | Communication from nodes, gateway and GUI interface shall be encrypted | This protects potentially sensitive IAQ and predictive maintenance data from eavesdropping and tampering at the data level |

### Hardware Requirements Specification

#### Hardware Overview

The system contains a mobile robot for HVAC navigation, duct cleaning operations and sensor node depolyment. Low power sensor nodes will be deployed in the HVAC system for data collection to identify system issues and enable predictive mainenance. There will also be a gateway node.

#### Hardware Definitions, Abbreviations

- HVAC: Heating, Ventilation, and Air Conditioning
- VOCs: Volatile Organic Compounds
- UV-C: Ultraviolet C - short-wavelength UV light used for chemical-free disinfection and sterilization

#### Hardware Functionality

| Requirement ID | Requirement Title | Description | Rationale |
|----------------|-------------------|-------------|-----------|
| HRS 01 | Bot Size and Weight | The mobile bot shall be maximum 300mm x 100mm x 100mm (can change) and weigh less than 5kg to fit through standard commercial ductwork. | Must navigate existing HVAC systems without modifications or damage. |
| HRS 02 | UV-C Sterilization | The bot shall include UV-C LEDs with 360-degree coverage to achieve 99.99% pathogen elimination. | UV-C sterilization is the core technology differentiator for chemical-free cleaning. |
| HRS 03 | Sensor Durability | Sensor nodes shall operate in -10°C to +70°C, 0-95% humidity with IP65 protection, VOC and 12+ month battery life. | HVAC environments are harsh; sensors must survive without frequent maintenance. |
| HRS 04 | Wireless Communication | System shall maintain mesh networking with 100m range and <2 second response time between sensors and bot. | Real-time monitoring and response is critical for building health management. |
| HRS 05 | Camera System | The bot shall include HD cameras with LED illumination for visual inspection and AI-powered contamination detection in low-light ductwork environments. | Visual documentation and AI analysis are essential for contamination identification and compliance reporting. |

### Software Requirements Specification

#### Software Overview

The node/gateway software shall collect, process, and transmit sensor data HVAC sensor nodes to a centralized gateway. It shall manage sensor feature toggling, battery optimization, and secure communications across BLE mesh and Wi-Fi networks.

The robot software shall collect and process real time controls and data for navitagion and cleaning operations.

#### Software Users

- Facility managers at commercial buildings (offices, hospitals, schools, retail) using IoT dashboard
- HVAC technicians operating cleaning robot
- Building maintenance staff monitoring the IoT dashboard
- Property manager

#### Software Abbreviations

- MCU: Microcontroller Unit

#### Software Functionality

| Requirement ID | Requirement Title | Description | Rationale |
|----------------|-------------------|-------------|-----------|
| SRS 01 | Battery Optimization | Software shall use MCU low power modes, intermmittent sensing and transmission to extend battery life to at least one year | It is important to maximize sensor lifetime to minimize disruptions and maintenance on the network |
| SRS 02 | Robot Deployment/Guidance | IoT dashboard shall alert operators to provide precise contamination or fault locations for targeted cleaning/work orders | Reduces manual inspection time and system downtime |
