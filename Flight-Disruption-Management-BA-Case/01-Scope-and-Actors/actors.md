# ✈️ Actors in Flight Disruption Management

This section outlines all operational, technical, and customer-facing actors involved in managing a flight disruption scenario.  
Each actor plays a crucial role in ensuring that delays are handled efficiently across the aviation ecosystem.

---

## 👨‍✈️ 1. Operations Control Center (OCC)
The central decision-making unit responsible for evaluating disruptions, determining the new Estimated Time of Departure (ETD), coordinating with airport teams, and triggering communication workflows.  
**Key responsibilities include:** delay validation, resource re-allocation, aircraft and crew decisions.

---

## 🧑‍✈️ 2. Crew Planning & Crew Control
The department responsible for managing pilot and cabin crew assignments.  
Flight delays may cause:
- crew legality issues (duty time exceeding limits),
- standby crew activation,
- reassignment to another aircraft or flight.

---

## ✈️ 3. Aircraft Operations / Fleet Management
Handles aircraft rotation, maintenance planning, and aircraft swap decisions.  
A delay in one sector can impact the aircraft’s next scheduled flights, causing a chain reaction across the network.

---

## 🚪 4. Airport Gate & Ground Handling Teams
Includes gate agents, ramp agents, load control, and ground service providers.  
They manage:
- gate changes,
- boarding operations,
- baggage loading/unloading,
- communication with passengers at the airport.

---

## 🎒 5. Baggage Handling System (BHS) & BRS
BHS routes bags through conveyors and sorting systems.  
BRS (Baggage Reconciliation System) ensures bags are matched with boarding passengers.  
A delay or gate change triggers updates in routing logic.

---

## 📱 6. Passenger & Notification Systems
Systems responsible for sending:
- push notifications (mobile app),
- SMS messages,
- email alerts.

They receive updated ETD and flight status from OCC through internal APIs or event-driven notifications.

---

## 🧳 7. Passengers
End users affected by any schedule change.  
Passenger experience depends on timely information, accurate ETD updates, and clear instructions during disruptions.

---

## 🛫 8. Airport Operations / ATC Coordination (High-Level)
Although not deeply modeled in this case, airport ops teams:
- approve gate allocation changes,
- coordinate ground movements,
- manage airport capacity constraints.

ATC is not part of this BA analysis but indirectly influences timing decisions.

---

## 💻 9. Integrated Airline Systems
These internal systems receive flight updates through structured data flows:

### 🔸 PNR System  
Handles reservation data, passenger details, contact info, and ticket status.

### 🔸 DCS (Departure Control System)  
Primary system for check-in, boarding, load control, and flight closure.

### 🔸 FIDS (Flight Information Display System)  
Displays real-time flight updates at the airport.

### 🔸 Mobile App & Website  
Reflect new ETD instantly for passenger visibility.

### 🔸 Internal APIs & Message Brokers  
Ensure synchronization between OCC, PNR, DCS, BRS, BHS and notification services.

---

## 📌 Summary
These actors together form the core operational ecosystem of a flight disruption scenario.  
A change initiated by OCC must propagate consistently across **multiple teams and systems**, making this one of the most interconnected workflows in the aviation industry.

