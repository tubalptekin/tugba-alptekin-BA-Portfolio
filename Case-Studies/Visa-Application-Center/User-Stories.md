📘 User Stories – Visa Application Center

👤 1. Applicant User Stories

US-01 – Online Application


As an applicant,

I want to submit an online application form,

so that I can start the visa process digitally.


Acceptance Criteria:

Required fields must be entered before submission

User receives confirmation after submission

Incomplete forms cannot be submitted

US-02 – Upload Documents

As an applicant,

I want to upload supporting documents,

so that the visa center can review my information.


Acceptance Criteria:

Only allowed file types are accepted (PDF, JPEG, PNG)

Maximum size: 10 MB per file

User can replace or delete uploaded documents

US-03 – Schedule Appointment

As an applicant,

I want to select an available appointment slot,

so that I can visit the center for biometrics and submission.


Acceptance Criteria:

Only available dates are selectable

User receives email + SMS confirmation

Appointment cannot overlap with existing ones

US-04 – Track Application Status

As an applicant,

I want to track the status of my application,

so that I know if my visa is processing, approved, or rejected.


Acceptance Criteria:

Status updates shown in timeline format

User receives notifications for status changes

🧑‍💼 2. Operations Staff User Stories

US-10 – Review Documents

As an operations staff member,

I want to review uploaded documents,

so that I can verify if the applicant meets requirements.


Acceptance Criteria:

Officer can mark documents as accepted/rejected

Officer can add notes

System prevents incomplete applications from moving forward

US-11 – Collect Biometrics

As an operations staff member,

I want to capture fingerprints and photos,

so that the biometric data can be sent to the consulate.


Acceptance Criteria:

Biometrics must be saved securely

Applicant identity must be verified before biometric capture

🤖 3. Automation Engine User Stories

US-20 – Send Notifications


As the system automation engine,

I want to send notifications to applicants,

so that they stay informed about their process.


Acceptance Criteria:

Notifications sent for appointment, biometrics, decision

If sending fails, retry mechanism triggers

US-21 – Send Application Package

As the automation engine,

I want to transfer the completed application to the consulate,

so that it can be reviewed and decided.

Acceptance Criteria:

Full document set must be included

Transfer must be logged with timestamps


🏛 4. Consulate System User Stories

US-30 – Review Application


As the consulate system,

I want to review application data,

so that I can determine the visa result.


Acceptance Criteria:

System must receive data in standard format

Missing items must be flagged

US-31 – Return Decision

As the consulate system,

I want to send back the decision,

so that the applicant is notified.

Acceptance Criteria:

Decision includes approval, rejection, or request for more documents

System sends decision securely to automation engine
