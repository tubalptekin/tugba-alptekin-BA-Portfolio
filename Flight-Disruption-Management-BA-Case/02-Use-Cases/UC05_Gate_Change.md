# ✈️ UC05 — Gate Change

## Purpose  
When a flight is delayed or reassigned to a different aircraft, the originally planned gate may no longer be suitable.  
This use case explains how the gate is changed and how this update flows to all relevant teams and systems.

---

## Primary Actor  
**Gate Management Team**

## Supporting Actors  
- OCC (Operations Control Center)  
- Fleet / Aircraft Operations  
- Ground Handling & Ramp  
- DCS (Departure Control System)  
- Airport FIDS  
- Passenger Notification System  
- BHS/BRS systems (indirect)  

---

## Preconditions  
- Flight has an updated ETD *or* a new aircraft assigned.  
- Current gate is either unavailable, unsuitable (wrong size), or creates a scheduling conflict.  

---

## Postconditions  
- A new gate is assigned and visible in all operational systems.  
- Passengers and airport teams receive updated information.  
- Baggage and ramp teams adjust their workflows accordingly.

---

## Main Flow

1. OCC updates the flight schedule (delay or aircraft change).
2. System checks whether the current gate still works for the new situation.
3. If conflict exists, Gate Management receives an automatic alert.
4. Gate Management searches for an available and suitable gate.
5. A new gate is selected and confirmed.
6. System updates the gate information in:
   - Central Operations System  
   - DCS  
   - Airport FIDS  
   - Mobile app & website  
7. Passenger communication system sends a gate-change notification.
8. Ramp and ground handling teams prepare equipment for the new gate.
9. The previous gate is released for other flights.

---

## Alternate Flows

### A1 — No Suitable Gate Available  
5a. If no suitable gate is free at the new ETD:  
- System suggests remote stand as fallback.  
- Ground handling teams prepare buses accordingly.

### A2 — Multiple Gate Conflicts  
2a. If the new aircraft type requires a widebody gate:  
- Narrowbody gates are filtered out automatically.  

### A3 — Last-Minute Gate Change  
7a. If gate changes shortly before boarding:  
- System triggers “urgent” notification type.  
- Airport staff guide passengers to the new location.

---

## Exceptions

**E01 — FIDS Not Updating**  
Airport display system does not reflect the change → System retries and logs a warning.

**E02 — DCS Sync Delay**  
Boarding system still shows the old gate → Manual update required by ground staff.

**E03 — Gate Incompatibility Detected Late**  
A physical mismatch (bridge height, aircraft size) is detected → Immediate reassignment triggered.

---

## Notes  
- Gate changes are extremely sensitive because they directly affect passenger flow inside the terminal.  
- Widebody aircraft can only be assigned to specific gate types.  
- Any gate change must be synchronized quickly to avoid confusion at the airport.

---

## Summary  
Gate Change ensures that a delayed or reassigned flight is moved to a suitable gate, and that all airport systems and passengers are informed in time.  
It’s one of the most frequent operational adjustments during flight disruptions.
