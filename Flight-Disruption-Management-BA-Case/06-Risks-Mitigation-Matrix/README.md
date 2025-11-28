# 🛡 06 — Risks & Mitigation Matrix

This section highlights the operational, technical, and passenger-facing risks that may arise during a flight delay event, and the mitigation actions required to minimize disruption impact.

| **Risk ID** | **Risk Description**                                                     | **Impact Area**               | **Likelihood** | **Severity** | **Risk Level** | **Mitigation Strategy**                                                                                                      |
| ----------- | ------------------------------------------------------------------------ | ----------------------------- | -------------- | ------------ | -------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **R-01**    | Delay update not propagating to all systems (OCC → Gate/FIDS/PNR)**      | Operations, Passenger Systems | Medium         | High         | 🔴 High        | Implement event-driven architecture with guaranteed delivery; monitor message queues; enable automated retries.              |
| **R-02**    | Passenger receives inconsistent or late notifications                    | Passenger Experience          | High           | Medium       | 🟠 Medium-High | Use centralized notification engine; ensure push/SMS/email are triggered from the same event source; add latency monitoring. |
| **R-03**    | Gate conflict due to delayed aircraft still occupying next flight’s gate | Airport Operations            | Medium         | High         | 🔴 High        | Introduce real-time gate conflict detection; automate gate reassignment suggestions; integrate OCC ↔ Airport Ops alerts.     |
| **R-04**    | Crew legality breach due to extended delay                               | Crew Management               | Medium         | High         | 🔴 High        | Automate legality recalculation; trigger alerts when limits are near; enable rapid crew reassignment workflow.               |
| **R-05**    | Wrong aircraft rotation sequence after delay                             | Fleet / OCC                   | Low            | High         | 🟠 Medium-High | Sync rotation tables in real-time; highlight rotation conflicts; provide OCC with automated alternative scenarios.           |
| **R-06**    | Baggage system misrouting due to last-minute gate change                 | BHS / Ground Handling         | Medium         | Medium       | 🟠 Medium      | Push gate updates instantly to BHS/BRS; enforce validation rules; enable baggage reroute exceptions screen.                  |
| **R-07**    | FIDS not refreshed, showing outdated flight information                  | Airport Ops / Passengers      | Low            | High         | 🟠 Medium-High | Use publish/subscribe architecture; define SLA for FIDS refresh; log and alert when screens fail to update.                  |
| **R-08**    | Over-notification spamming passengers (duplicate SMS/push emails)        | Passenger Experience          | Medium         | Low          | 🟡 Medium      | Add de-duplication logic; rate-limit notifications; create templates for major/minor delay types.                            |
| **R-09**    | Rebooking system overload during mass delays                             | Passenger Systems             | Low            | High         | 🟠 Medium-High | Implement queue management; scale dynamically; enable fallback static rebooking list view.                                   |
| **R-10**    | OCC operator error during manual ETD entry                               | OCC / System Data             | Low            | Medium       | 🟡 Medium      | Add mandatory validation; highlight unrealistic ETD values; enforce rule-based ETD suggestions.                              |

<br>

## **🧭 Risk Heat Map (Summary)**
|                       | **Low Impact** | **Medium Impact** | **High Impact** |
| --------------------- | -------------- | ----------------- | --------------- |
| **Low Likelihood**    | R-05, R-07     | R-09              | R-10            |
| **Medium Likelihood** | R-08           | R-06              | R-01, R-03      |
| **High Likelihood**   | —              | R-02              | R-04            |

<br>

## 🛠 Mitigation Themes (BA Perspective)

**1. System Reliability**

Event-driven architecture

Retry mechanisms

API health monitoring

**2. Operational Synchronization**

Centralized delay-update service

Real-time gate & resource recalculation

Cross-system validation rules

**3. Passenger Experience Protection**

Single notification engine

Avoid duplicate or confusing messages

Provide consistent updates across app/SMS/email

**4. Decision Support for OCC**

Automated ETD suggestion logic

Conflict detection for gate/crew/rotation

Exception workflows for manual overrides
