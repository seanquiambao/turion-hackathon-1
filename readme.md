# Schedule
- Kickoff: 9:00am – 9:30am
- Development: 9:30am – 12:00pm
- Lunch: 12:00pm – 1:00pm
- Development: 1:00pm – 4:00pm
- Presentations/Judging: 4:00pm – 5:00pm
- Awards: 5:15pm

# Problem Statements

---

## 1. Personal Satellite Notifications

**Problem Statement:**  
Space enthusiasts and researchers lack easy ways to know when specific satellites pass overhead for observation or data collection. Current solutions require technical knowledge or multiple specialized applications.

**Challenge:**  
Create a user-friendly mobile application that allows users to:
- Subscribe to specific satellites from a comprehensive database  
- Receive timely notifications before selected satellites pass overhead  
- View satellite paths on an interactive map  
- Provide optimal viewing conditions and locations  
- Share sightings with a community of space enthusiasts  

**Impact:**  
Democratize access to satellite tracking, enhance citizen science opportunities, and increase public engagement with space missions.

**Resources:**

- [CelesTrak - NORAD Two-Line Element Sets (TLE)](https://celestrak.org/NORAD/elements/)  
  Provides orbital elements for thousands of active satellites.

- [CelesTrak GP Data Format Documentation](https://celestrak.org/NORAD/documentation/gp-data-formats.php)  
Detailed reference on the General Perturbations (GP) model—commonly represented using Two-Line Element Sets (TLEs)—including API formats, query parameters, and usage examples.
---

## 2. Solar System Mission Explorer

**Problem Statement:**  
Understanding the current status and position of active space missions across our solar system remains difficult for the general public and educators.

**Challenge:**  
Develop an interactive visualization tool that:
- Displays real-time approximate positions of NASA, ESA, and other space agency missions  
- Shows trajectory paths and mission milestones on a 3D solar system model  
- Includes mission details, objectives, and current status  
- Updates automatically using publicly available mission data  
- Offers educational content about each mission and celestial body  

**Impact:**  
Create an engaging educational tool that increases public awareness of ongoing space exploration efforts and inspires future generations of space scientists and engineers.

**Resources:**  
- [NASA JPL Horizons System](https://ssd.jpl.nasa.gov/horizons/)  
  Provides ephemeris and trajectory data for spacecraft and celestial bodies across the solar system.

---

## 3. AI-Powered Telemetry Anomaly Detection

**Problem Statement:**  
Mission control systems generate vast amounts of telemetry data that must be continuously monitored for anomalies, creating high cognitive load for operators and risking missed critical events.

**Challenge:**  
Build an AI system that:
- Ingests and processes multiple telemetry data streams in real time  
- Learns normal operational parameters for different mission phases  
- Detects anomalies and unusual patterns using machine learning  
- Prioritizes alerts based on severity and mission impact  
- Provides explanations for detected anomalies to assist human operators  
- Integrates with existing notification systems  

**Impact:**  
Reduce operator workload, minimize response time to critical anomalies, and potentially prevent mission failures through early detection of issues.

---

## 4. Mission Control Interface Builder

**Problem Statement:**  
Creating custom interfaces for mission control requires specialized programming knowledge, limiting the ability to quickly adapt to mission needs or optimize operator workflow.

**Challenge:**  
Design a drag-and-drop interface builder that enables:
- Creation of custom mission control screens without coding  
- Real-time display of telemetry data with customizable visualizations  
- Command composition and transmission with safety validation  
- Historical data review and trend analysis  
- Collaborative workspace for multiple operators  
- Export/import of screen configurations for different mission phases  

**Impact:**  
Increase mission control efficiency, reduce development time for custom interfaces, and allow operators to optimize their workflow based on specific mission requirements.

**Example Command/Telemetry Definitions:**

`command.json`
```json
{
  "command_name": "ENABLE_TLM_OUTPUT",
  "description": "Enables transmission of telemetry data through the radios.",
  "fields": [
    {
      "name": "OUTPUT_RADIO",
      "description": "Specifies which radio to use for telemetry output",
      "type": "UINT",
      "value": 0,
      "range": {
        "min": 1,
        "max": 255
      }
    },
    {
      "name": "SECONDS",
      "description": "Duration in seconds to enable telemetry output",
      "type": "UINT",
      "value": 0,
      "range": {
        "min": 1,
        "max": 65535
      }
    }
  ],
  "hazardous": false
}
```

`telemetry.json`
```json
{
  "telemetry_name": "TLM_OUTPUT_HK",
  "description": "Housekeeping Telemetry Packet",
  "fields": [
    {
      "name": "AP_ID",
      "description": "APP ID",
      "type": "UINT",
      "value": 0,
      "limit": {
        "min": 0,
        "max": 65535
      }
    },
    {
      "name": "CCSD_BOOT_COUNT",
      "description": "Boot Count",
      "type": "UINT",
      "value": 0,
      "limit": {
        "min": 0,
        "max": 65535
      }
    },
    {
      "name": "PACKET_TIME",
      "description": "Timestamp indicating when the packet was received, in ISO 8601 format",
      "type": "STRING",
      "value": "2025-05-13T00:00:00Z"
    },
    {
      "name": "OUTPUT_RADIO",
      "description": "Active radio for telemetry output",
      "type": "UINT",
      "value": 1,
      "limit": {
        "min": 1,
        "max": 2
      }
    },
    {
      "name": "LAST_RECEIVED_ID",
      "description": "Last received command ID",
      "type": "UINT",
      "value": 0,
      "limit": {
        "min": 0,
        "max": 500
      }
    },
    {
      "name": "TLM_OUTPUT_REMAINING_SECS",
      "description": "Number of seconds left that ENABLE_TLM_OUTPUT is active",
      "type": "UINT",
      "value": 0,
      "limit": {
        "min": 0,
        "max": 900
      }
    }
  ]
}
```


#### 

---

## 5. 3D Thermal Gradient Visualization System

**Problem Statement:**  
Spacecraft thermal engineers lack intuitive tools to visualize and analyze thermal conditions across satellite components in three dimensions, making it difficult to identify hotspots, thermal imbalances, or cooling system inefficiencies that could compromise mission success.

**Challenge:**  
Develop an interactive 3D visualization system that:
- Maps thermal telemetry data from discrete sensor positions onto a complete 3D model of the satellite  
- Interpolates temperatures between sensor points to generate continuous thermal gradients  
- Displays color-coded heat maps overlaid on the satellite structure  
- Enables time-based playback to observe thermal changes during different mission phases or orbital positions  
- Allows engineers to rotate, zoom, and section the model to examine internal components  
- Supports threshold-based alerts when temperatures approach operational limits  
- Exports analysis reports and thermal profile snapshots  

**Impact:**  
Enhances spacecraft safety and diagnostics by transforming thermal telemetry into intuitive, interactive 3D visualizations for real-time analysis and alerting.

**Example Dataset:**  
- [Thermal Data CSV - `thermal_data_final.csv`](./thermal_data.csv)

**3D Model Resource:**  
- [Satellite 3D Model - `satellite.obj`](./satellite.obj)