<p align="center">
  English · <a href="#">বাংলা</a>
</p>

<h1 align="center">Pothe: A Smart Public Transport Tracking and Demand Prediction System</h1>

<p align="center">
  <strong>One ecosystem for human-assisted bus tracking, arrival prediction, and route demand analytics.</strong><br>
  See exactly where your bus is, how crowded it is, and when it will arrive.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-PWA-blue.svg" alt="React">
  <img src="https://img.shields.io/badge/Node.js-Express-green.svg" alt="Node.js">
  <img src="https://img.shields.io/badge/PostgreSQL-PostGIS-336791.svg" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/Testing-Jest_%7C_Cypress-lightgrey.svg" alt="Testing">
  <img src="https://img.shields.io/badge/license-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/badge/Status-Capstone_Project-success.svg" alt="Status">
</p>

<p align="center">
  <a href="#-the-problem">The Problem</a> · 
  <a href="#-project-overview">Overview</a> · 
  <a href="#-how-pothe-works">How it Works</a> · 
  <a href="#-key-features-by-user-role">Features</a> · 
  <a href="#-tech-stack">Tech Stack</a> · 
  <a href="#-future-scope">Future Scope</a>
</p>

> [!IMPORTANT]  
> This project is developed as a System Analysis & Design Capstone Project (SE 231) for Daffodil International University. 

---

## 🚨 The Problem

Public bus users, owners, and government policymakers currently face major challenges:
* **Unknown Bus Location & Crowding:** Passengers lose time waiting without knowing when buses will arrive or how crowded they are.
* **Limited Visibility for Owners:** Traditional GPS hardware is too expensive for small local bus operators, leaving them blind to their fleet's location and load.
* **No Accountability:** Passengers have no structured channel to report misbehavior by bus staff or inaccuracies.
* **Lack of Data for Policymakers:** Decisions about bus and route allocations rely on guesswork because passenger demand per route is not statistically recorded.

## 📖 Project Overview

"Pothe" (“পথে”) solves these issues without requiring GPS devices on every bus. It is a smart public transport tracking and demand prediction system built around an ecosystem of human checkers and general passengers. 

By placing checkers at fixed checkpoints to input passenger counts, the system combines this trusted data with historical speeds and live Google Maps traffic to estimate current bus positions. The entire interface is bilingual, fully supporting both **Bangla and English**.

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
