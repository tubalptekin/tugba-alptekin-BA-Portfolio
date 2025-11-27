# ✈️ UC04 — Aircraft Reassignment

## 🎯 Goal
To assign a new aircraft to a delayed flight when the original aircraft becomes unavailable due to rotation conflicts, maintenance requirements, technical issues, or downstream scheduling constraints.

---

## 👥 Primary Actor
**Fleet Management / Aircraft Operations**

## 🧩 Supporting Actors
- OCC (Operations Control Center)
- Maintenance Control Center (MCC)
- Gate Management
- BHS / BRS Systems
- Central Operations System
- Cabin & Cockpit Crew Planning
- DCS & PNR Systems

---

## 🔧 Preconditions
- The flight has an existing assigned aircraft.
- Updated ETD (via UC02) causes a conflict or aircraft becomes unavailable.
- Aircraft configuration and type requirements are known.

---

## 🔚 Postconditions
- A new aircraft is assigned to the disrupted flight.
- All dependent systems (crew assignments, gate, baggage routing, DCS, OCC) receive updated aircraft information.
- Original aircraft is released or reassigned.

---

## 🔄 Main Flow

1. OCC updates ETD for the delayed flight.
2. System checks aircraft rotation impact for the next scheduled flights.
3. System identifies a rotation conflict or aircraft unavailability.
4. Fleet Management receives an automatic alert.
5. Fleet Management evaluates alternative aircraft options:
   - same aircraft type  
   - compatible seating configuration  
   - available at the airport  
   - meets maintenance requirements  
6. Fleet selects an alternative aircraft.
7. System validates:
   - aircraft type/code compatibility  
   - maintenance status (MEL limitations)  
   - fueling requirements  
   - availability window  
8. System assigns the new aircraft to the flight.
9. Crew Planning recalculates if pilot type rating matches the new aircraft.
10. Gate Management evaluates if the new aircraft requires a gate change.
11. BHS routing logic updates baggage-to-aircraft mapping.
12. DCS and PNR systems update aircraft tail number and configuration.
13. OCC receives final confirmation that aircraft swap is completed.

---

## 🔀 Alternate Flows

### A1 — No Suitable Replacement Aircraft Available
5a. No aircraft matches type or configuration.  
→ System recommends delaying further or cancelling the flight.  
→ OCC escalates decision to management.

### A2 — Replacement Aircraft Requires Gate Change
10a. Assigned gate incompatible (e.g., narrowbody vs. widebody).  
→ System triggers **UC05 — Gate Change**.

### A3 — Crew Type Rating Mismatch
9a. Assigned crew cannot operate new aircraft type.  
→ Triggers **UC03 — Crew Reassignment**.

### A4 — Maintenance Holds the Aircraft
7a. Aircraft has open maintenance items.  
→ System blocks assignment and selects next available candidate.

---

## ❌ Exceptions

**E01 — Incomplete Aircraft Data**  
Missing seating configuration or type code. Assignment blocked.

**E02 — Double Assignment Conflict**  
Candidate aircraft already planned for another flight. System prevents duplication.

**E03 — Fueling/De-icing Delay**  
Aircraft requires additional turnaround time exceeding ETD. System alerts OCC.

---

## 📌 Notes
- Aircraft swaps are used to prevent knock-on delays across the entire flight network.  
- Widebody vs. narrowbody compatibility greatly affects gate and baggage operations.  
- Cabin configuration (e.g., business/economy mix) must match booked passenger load.

---

## 📝 Summary
Aircraft reassignment minimizes network-wide disruption by reallocating a suitable aircraft when the original is no longer viable.  
This use case ensures alignment between fleet, crew, ground handling, and passenger systems, making it a core component of disruption management.
