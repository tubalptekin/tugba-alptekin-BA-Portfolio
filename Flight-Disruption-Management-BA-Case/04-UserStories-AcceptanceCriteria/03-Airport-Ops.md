# 🛫 Airport Operations — User Stories & Acceptance Criteria

Bu bölüm, havaalanı operasyon ekiplerinin gecikme sonrası aldığı aksiyonları kapsamaktadır.

## ✔️ User Story 1 — Gate Conflict Check

As an Airport Operations Officer,

I want the system to automatically detect gate conflicts caused by a delay,

so that I can prevent gate overlaps and ensure smooth airport traffic flow.

**Acceptance Criteria (Gherkin)**

Scenario: Gate conflict detection

  Given a flight receives a new ETD
  
  When the system checks the airport gate schedule
  
  Then it should identify whether the assigned gate is still available
  
  And flag conflicts with arriving or departing flights

## ✔️ User Story 2 — Update Gate Assignment

As an Airport Operations Officer,

I want the system to recommend a new gate if the delay causes a conflict,

so that gate changes can be made quickly and safely.

**Acceptance Criteria (Gherkin)**

Scenario: Gate reassignment

  Given a gate conflict is detected
  
  When the system suggests available gates
  
  Then I should be able to select and confirm a new gate
  
  And the system should notify all dependent systems (FIDS, OCC, Ramp)

## ✔️ User Story 3 — FIDS (Flight Info Display System) Update

As an Airport Operations Officer,

I want FIDS screens to automatically update after a delay,

so that passengers at the airport always see accurate information.


**Acceptance Criteria (Gherkin)**

Scenario: FIDS updates after delay

  Given a delay event is published
  
  When the FIDS system receives the update
  
  Then airport screens should refresh with:
  
      - new ETD
      - gate change (if any)
      - delay reason (if shared)

## ✔️ User Story 4 — Notify Gate Staff & Ground Handling

As an Airport Duty Manager,

I want gate staff, boarding agents, and ground handling teams to be automatically notified of delays,

so that they can adjust their workflow accordingly.

**Acceptance Criteria (Gherkin)**

Scenario: Ops teams notified

  Given the OCC publishes a delay event
  
  When the airport operational system receives the event
  
  Then the system should notify:
  
      - Gate agents
      - Boarding staff
      - Ramp & ground handling
      - Pushback & towing team
      
  And notifications should include updated ETD and gate information

## ✔️ User Story 5 — Passenger Flow Impact Analysis

As an Airport Operations Officer,

I want to see how the delay affects passenger flow in the terminal,

so that I can proactively manage congestion at gates, security, and shuttle points.


**Acceptance Criteria (Gherkin)**

Scenario: Terminal impact shown

  Given the delay is confirmed
  
  When the airport system runs flow analysis
  
  Then it should highlight:
  
      - expected crowding areas
      - connecting passenger congestion
      - required staffing adjustments

## ✔️ User Story 6 — Stand Allocation (Apron Stand)

As an Apron Operations Officer,

I want the system to recalculate stand usage after delays,

so that apron availability remains conflict-free.

**Acceptance Criteria (Gherkin)**

Scenario: Stand allocation recalculation

  Given a delayed aircraft remains parked longer than scheduled
  
  When apron systems receive a delay update
  
  Then the system should check stand occupancy
  
  And recommend alternatives if the stand is required for another flight

## ✔️ User Story 7 — Boarding Process Freeze/Resume

As a Gate Agent,

I want the boarding process to be frozen or resumed depending on updated ETD,

so that gate operations remain in sync with OCC decisions.

**Acceptance Criteria (Gherkin)**

Scenario: Boarding freeze/resume

  Given the flight is delayed before boarding starts
  
  When OCC sets a new ETD
  
  Then boarding should remain frozen
  
  And once OCC confirms readiness, boarding should resume
  
