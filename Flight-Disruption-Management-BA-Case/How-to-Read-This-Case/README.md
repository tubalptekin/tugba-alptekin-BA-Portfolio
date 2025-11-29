# 📖 How to Read This Case

This case study is designed to walk you through the end-to-end disruption-handling lifecycle used in modern airline operations.
To fully understand the flow, follow the sections in the order below:

## 1️⃣ Start with the Scope & Actors

📁 01-Scope-and-Actors

Who is involved in disruption handling?

What are the responsibilities of OCC, Passenger Systems, Airport Ops, Crew Ops, BHS/BRS?

Which boundaries exist between systems and operational teams?

Outcome: You understand the ecosystem and problem domain.

## 2️⃣ Explore the Use Cases

📁 02-Use-Cases

What are the main functional behaviors of the system?

How does a delay move through OCC → Airport Ops → Passenger Systems?

Where are the alternate flows and exceptions?

Outcome: You get a feature-level understanding of the disruption process.

## 3️⃣ Review the Process Flows

📁 03-Process-Flows

High-level operational flow

Gate reassignment flow

Baggage routing and crew legality flows

Parallel operations across domains

Outcome: You see how each actor reacts to delay events and how the process works end-to-end.

## 4️⃣ Check System Interaction (HLA + Event Flow)

📁 05-System-Interaction-Diagram

How systems communicate after ETD update

Event-driven disruption pipeline

OCC → Event Publisher → Subscriber Systems

Sync between PSS, FIDS, BHS/BRS, Crew Ops, Fleet Ops

Outcome: You understand the technical underpinnings of operational coordination.

## 5️⃣ Dive into User Stories & Acceptance Criteria

📁 04-UserStories-AcceptanceCriteria

Passenger communication

OCC decisions

Airport operations

Crew & Aircraft resource updates

Fully structured Gherkin acceptance criteria

Outcome: You see BA requirements broken into precise, testable behaviors.

## 6️⃣ Review UI Mockups (Passenger-Facing)

📁 UI-Mockups

Delay notification screen

Rebooking selection view

Passenger assistance options

Outcome: You visualize how requirements translate into user experience.

## 7️⃣ Analyze Risks & Mitigation Strategies

📁 06-Risks-Mitigation-Matrix

Technical, operational, passenger-facing risks

Likelihood × severity scoring

Mitigation design

Outcome: You understand risk-aware BA thinking and operational resiliency.

## 8️⃣ Explore Tools & Techniques Used

📁 08-Tools-Techniques

BPMN

Event modeling

Use case writing

HLA design

UI prototyping

Impact analysis

Outcome: You see the methodological backbone of the project.

### 🎯 Final Note

If you want to understand how airlines manage disruption across 6 operational domains, this case study breaks it down into a clear, structured, and realistic BA framework.

This reading path ensures you grasp both the big picture and the deep technical/operational details.
