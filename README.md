<p align="center">
  English · <a href="#">বাংলা</a>
</p>

<h1 align="center">Pothe: A Smart Public Transport Tracking and Demand Prediction System</h1>

<p align="center">
  <strong>One ecosystem for human-assisted bus tracking, arrival prediction, and route demand analytics.</strong><br>
  See exactly where your bus is, how crowded it is, and when it will arrive.
</p>

<br>

<!-- UI Showcase Images -->
<p align="center">
  <img src="assets/admin_dashboard.jpeg" width="600" alt="Pothe Admin Dashboard showing Bus Management and Nilachol Express">
</p>
<p align="center">
  <img src="assets/passenger_app.jpeg" width="300" alt="Pothe Passenger Mobile App showing Nilachol Express Route">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-PWA-blue.svg" alt="React">
  <img src="https://img.shields.io/badge/Node.js-Backend-green.svg" alt="Node.js">
  <img src="https://img.shields.io/badge/PostgreSQL-PostGIS-336791.svg" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/license-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/badge/Status-Capstone_Project-success.svg" alt="Status">
</p>

<p align="center">
  <a href="#-project-overview">Overview</a> · 
  <a href="#-how-pothe-works">How it Works</a> · 
  <a href="#-key-features-by-user-role">Key Features</a> · 
  <a href="#-tech-stack">Tech Stack</a> · 
  <a href="#-quick-start">Quick Start</a>
</p>

> [!IMPORTANT]  
> This project is developed as a System Analysis & Design Capstone Project (SE 231) for Daffodil International University. 

---

## 📖 Project Overview

"Pothe" (“পথে”) is a smart public transport tracking and demand prediction system. It serves as a centralized ecosystem where human checkers, passengers, bus owners, and government authorities share real-time information about bus locations, crowd levels, and transport demand. 

Unlike traditional setups requiring expensive GPS tracking hardware in every vehicle, Pothe utilizes a low-cost, human-assisted checkpoint approach combined with historical travel times and live Google Maps traffic data to estimate bus locations and arrival times.

## ⚙️ How Pothe Works

Pothe operates through a seamless flow of data collection, processing, and distribution:

```mermaid
flowchart TD
    subgraph Data Collection
        A[Checker at Checkpoint] -->|Selects Bus ID & Enters Sitting/Standing Count| B(Pothe Backend)
    end
    
    subgraph Processing & Estimation
        B -->|Combines Data with Historical Speed| C{Estimation Engine}
        C <-->|Fetches Live Traffic| D[Google Maps API]
    end
    
    subgraph End Users
        C -->|Classifies Buses: Most Likely / Less Likely| E[Passenger App]
        C -->|Updates Fleet Location & Demand| F[Owner & Govt Dashboard]
        
        E -->|Views ETA & Crowd Level| G((Passenger))
        F -->|Monitors Reports & Complaints| H((Admin / Authorities))
    end

    classDef default fill:#1e1e1e,stroke:#3b82f6,stroke-width:2px,color:#fff;
    classDef engine fill:#0f766e,stroke:#2dd4bf,stroke-width:2px,color:#fff;
    class C engine;
