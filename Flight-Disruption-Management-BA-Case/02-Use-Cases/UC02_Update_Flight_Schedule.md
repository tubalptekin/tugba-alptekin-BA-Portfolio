# ✈️ UC02 — Update Flight Schedule

## 🎯 Goal
To update the flight’s operational timeline by setting a new Estimated Time of Departure (ETD) after a disruption is confirmed, ensuring all dependent systems and operational units receive the updated schedule.

---

## 👥 Primary Actor
**Operations Control Center (OCC)**

## 🧩 Supporting Actors
- Crew Planning System
- Aircraft Assignment / Fleet Management System
- Gate Management System
- PNR System
- DCS (Departure Control System)
- Airport FIDS
- Mobile App / Website
- Internal Message Broker / Event System

---

## 🔧 Preconditions
- Flight delay has been confirmed by OCC.
- Root cause of delay is identified (technical, operational, weather, etc.).
- Operational constraints (crew legality, aircraft availability) have been assessed.

---

## 🔚 Postconditions
- Flight has a new ETD stored in the operations system.
- New ETD is propagated to all integrated systems (PNR, DCS, FIDS, internal APIs).
- Resource recalculation (crew, aircraft, gate) may be triggered automatically or manually.

---

## 🔄 Main Flow

1. OCC confirms that the flight is delayed.
2. OCC selects the new ETD based on operational assessment.
3. OCC updates ETD in the **Central Operations System**.
4. System validates the ETD (must be in the future, comply with airport slots).
5. System publishes a **Flight Schedule Update Event**.
6. Crew Planning receives the new ETD and recalculates crew legality.
7. Fleet Management recalculates aircraft rotation impact.
8. Gate Management checks gate availability & updates assignment if required.
9. PNR & DCS receive the new ETD and update:
   - passenger itinerary,
   - check-in counters,
   - boarding times.
10. FIDS updates airport screens with the new timing.
11. Mobile App & Website display the updated ETD.
12. All changes are logged for audit purposes.

---

## 🔀 Alternate Flows

### A1 — Crew Duty Violation Detected
6a. Crew Planning identifies that crew duty time will exceed limits.  
→ Crew Control initiates crew change process.  
→ System triggers **UC03 — Crew Reassignment**.

### A2 — Aircraft Rotation Conflict
7a. New ETD impacts next flight of the aircraft.  
→ Fleet Management evaluates aircraft swap.  
→ System triggers **UC04 — Aircraft Reassignment**.

### A3 — Gate Conflict at the Updated ETD
8a. Gate is unavailable at new ETD.  
→ Gate Management searches for an alternative gate.  
→ System triggers **UC05 — Gate Change**.

### A4 — PNR or DCS Not Reachable
9a. One of the systems fails to receive ETD.  
→ System retries 3 times.  
→ After failure, alerts OCC to manual intervention.

---

## ❌ Exceptions

**E01 — Invalid ETD**  
ETD is earlier than current time or violates airport slot restrictions. System rejects the update.

**E02 — Overlapping Events**  
Multiple delay updates sent too close in time may cause conflict. System merges events with idempotency.

**E03 — Missing Required Data**  
If no crew or aircraft assignment exists, system blocks update and requests OCC to resolve dependencies first.

---

## 📌 Notes
- Updating ETD is one of the most sensitive operations in aviation; all systems must remain synchronized.  
- Crew legality check is mandatory before finalizing ETD.  
- Airport operational rules (slot times, night restrictions, ground service windows) may restrict ETD options.

---

## 📝 Summary
This use case manages the end-to-end workflow of updating a flight schedule after a disruption.  
It coordinates multiple critical systems — crew, aircraft, gate, PNR, DCS, airport displays — ensuring operational consistency across the airline network.
