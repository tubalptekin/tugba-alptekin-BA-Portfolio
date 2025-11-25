📌 Requirements — Visa Application Center System
1. Project Overview

The Visa Application Center System manages the end-to-end workflow of visa applications, from scheduling appointments to collecting biometric data and submitting documents to the consulate.
| Stakeholder           | Role                     | Expectations                                                             |
| --------------------- | ------------------------ | ------------------------------------------------------------------------ |
| **Applicant**         | Visa seeker              | Easy appointment booking, document upload, application tracking          |
| **VAC Officer**       | In-office operator       | Efficient document verification & biometric workflow                     |
| **Cashier**           | Handles fees             | Receives payments and issues receipts                                    |
| **Consulate**         | Decision authority       | Accurate, complete, timely applications                                  |
| **System Admin**      | Manages roles & dat      | Secure system operations                                                 |

3. Functional Requirements
3.1 Appointment Management

FR-01: Applicant must select visa type and available date.

FR-02: System must show available appointment slots.

FR-03: Applicant must receive appointment confirmation (email + SMS).

3.2 Document Submission

FR-10: Applicant must upload required documents.

FR-11: System must validate file formats and size.

FR-12: VAC Officer must review and mark documents as accepted or rejected.

3.3 Biometric Collection

FR-20: System must manage biometric room queues.

FR-21: Officer must capture fingerprints & photo.

FR-22: Data must be securely stored and transferred to consulate.

3.4 Payment

FR-30: Applicant must pay visa fee during appointment.

FR-31: System must generate digital receipt.

FR-32: Refund rules must be applied automatically.

3.5 Application Tracking

FR-40: Applicant must track application status (Received → Processing → Completed).

FR-41: Applicant must receive status notifications.

FR-42: Consulate must be able to update decision status.

4. Non-Functional Requirements
Security

NFR-01: Biometric data must be encrypted (AES-256).

NFR-02: System must comply with GDPR and KVKK.

Performance

NFR-10: Appointment list must load in < 2 seconds.

Usability

NFR-20: Mobile-friendly interface.

NFR-21: Multilingual support (TR/EN).

5. Business Rules

BR-01: Applicant cannot book more than one appointment at a time.

BR-02: Missing documents = application cannot proceed.

BR-03: Biometric collection is mandatory for all applicants except categories defined by consulate.

6. Success Metrics

30% faster processing time

40% fewer rejected applications

25% reduction in queues at biometric room
