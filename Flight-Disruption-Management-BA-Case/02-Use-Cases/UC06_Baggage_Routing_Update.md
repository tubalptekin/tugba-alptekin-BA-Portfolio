# ✈️ UC06 — Baggage Routing Update

## Purpose  
When a flight is delayed, moved to a different gate, or assigned a new aircraft, the baggage handling system (BHS) must update its routing logic.  
This ensures bags end up on the correct aircraft and prevents misloads or baggage delays.

---

## Primary Actor  
**Baggage Handling System (BHS)**

## Supporting Actors  
- BRS (Baggage Reconciliation System)  
- OCC (Operations Control Center)  
- Gate Management  
- Ground Handling / Ramp Teams  
- DCS (Departure Control System)  
- Central Operations System  

---

## Preconditions  
- Flight has experienced a disruption (delay, aircraft swap, or gate change).  
- New ETD, gate, or aircraft information is available.  
- Bag tags (barcodes) are already scanned into the system.

---

## Postconditions  
- All bags for the flight are routed according to the updated aircraft and gate details.  
- Ramp teams receive the latest load instructions.  
- BRS reflects accurate bag-to-passenger matching.

---

## Main Flow

1. OCC updates the flight details due to disruption (new ETD, new gate, or new aircraft).
2. Central Operations System publishes an update event.
3. BHS receives:
   - new gate number,  
   - new aircraft assignment (tail number),  
   - updated ETD.
4. BHS recalculates the routing path for bags already in the system.
5. System updates conveyor and sorting decisions so that all bags move toward the correct make-up point.
6. BRS aligns bag information with the new aircraft and passenger data.
7. Ground handling team receives updated loading instructions.
8. Ramp teams place bags on the correct aircraft according to the revised plan.
9. System logs all routing changes for traceability.

---

## Alternate Flows

### A1 — Bags Already Loaded on the Aircraft  
5a. If some bags were already loaded before the disruption:  
- Ramp team performs a partial unload.  
- BRS updates their new loading sequence.

### A2 — Gate Change After Bags Arrived at Previous Gate  
4a. Bags arrive at the old gate location:  
- Ramp team transfers bags manually to the new gate.  
- System marks transfer as “manual handling.”

### A3 — Missed Bag Detected  
6a. BRS finds that a bag hasn’t been scanned at any checkpoint:  
- System flags it for manual search.  
- Ground teams locate and route it properly.

---

## Exceptions

**E01 — BHS Routing Failure**  
System cannot calculate a new path → Bags diverted to holding area until manual routing is issued.

**E02 — Barcode Scanner Outage**  
Bag tag cannot be read → Manual entry required by staff.

**E03 — Aircraft Change Without Notice**  
If OCC updates aircraft but the message fails to reach BHS → Misrouting risk alert is triggered.

---

## Notes  
- Baggage systems operate on near real-time logic; even a small communication delay can create misloads.  
- Aircraft changes often require special baggage decisions (e.g., different cargo hold layout).  
- BRS is critical because aviation regulations forbid loading a bag if the passenger is not on board.

---

## Summary  
Baggage Routing Update ensures that every bag reaches the correct aircraft after a disruption.  
It maintains operational accuracy, prevents misloads, and keeps baggage and passenger data aligned across BHS, BRS, and ground teams.
