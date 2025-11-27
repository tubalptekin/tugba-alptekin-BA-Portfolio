# ✈️ UC03 — Crew Reassignment

## 🎯 Goal
To ensure operational continuity by assigning a new pilot and/or cabin crew team when the original crew becomes unavailable due to legality constraints, duty time limits, medical issues, or rotation conflicts resulting from a flight delay.

---

## 👥 Primary Actor
**Crew Control / Crew Planning**

## 🧩 Supporting Actors
- OCC (Operations Control Center)
- Central Operations System
- Crew Legality Engine (Duty Time Calculator)
- Mobile App / Crew Portal
- Aircraft Assignment System
- HR / Standby Crew Pool

---

## 🔧 Preconditions
- Flight has been delayed and updated ETD is known.
- Initial crew assignment exists in the system.
- Crew duty legality must be checked before flight operation continues.

---

## 🔚 Postconditions
- A new crew is assigned (fully or partially).
- Updated crew data is synchronized with the Central Operations System, DCS, and OCC.
- Original crew is released or reassigned.

---

## 🔄 Main Flow

1. OCC updates the flight’s ETD (via UC02).
2. Crew Legality Engine recalculates crew duty times based on the new schedule.
3. System detects that one or more crew members will exceed duty time limits.
4. Crew Control is alerted through the Crew Portal.
5. Crew Control selects one of the following actions:
   - Assign full standby crew  
   - Replace only the pilot(s)  
   - Replace only cabin crew  
   - Mix standby + available crew from nearby rotations
6. Crew Control confirms new crew assignment.
7. System validates:
   - Crew certifications  
   - Aircraft type rating  
   - Required cockpit + cabin composition  
   - Crew availability & rest requirements
8. System updates the flight roster with new crew.
9. DCS and OCC receive updated crew information.
10. New crew receives a digital duty notification via mobile app.
11. Original crew is marked as “released” or reassigned.

---

## 🔀 Alternate Flows

### A1 — No Standby Crew Available
5a. Standby crew pool is empty.  
→ System suggests cross-utilization from nearest arriving flights.  
→ Crew Control manually selects replacements.

### A2 — Crew Certification Mismatch
7a. Replacement crew does not have the correct license or aircraft type rating.  
→ System blocks the assignment.  
→ Crew Control must select another eligible crew.

### A3 — Partial Replacement
5b. Only 1 pilot or only 1 cabin crew is replaced.  
→ System ensures minimum crew composition rules are respected.

### A4 — Last-Minute Crew Unavailability
Before new ETD, a crew member reports sick.  
→ Emergency crew reassignment is triggered following the same flow.

---

## ❌ Exceptions

**E01 — Legality Engine Failure**  
If legality cannot be calculated, system stops assignment and alerts OCC.

**E02 — Data Synchronization Error**  
Crew roster cannot be pushed to DCS/OCC.  
System retries 3 times, then escalates.

**E03 — Duplicate Assignment**  
Crew already assigned to another flight. System prevents double-booking.

---

## 📌 Notes
- Crew legality calculation must comply with national and international regulations (EASA, SHGM).  
- Standby crew pools differ by airport and time of day.  
- Cockpit and cabin roles must meet minimum composition requirements.

---

## 📝 Summary
Crew reassignment ensures that delayed flights continue safely and legally by reallocating qualified crew members. Coordinating legality, availability, and certifications makes this one of the most complex workflows in flight disruption management.
