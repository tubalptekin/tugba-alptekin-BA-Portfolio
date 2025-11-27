# ✈️ UC01 — Publish Delay Notification

## 🎯 Goal
To notify all affected passengers and systems about a confirmed flight delay by sending real-time updates through SMS, push notifications, email, airport screens, and reservation systems.

---

## 👥 Primary Actor
**Operations Control Center (OCC)**

## 🧩 Supporting Actors
- Passenger Notification Service (Push/SMS/Email)
- PNR System
- DCS (Departure Control System)
- FIDS (Flight Information Display System)
- Mobile App / Website
- Passengers

---

## 🔧 Preconditions
- OCC has validated the delay reason (operational/technical/weather).
- New ETD (Estimated Time of Departure) has been determined.
- Passenger contact information exists in the PNR.

---

## 🔚 Postconditions
- Passengers receive updated ETD information via multiple channels.
- PNR, DCS, and mobile systems reflect the new flight time.
- Airport FIDS displays the delay information.

---

## 🔄 Main Flow

1. OCC identifies and confirms the flight delay.
2. OCC updates the new ETD in the internal operations system.
3. System triggers the **Delay Notification Event**.
4. Notification Service retrieves passenger contact data from the PNR.
5. System sends:
   - SMS  
   - Mobile push notifications  
   - Email alerts  
6. Airport FIDS receives and displays the updated ETD.
7. Mobile app and website refresh the flight status.
8. Passenger sees the notification and updated flight information.

---

## 🔀 Alternate Flow

### A1 — Missing Contact Information
4a. If a passenger has no valid contact channel  
→ Only airport FIDS and mobile app will reflect the delay.

### A2 — Notification Service Failure
5a. If push or SMS service fails,  
→ System retries 3 times.  
→ If still failing, an alert is logged for OCC review.

### A3 — Late ETD Change (Multiple Updates)
2a. If ETD changes again after notification is sent  
→ System triggers a second notification labeled as “Updated Delay”.

---

## ❌ Exceptions

**E01 — Invalid ETD**  
System rejects invalid or past timestamps. OCC must correct the entry.

**E02 — Duplicate Notification Event**  
System detects duplicate events and prevents double-notification (idempotency).

---

## 📌 Notes
- Passenger communication must be consistent across all channels.
- Mobile app should refresh automatically without page reload.
- All notifications must include: flight number, old ETD, new ETD, and cause (if available).

---

## 📝 Summary
This use case ensures that passengers and all integrated airline systems receive timely, accurate delay information across multiple channels. It is critical for minimizing passenger frustration and operational confusion during disruption events.
