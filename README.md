<div align="center">

  <!-- 1st Image: Project Banner -->
  <img src="https://github.com/alrafayethabib/Pothe/blob/79a91f0a358167066fa72db2bfb7b6da3b279664/Pothe_Banner.jpeg" alt="Pothe Banner - A Smart Public Transport Tracking and Demand Prediction System" width="100%" />

  <br />
  <br />

  # 🚌 Pothe (পথে): A Smart Public Transport Tracking & Demand Prediction System

  <p align="center">
    <b>A low-cost, human-assisted smart public transport ecosystem connecting passengers, checkers, bus owners, and government policymakers.</b>
  </p>

  <!-- Badges -->
  <p align="center">
    <img src="https://img.shields.io/badge/Frontend-React_PWA-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React PWA" />
    <img src="https://img.shields.io/badge/Styling-Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS" />
    <img src="https://img.shields.io/badge/Backend-Node.js_&_Express-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js" />
    <img src="https://img.shields.io/badge/Database-PostgreSQL_+_PostGIS-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL PostGIS" />
    <img src="https://img.shields.io/badge/Cache-Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis" />
    <img src="https://img.shields.io/badge/Maps-Google_Maps_API-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white" alt="Google Maps" />
  </p>

  <p align="center">
    <a href="#-about-the-project">About</a> •
    <a href="#-how-pothe-works">How It Works</a> •
    <a href="#-ui-previews--screenshots">Screenshots</a> •
    <a href="#-key-features-by-user-role">Key Features</a> •
    <a href="#-tech-stack">Tech Stack</a> •
    <a href="#-getting-started">Getting Started</a> •
    <a href="#-project-scope--roadmap">Roadmap</a>
  </p>
</div>

---

## 📖 About The Project

**Pothe (“পথে”)** is a web-based smart public transport ecosystem where human checkers, general passengers, bus owners, and government authorities share a central source of real-time transport intelligence. 

Instead of relying on expensive GPS hardware installed on every local bus, **Pothe** leverages existing human checkers stationed at fixed checkpoints along a route. By combining trusted checkpoint passenger counts with historical segment speeds and live Google Maps traffic data, Pothe accurately estimates bus locations, predicts arrival probabilities, displays crowd levels, and generates actionable demand reports for bus operators and policymakers.

---

## ⚠️ Problem Statement

Public bus commuters, operators, and transport authorities face several critical challenges daily:

1. **Unknown Bus Locations:** Passengers wait at stops with no way of knowing which buses are approaching or when they will arrive, especially during peak hours or bad weather.
2. **Unknown Crowd Levels:** Commuters cannot tell whether an approaching bus has available seats or is already overcrowded.
3. **Multi-Company Route Confusion:** Multiple bus companies operate on overlapping corridors, but passengers lack a unified platform to compare all available buses heading to their destination.
4. **High Hardware Cost for Owners:** Installing and maintaining dedicated GPS trackers on every local bus is costly for small operators, leaving owners blind to bus positions and passenger loads.
5. **Lack of Accountability:** Passengers have no structured channel to report staff misbehavior or inaccurate checker counts.
6. **No Demand Data for Policymakers:** Passenger load per route and stop is not statistically recorded, forcing route allocation decisions to rely on guesswork.

---

## ⚙️ How Pothe Works

Pothe operates through a seamless 4-step workflow:

```text
[1. Checker Records] ➔ [2. System Estimates] ➔ [3. Passenger Decides] ➔ [4. Owners & Govt Analyze]
```

