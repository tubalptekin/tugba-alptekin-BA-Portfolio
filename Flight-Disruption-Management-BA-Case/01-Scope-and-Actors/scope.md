# ✈️ Flight Disruption Management – Scope Definition

## 🎯 Purpose
This analysis focuses on understanding and documenting the end-to-end process of **Flight Disruption Management**—one of the most critical operational and technical workflows in aviation.  
The goal is to identify how a delay event affects passengers, operational teams, systems, and airport processes, and to propose a clear, structured view of how information should flow between stakeholders.

This study is prepared **for learning and portfolio purposes** and is inspired by real-world aviation operations.

---

## 🔍 What This Analysis Covers (In Scope)

### 1) **Delay Detection & OCC Decision Flow**
- Delay identification (operational, technical, weather)
- OCC (Operations Control Center) evaluation and decision-making
- Creation of a new Estimated Time of Departure (ETD)

### 2) **Passenger Communication Workflow**
- Triggering notifications (SMS, push, email)
- Updating PNR & DCS
- Reflecting delay in mobile app and airport screens (FIDS)

### 3) **Re-Scheduling & Resource Re-Assignment**
- Crew duty impact (crew legality checks)
- Aircraft swap decision
- Gate changes and airport coordination

### 4) **Operational Systems Impact**
- Baggage Handling System (BHS) routing updates
- BRS (Baggage Reconciliation System) synchronization
- Flight status propagation across integrated systems

### 5) **Alternative Scenarios & Edge Cases**
- Multi-leg connections impacted by delay
- Knock-on delay risk on next sectors
- Crew timeout (duty exceed) scenarios
- Aircraft unavailability or last-minute defects
- Severe weather & airport operational constraints

---

## ❌ Out of Scope (Not Included)

### These topics are **not part of this analysis**:
- Fuel calculation details  
- Aircraft technical troubleshooting  
- Air Traffic Control (ATC) procedures  
- Commercial decisions (compensation, refunds)  
- Catering & in-flight service redesign  
- Safety-related regulatory documentation (EASA, ICAO standards)

These areas are highly specialized and not directly linked to BA functional analysis.

---

## 🧭 Assumptions

- Passenger communication is triggered by internal OCC systems.
- Data synchronization is performed through standard airline integrations (PNR, DCS, BRS, FIDS).
- All timelines shown in flows represent logical sequences, not actual operational SLA durations.
- The analysis assumes a single disrupted flight; multi-sector propagation will be included as an edge case.

---

## 📌 Summary
This scope defines the boundaries of the **Flight Disruption Management** process and identifies which systems, stakeholders, 
and operational flows will be analyzed. The goal is to bring clarity to a highly interconnected aviation workflow where a small delay can impact multiple downstream processes.

