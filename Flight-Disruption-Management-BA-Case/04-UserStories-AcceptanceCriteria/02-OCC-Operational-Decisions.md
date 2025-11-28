# 🛫 User Stories — OCC Operational Decisions

OCC’nin (Operations Control Center) gecikme sonrası aldığı teknik ve operasyonel kararları kapsar.

## ✔️ User Story 1 — OCC Evaluates Delay Impact

As an OCC controller,

I want to evaluate the root cause and scope of a delay,

so that I can decide the appropriate operational response.

**✅ Acceptance Criteria (Gherkin)**

Scenario: OCC evaluates the delay

  Given a delay notification is received from the airport or crew
  
  When the OCC controller views the operational dashboard
  
  Then the system should display aircraft status, crew status, and previous rotations
  
  And highlight potential conflicts (crew legality, gate conflict, aircraft availability)
  

## ✔️ User Story 2 — Set New ETD (Estimated Time of Departure)

As an OCC controller,

I want to set a revised ETD,

so that downstream systems receive the correct operational timeline.


**Acceptance Criteria (Gherkin)**

Scenario: OCC sets revised ETD

  Given the OCC has completed the delay assessment
  
  When the controller enters a new ETD value
  
  Then the system should validate ETD against aircraft readiness and crew legality
  
  And publish the new ETD as an operational event

## ✔️ User Story 3 — Trigger Gate Re-Evaluation

As an OCC controller,

I want the system to automatically check whether the assigned gate is still available,

so that conflicts are prevented during peak hours.


**Acceptance Criteria (Gherkin)**

Scenario: System checks gate conflict

  Given the flight has been delayed beyond a threshold
  
  When the OCC sets a new ETD
  
  Then the system should check if the current gate remains available
  
  And flag if another departing/arriving flight will use that gate
  

## ✔️ User Story 4 — Publish Delay Event to All Systems

As an OCC controller,

I want the delay update to immediately notify all connected systems,

so that every operational unit receives synchronized information.


**Acceptance Criteria (Gherkin)**

Scenario: Delay event published to all systems

  Given the OCC has confirmed the delay and new ETD
  
  When the delay update is submitted
  
  Then the system should publish a structured event to:
  
      | FIDS               |
      
      | Passenger System   |
      
      | Baggage System     |
      
      | Crew Management    |
      
      | Ground Ops         |
      
      | Airport Authority  |
      
  And all subscribing systems should update their internal timelines

 ## ✔️ User Story 5 — Recalculate Aircraft Rotation Impact

As an OCC controller,

I want the system to show how the delay affects the aircraft’s next flights,

so that I can proactively adjust future rotations.

**Acceptance Criteria (Gherkin)**

Scenario: Rotation impact calculated

  Given the current flight has a confirmed delay
  
  When the OCC opens the rotation impact module
  
  Then the system should show the following for the next flights:
  
      - planned departure/arrival times
      - expected updated times
      - conflicts due to turn-around constraints

## ✔️ User Story 6 — Recalculate Crew Legality

As an OCC controller,

I want the system to alert me when a delay causes the crew to exceed duty limits,

so that I can arrange crew replacement before disruption worsens.


**Acceptance Criteria (Gherkin)**

Scenario: Crew legality recalculated

  Given the flight delay affects crew duty time
  
  When the system recalculates legality
  
  Then it should indicate:
  
      - if crew remains legal
      
      - if replacement is required
      
      - time remaining before exceeding duty limit
      

## ✔️ User Story 7 — Approve Rebooking Eligibility

As an OCC controller,

I want to enable or disable rebooking eligibility based on delay conditions,

so that passenger operations follow the correct rules.


**Acceptance Criteria (Gherkin)**

Scenario: OCC enables rebooking

  Given the delay exceeds the rebooking threshold
  
  When the OCC enables rebooking for this flight
  
  Then the system should notify the passenger system
  
  And rebooking options should become available
  