1. **📋 Checker Records:** At fixed, geofenced checkpoints along a route, a checker selects the **Bus ID** and enters the number of **sitting** and **standing** passengers in just three taps. The server automatically attaches the timestamp and checkpoint coordinates.
2. **🧠 System Estimates:** Pothe combines the last recorded checkpoint pass of each bus with historical segment speeds and live **Google Maps traffic** to estimate its real-time position between checkpoints.
3. **🚏 Passenger Decides:** Passengers searching for a destination see approaching buses behind them categorized into two probability tiers (**Most Likely** and **Less Likely**), complete with Estimated Time of Arrival (ETA), Bus ID, company name, and live crowd badges.
4. **📊 Owners & Government Use the Data:** Bus owners monitor their fleet and passenger loads, while government authorities access weekly, monthly, six-monthly, and annual demand and complaint analytics.

---

## 📱 UI Previews & Screenshots

### 1️⃣ Passenger Mobile Application (User App)
The passenger-facing Progressive Web App (PWA) is designed to run smoothly even on low-end Android devices and weak network connections, offering bilingual support (**Bangla & English**).

<div align="center">
  <!-- 2nd Image: User App Screenshot -->
  <img src="https://github.com/alrafayethabib/Pothe/blob/70afe6bde0c0438bb5882477e1606048a729f8a4/User_view.jpeg" alt="Pothe Passenger Mobile App UI" width="380" />
</div>

* **Live Route & Bus Tracking:** View approaching buses on the map with estimated positions between checkpoints.
* **Arrival Probability & ETA:** See buses behind you sorted into **Most Likely** and **Less Likely** tiers with real-time ETA.
* **Crowd Level Badges:** Check sitting and standing passenger counts recorded at the latest checkpoint before boarding.
* **Destination Search & Accountability:** Find traffic-ranked routes to your destination and submit complaints against bus staff or checkers if needed.

---

### 2️⃣ Admin & Government Dashboard
A comprehensive web dashboard empowering **System Admins**, **Bus Owners**, and **Government Authorities** to manage operations, monitor fleet activity, and analyze route demand.

<div align="center">
  <!-- 3rd Image: Admin & Government Dashboard Screenshot -->
  <img src="./Gemini_Generated_Image_sr8azvsr8azvsr8a.jpeg" alt="Pothe Admin and Government Dashboard" width="90%" />
</div>

* **Bus, Route & Checkpoint Management:** Admins can register buses with unique IDs, configure ordered checkpoints with geofences, and assign checkers to shifts.
* **Government Demand Analytics:** Generate and export (**PDF / CSV**) periodic reports (weekly, monthly, six-monthly, yearly) on route demand, checkpoint crowding, and complaint statistics.
* **Immutable Audit Trail & Anomaly Detection:** Automatically flags implausible passenger counts and logs every entry, correction, and account action for transparency.

---

## 🌟 Key Features by User Role

| User Role | Core Capabilities |
| :--- | :--- |
| **🧍 Passenger** | • OTP-verified registration & guest browsing<br>• Destination search & traffic-ranked route recommendations<br>• View approaching buses behind the stop with **Most Likely / Less Likely** tiers & ETA<br>• View live bus crowd levels and raw sitting/standing counts from checkers<br>• Subscribe to bus arrival alerts & file/track complaints |
| **📋 Checker** | • Ultra-fast 3-tap interface to select Bus ID and input sitting & standing counts<br>• Automatic server-side timestamp & **PostGIS geofence validation**<br>• **Offline Queue & Sync** (stores entries locally when offline with original timestamps)<br>• Time-windowed entry correction with full audit logging |
| **🚌 Bus Owner** | • Track estimated bus positions and last checkpoint records across the fleet<br>• Analyze passenger load and demand trends per bus<br>• View and respond to passenger complaints regarding bus staff |
| **🏛️ Government Authority** | • View route-wise and checkpoint-wise passenger demand analytics<br>• Access weekly, monthly, 6-monthly, and annual statistical reports<br>• Monitor complaint statistics by route, company, and category<br>• Export reports in **PDF** and **CSV** formats for transport planning |
| **🛡️ System Admin** | • Manage routes, ordered checkpoints, buses, users, and checker shift assignments<br>• Review flagged anomalous entries and checker complaints<br>• Monitor immutable system-wide audit logs |

