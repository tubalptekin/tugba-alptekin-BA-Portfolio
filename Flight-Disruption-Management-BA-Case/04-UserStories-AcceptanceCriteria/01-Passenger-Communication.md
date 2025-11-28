# 📱 User Stories — Passenger Communication

Bu bölüm uçuş gecikmesi sonrası yolcuya gönderilen tüm bilgilendirme akışlarını kapsar.

## ✔️ User Story 1 — Notify Passenger About Delay

As a passenger,

I want to receive a notification when my flight is delayed,

so that I am aware of the change without needing to check manually.

**✅ Acceptance Criteria (Gherkin)**

Scenario: Passenger receives delay notification

  Given the flight has a confirmed delay
  
  And the system has the passenger’s valid contact information
  
  When the OCC publishes a delay update event
  
  Then the system should send a push notification
  
  And send an SMS if enabled
  
  And send an email if email preference is active
  

## ✔️ User Story 2 — Show Updated ETD in Mobile App

As a passenger,

I want to see the new departure time clearly in the app,

so that I can adjust my plans quickly.

**✅ Acceptance Criteria (Gherkin)**

Scenario: Passenger sees updated ETD in the app

  Given my flight status has changed
  
  When I open the mobile app or refresh the flight details
  
  Then I should see the updated ETD
  
  And the delay duration should be displayed
  
  And the change should be marked visually (e.g., highlighted)

## ✔️ User Story 3 — Provide Reason for Delay

As a passenger,

I want to know the reason for the delay,

so that I understand the situation and feel informed.

**✅ Acceptance Criteria (Gherkin)**

Scenario: Delay reason displayed in app

  Given the OCC has entered a delay reason
  
  When the passenger views the flight details
  
  Then the system should display the delay reason
  
  And show a short description (e.g., "Aircraft rotation", "Weather", "Technical check")
  

## ✔️ User Story 4 — Offer Passenger Rebooking Options (If Eligible)

As a passenger affected by major delays,

I want to see alternative flights I can move to,

so that I can choose the option most suitable for my schedule.

⚠️ This only applies for delays > X minutes or regulations requiring compensation.

**✅ Acceptance Criteria (Gherkin)**

Scenario: Eligible passenger sees rebooking options

  Given the flight delay exceeds the airline’s rebooking threshold
  
  And there are alternative flights available
  
  When the passenger opens the rebooking screen
  
  Then the system should show a list of alternative flights
  
  And allow the passenger to select a new flight
  
  And confirm the change
  

## ✔️ User Story 5 — Confirm Rebooking

As a passenger,

I want to confirm and finalize my rebooking selection,

so that my new flight is reserved without needing to call support.


**Acceptance Criteria (Gherkin)**

Scenario: Passenger confirms rebooking

  Given the passenger has selected an alternative flight
  
  When the passenger taps “Confirm”
  
  Then the system should reissue the ticket
  
  And send a confirmation notification
  
  And update the PNR with the new flight segment
  

## ✔️ User Story 6 — Display Compensation Options (if applicable)

As a passenger,

I want to see compensation or voucher options if regulations require it,

so that I can choose the benefit I am entitled to.


**Acceptance Criteria (Gherkin)**

Scenario: Passenger sees compensation options

  Given the delay meets compensation rules (EU261 or airline policy)
  
  When the passenger opens the disruption assistance page
  
  Then compensation options should be shown
  
  And the passenger should be able to claim or request them
