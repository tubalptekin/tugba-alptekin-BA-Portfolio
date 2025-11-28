# 🛠 Operational Resources — User Stories & AC

Aşağıdaki user story’ler havayolunun “arka sahne” dediğimiz teknik ekipleri için hazırlanmıştır.

## ✔️ User Story 1 — Crew Legality Recalculation

As a Crew Controller,

I want the system to automatically recalculate crew duty time after a delay,

so that I can identify whether the assigned crew is still legally allowed to operate the flight.


**Acceptance Criteria (Gherkin)**

Scenario: Crew legality checked after delay

  Given the flight receives a new ETD
  
  When the system recalculates crew duty time
  
  Then it should determine whether the crew remains legal
  
  And show remaining duty time
  
  And flag if replacement crew is required

## ✔️ User Story 2 — Assign Replacement Crew if Required

As a Crew Controller,

I want to see replacement crew options when the assigned team becomes illegal,

so that I can maintain flight continuity.

**Acceptance Criteria (Gherkin)**

Scenario: Replacement crew suggested

  Given the assigned crew becomes illegal due to delay
  
  When the system runs eligibility checks
  
  Then it should display available standby crew
  
  And show their certifications, rest status, and locations
  
  And allow the controller to assign them

## ✔️ User Story 3 — Aircraft Rotation Impact Check

As a Fleet Manager,

I want the system to show how a delay affects the aircraft’s next flights,

so that I can proactively adjust future schedules.

**Acceptance Criteria (Gherkin)**

Scenario: Rotation impact displayed

  Given an aircraft is delayed
  
  When the system analyzes downstream rotations
  
  Then it should display:
  
      - scheduled next leg
      - expected updated times
      - conflicts with turn-around constraints

## ✔️ User Story 4 — Reassign Aircraft if Needed (Swap)

As a Fleet Manager,

I want the system to recommend a suitable replacement aircraft,

so that the delay does not cause cascading disruptions.

**Acceptance Criteria (Gherkin)**

Scenario: Replacement aircraft recommended

  Given the current aircraft causes rotation conflicts
  
  When the system analyzes fleet availability
  
  Then it should show alternative aircraft options
  
  And validate:
  
      - aircraft type compatibility
      - maintenance status
      - location
      - turnaround feasibility

## ✔️ User Story 5 — Ramp Operations Update

As a Ramp Operations Supervisor,

I want to receive updated ETD and aircraft/gate updates,

so that ground teams can adjust servicing plans.

**Acceptance Criteria (Gherkin)**

Scenario: Ramp operations notified

  Given the aircraft is delayed or swapped
  
  When the OCC publishes updated details
  
  Then ramp teams should receive:
  
      - new gate
      - new ETD
      - aircraft tail number
      - baggage loading/unloading updates

## ✔️ User Story 6 — Baggage Routing Update (BHS/BRS)

As a Baggage System Operator,

I want the baggage routing logic to update automatically after a delay,

so that bags are not misrouted or delayed.


**Acceptance Criteria (Gherkin)**

Scenario: Baggage routing updated

  Given the flight’s ETD changes
  
  When the BHS system receives updated operational data
  
  Then it should reroute all in-system bags
  
  And adjust conveyor timing
  
  And notify ramp staff if manual transfer is required
  

## ✔️ User Story 7 — Catering, Fueling & Service Adjustments

As a Ground Service Coordinator,

I want fueling, catering, and cleaning schedules to adjust based on the new ETD,

so that service teams are neither too early nor too late.


**Acceptance Criteria (Gherkin)**

Scenario: Service schedule updated

  Given the aircraft is delayed
  
  When the operational service scheduler receives updated ETD
  
  Then it should adjust:
  
      - fueling time
      - catering delivery
      - cleaning schedule
  And notify relevant vendors

## ✔️ User Story 8 — Final Operational Readiness Confirmation

As an OCC Controller,

I want to see a summary that confirms crew, aircraft, gate, ramp, and baggage workflows are aligned,

so that I can declare the flight “ready for operation”.


**Acceptance Criteria (Gherkin)**

Scenario: Operational readiness shown

  Given all impacted teams have acknowledged updated data
  
  When the OCC opens the readiness dashboard
  
  Then the system should show:
  
      - crew confirmed
      - aircraft ready
      - gate available
      - baggage loaded
      - ramp service complete
      - passenger updates completed