---

## 🛠️ Tech Stack

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Language** | JavaScript / TypeScript, SQL | Unified full-stack development and relational data queries |
| **Frontend** | React (PWA), Tailwind CSS | Responsive Progressive Web App optimized for mobile & desktop |
| **Backend** | Node.js, Express.js | RESTful API for auth, checker entries, position estimation & reports |
| **Database** | PostgreSQL + **PostGIS** | Relational storage with geospatial queries for checkpoint geofencing |
| **Caching** | Redis | Caching Google Maps traffic data and live bus position predictions |
| **Maps & Traffic** | Google Maps Platform | Maps JavaScript API, Directions API & Distance Matrix for live ETA |
| **Notifications** | Firebase Cloud Messaging (FCM) & SMS Gateway | Push notifications for approaching buses and OTP verification |
| **Testing** | Jest, Postman, Cypress | Unit testing, API validation, and end-to-end (E2E) testing |
| **Design** | Figma, draw.io | UI/UX prototyping, Use Case, ER, and system architecture modeling |

---

## 🚀 Getting Started

Follow these steps to set up the **Pothe** project locally on your machine.

### Prerequisites
* **Node.js** (v18+ recommended)
* **PostgreSQL** (with **PostGIS** extension enabled)
* **Redis** server
* **Google Maps API Key** (Directions, Distance Matrix, Maps JS enabled)

### Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/pothe.git](https://github.com/your-username/pothe.git)
   cd pothe
   ```

2. **Install Backend & Frontend dependencies:**
   ```bash
   # Install backend dependencies
   cd server
   npm install

   # Install frontend dependencies
   cd ../client
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the `server/` directory:
   ```env
   PORT=5000
   DATABASE_URL=postgresql://username:password@localhost:5432/pothe_db
   REDIS_URL=redis://localhost:6379
   JWT_SECRET=your_jwt_secret_key
   GOOGLE_MAPS_API_KEY=your_google_maps_api_key
   SMS_GATEWAY_API_KEY=your_sms_api_key
   FCM_SERVER_KEY=your_firebase_server_key
   ```

4. **Run Database Migrations (with PostGIS):**
   ```bash
   cd ../server
   npm run migrate
   ```

5. **Start the Development Servers:**
   ```bash
   # Start backend server
   npm run dev

   # In a new terminal, start the React PWA frontend
   cd ../client
   npm run dev
   ```

---

## 🗺️ Project Scope & Roadmap

- [x] **Phase 1: Pilot Version (Current Scope)**
  - Single pilot corridor deployment with ordered checkpoints, buses, and checkers.
  - Geofenced checker data entry with offline queue synchronization.
  - Rule-based bus position estimation using checkpoint records + Google Maps live traffic.
  - Passenger PWA with two-tier arrival probability (*Most Likely* & *Less Likely*) and crowd badges.
  - Owner Dashboard, Government Analytics Reports (PDF/CSV), and Complaint Management.
  - Bilingual UI (**Bangla & English**).

- [ ] **Phase 2: Future Scope**
  - Multi-corridor expansion and 1-transfer route recommendations.
  - Machine Learning (ML) based arrival time and passenger demand forecasting.
  - Automated push alerts (*"Your bus is arriving in 5 minutes"*).
  - Checker performance scoring and optional hybrid GPS integration.

---

## 🎓 Academic Context & Author

This project was developed as part of the **System Analysis & Design Capstone Project (Course Code: SE 231)** at **Daffodil International University (DIU)**.

* **Author:** Al Rafayet Habib
* **Student ID:** 251-35-084 (Batch: 44, Section: B2, Group: 01)
* **Course Teacher / Supervisor:** Abu Toha Md Faisal, Lecturer, Dept. of Software Engineering, DIU

---

<div align="center">
  <p>Made with ❤️ for smarter public transport in Bangladesh.</p>
</div>
