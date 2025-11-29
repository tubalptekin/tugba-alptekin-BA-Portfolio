<p align="center">
  <img src="images/Flight Disruption Management.png" alt="Flight Disruption Management Banner" style="border-radius: 8px;" width="70%">
</p>

# ✈️ Flight Disruption Management — Business Analysis Case Study
*A sector-focused project analyzing one of the most critical operational & technical processes in aviation: Flight Disruption Management.*

In aviation, even a **5-minute delay** can impact:
- hundreds of passengers,
- dozens of operational teams,
- real-time data systems,
- airport coordination,
- baggage routing,
- crew planning and aircraft assignments.

This project explores the **end-to-end flow** of managing flight delays from a **Business Analyst** perspective, including:

### 🔹 Passenger communication (SMS / Push / E-mail)
### 🔹 Flight re-scheduling & OCC decision making
### 🔹 Crew – aircraft – gate assignment logic
### 🔹 Baggage handling system impact (BHS / BRS)
### 🔹 Airport operations coordination
### 🔹 Alternative scenarios & edge cases

<br>

---

## 🗂 Project Overview

This diagram provides a one-glance summary of how flight delays propagate across operational units and how each system responds. It visually connects the key focus areas of this case study:

Delay Detection

OCC Decision Making

Passenger Notification & Rebooking

Gate & Airport Operations Adjustments

Crew, Aircraft & Ground Handling Updates

System-to-System Integration Points

<p align="center"> <img src="./images/project-overview.png" width="600"> </p>

## ✈️ High-Level Delay Handling Flow

This flow illustrates how a detected delay propagates across multiple operational domains  
(OCC, Passenger Systems, Airport Ops, and Operational Resources).

<p align="center">
  <img src="./images/disruption-parallel-flow.png" width="800">
</p>

---

## 🏗 High-Level Architecture (HLA)

The architecture below shows how operational systems interact  
when a delay update is published from the OCC.

<p align="center">
  <img src="./images/hla.png" width="850">
</p>


## 🎯 Objective

This case study aims to demonstrate how a Business Analyst approaches operational disruption,
evaluates system impact areas, and designs a structured solution to minimize passenger inconvenience,
operational cost, and cascading delays.
To demonstrate analytical thinking, system interaction understanding, and solution-oriented analysis for aviation operations — especially for teams like Turkish Airlines.

<br>

---

## 🖥 Sample UI Screens 
### 📱 Passenger Notification UI Mockup

Below is a sample passenger-facing UI that demonstrates how a delay update is communicated via mobile push notifications and SMS channels.

<p align="center">
  <img src="images/flight-notification-ui.png" width="650">
</p>

### 🛫 Passenger Rebooking UI 
This screen shows how passengers can view available alternative flights, accept rebooking offers, or request compensation depending on regulations.

<p align="center">
  <img src="images/flight-rebooking-ui.png" width="650">
</p>

---

## 🔄 System Interaction Overview  
A visual map showing how OCC, Airport Ops, Passenger Systems, Crew Operations, and BHS interact during a disruption.

<p align="center">
  <img src="./images/system-interaction-diagram.png" width="650">
</p>

*Full version available in:* **`05-System-Interaction-Diagram`**

## 🛡 Risks & Mitigation Matrix

Flight delays impact multiple operational and passenger-facing systems.
This matrix summarizes the key risks identified in the analysis and the mitigation strategies designed to reduce disruption impact.

<p align="center"> <a href="./06-Risks-Mitigation-Matrix/README.md"> <img src="images/risk-matrix-preview.png" width="400" alt="Risk & Mitigation Matrix Preview"> </a> </p>

*➡️ Click the image to view the full matrix.*

## 📌 Scope

This analysis covers:
- Delay propagation and operational impact
- Passenger-facing updates and notification logic
- Gate, crew, and aircraft assignment impacts
- System-to-system communication during disruption

## 🚫 Out of Scope

This analysis does ***not*** cover:
- Airline pricing logic
- Maintenance delay root-cause analysis
- Weather forecasting systems

## 📚 Key Insights

- Even small delays create multi-system ripple effects (PNR, FIDS, Gate Ops, Crew legality).
- A structured notification + resource recalculation strategy reduces passenger frustration.
- Standardizing disruption-handling events improves OCC efficiency and reduces operational risk.


### 🔮 Future Enhancements

This case study can be expanded with additional Business Analysis deliverables and more advanced operational scenarios.
Below are potential next steps that would further strengthen the model:

**1️⃣ Predictive Delay Modeling (ETA Forecasting)**

Integrate machine learning–based ETA predictions using historical flight, weather, crew, and airport capacity data.
This would help OCC anticipate disruptions before they occur.

**2️⃣ Passenger Segmentation for Personalized Experience**

Design logic for:

high-value / connecting passengers,

special service passengers (SPML, PRM),

group travelers,

corporate travel accounts.

Each segment would receive tailored rebooking options and notification rules.

**3️⃣ Automated Crew Legality Assessment Rules**

Model detailed FTL rules (flight time limitations) and integrate decision logic for:

illegal crew cases,

reserve crew assignment,

split duty impacts.

Improves realism for operational-resource flows.

**4️⃣ Event-Driven Architecture Upgrade**

Replace batch triggers with an event-driven disruption pipeline, using:

Kafka (or MQ),

change-data-capture streams,

real-time fan-out to OCC, PSS, BHS, and FIDS.

Reduces latency and improves system resilience.

**5️⃣ SCENARIOS: Edge Case Library**

Add diagrams & use cases for operational edge cases such as:

aircraft swap,

last-minute gate change,

crew sickness,

misconnected passengers,

diversion handling,

irregular operations (IRROPS).

**6️⃣ KPI Dashboard Mockups**

Design dashboards to track:

delay propagation timeline,

passenger rebooking funnel,

crew legality violation counts,

missed connections,

AHT (average handling time) for OCC decisions.

Shows BA skill in business intelligence and reporting.


## 📁 Project Structure (This folder will include)
01-Scope-and-Actors

02-Use-Cases

03-Process-Flows

04-UserStories-AcceptanceCriteria

05-System-Interaction-Diagram

06-Risks-and-Mitigation


Each section will be added step-by-step with diagrams, flows, use cases, and acceptance criteria.

---

## ✨ Author
***Tuğba Alptekin***
Junior Business Analyst | MIS Graduate  
Focused on Aviation, Technology, and Process Optimization  
