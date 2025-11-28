# 🔄 System Interaction Diagram  
This diagram shows how OCC, Passenger Systems, Airport Operations, Crew Systems, and Baggage/Ramp Systems exchange real-time information during a flight delay event.

<p align="center">
  <img src="Flight-Disruption-Management-BA-Case/images/system-interaction-diagram.png" width="850">
</p>

## What This Diagram Represents
- Event-driven communication after a delay update  
- OCC as the main decision source  
- Updates published to Passenger, Airport, Crew, and Baggage systems  
- Real-time feedback loops (gate conflicts, crew legality, aircraft rotation)

## Why It Matters (BA Perspective)
A Business Analyst must understand:
- Which systems are **upstream** and **downstream**
- Which data elements are exchanged (flight status, ETD, gate, crew legality status, rotation impacts)
- How events trigger operational decisions
- Which systems must remain synchronized to avoid cascading problems
