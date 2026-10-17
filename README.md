Link to the tools webpage here: https://blackwirenetwork.github.io/Field-HUD/

May need to copy the link and paste it in your Web Browser and manually allow location services in your browser settings

## Current Status & Capabilities

Field HUD Pro is fully functional for all offline core features, calculations, and data management. You can immediately use it in the field for:
- Point logging and epoch-averaging using standard mobile GPS
- Importing and exporting standard CSV and DXF files
- Executing COGO calculations (inverses, station/offset, curve geometry)
- Managing CAD linework, point filters, and county GIS parcel lookups

*Note: High-precision, centimeter-level RTK GPS functionality requires pairing an external GNSS receiver (such as Topcon or Trimble) and configuring the optional NMEA bridge.*


# Field HUD: Pro Edition

Field HUD Pro is a serverless, offline-capable Progressive Web App (PWA) designed to transition standard mobile devices and tablets into professional-grade land surveying data collectors. By utilizing client-side processing, this tool allows field crews to collect precise geospatial data, perform complex coordinate geometry (COGO) calculations, and manage computer-aided design (CAD) linework entirely offline from a standard web browser.

---

## Realistic Use Cases

- **Boundary Reconnaissance and Recovery:** A crew chief uses the mobile map overlay to navigate toward historical property corners. By querying live county parcel data and using real-time State Plane coordinates, they can efficiently locate buried iron pins or concrete monuments in overgrown terrain.
    
- **Topographic and As-Built Surveys:** A crew chief maps a newly paved parking lot. By utilizing the application's Smart Linework modifiers, they walk the edge of pavement and back of curb, automatically generating CAD-ready polylines on their screen in real time.
    
- **Construction Layout and Staking:** A surveyor imports a CSV file of design coordinates for building foundations. They select a point, and the HUD provides real-time telemetry—Delta North, Delta East, and Distance—guiding them exactly where to set the physical marker.
    
- **Remote Fieldwork:** Working deep in a wooded area with zero cellular service, a crew continues to record points and calculate inverses. Because the app caches its engine and stores all point data locally via IndexedDB, data integrity is maintained. Upon returning to connectivity, they export a DXF file directly to the drafting team.

---

## Core Capabilities

- **Geospatial Engine and Coordinate Transformations:** The application integrates Leaflet mapping layers with real-time Proj4js spatial reference system transformations. This translates raw WGS84 satellite GPS data into accurate localized State Plane Coordinate Systems, such as NAD83 South Carolina.

- **Coordinate Geometry Suite:** The app executes core mathematical surveying algorithms natively in the browser. This includes point-to-point inverses, station and offset baseline tracking, and curve geometry solvers for civil construction layout.

- **Hardware Integration and Telemetry:** Field HUD utilizes the mobile Geolocation API with built-in epoch-averaging and quality control tolerance thresholds to mitigate multipath GPS errors. The architecture is also prepared to bridge external RTK GNSS hardware via local TCP NMEA streams for centimeter-level accuracy.

- **CAD Interoperability:** Client-side parsing handles standard PNEZD formats. The application natively compiles and exports deliverable CSV and DXF files directly to the device memory.

- **Persistent Offline Storage:** The system uses LocalForage to manage persistent local state and project databases, ensuring field data is securely stored on the hardware without requiring a centralized cloud backend.

---

## Tech Stack

- **Frontend:** HTML5, JavaScript (ES6+), Tailwind CSS
- **Mapping and Spatial:** Leaflet.js, Proj4js
- **Database:** IndexedDB via LocalForage
- **Deployment:** GitHub Pages with Automated Version-Control Cache-Busting

---
    
## Disclaimer

This software is an independent field assistant tool. The licensed Professional Land Surveyor or Crew Chief in charge maintains sole legal responsibility for verifying all construction layouts, property boundaries, and as-built measurements against recorded plats and physical control monuments.
