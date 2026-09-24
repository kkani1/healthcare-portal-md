# User Stories - Healthcare Portal System

# Domain context mapping
The legacy healthcare portal has everything in one big system. In a modern agile and domain driven design we will split everything into separate domains with their own rules and data.
o	Patient Management 
Components: Patient, Profile, Appointment, Provider, Care plan
Responsibilities: Manages patient demographics, Registration, Profile updates, Appointment Scheduling, and Rescheduling, 

o	Billing and Insurance claims
Components: Invoice, Payment, Insurance claim, Insurance provider, Insurance Eligibility
Responsibilities: Billing patients, submitting insurance claim, verifying insurance eligibility, Processing payments

o	Lab Test Diagnostic
Components: Lab Order, Lab Result, Lab technician
Responsibilities: Tracks lab test requests, process diagnostic results, links report back to specific patient record



## Story 1
Story 1: Reschedule an Appointment
As a registered patient,
I want to view my upcoming and past medical appointments   in a centralized dashboard
So that I can easily keep track of my healthcare schedule without needing to call front desk

```gherkin
Scenario: Viewing scheduled and past appointments successfully
Given a patient is logged into the healthcare portal dashboard
And the patient has upcoming appointments and past appointments
When they navigate to the “Appointment” section
Then the system should display the upcoming appointments sorted by date ascending, time physician name and specialty.
And the system should display a separate “History” tab containing past appointments sorted by date, time, physician name and visit status in the right order.
```

## Story 2
As a registered patient
I want to update my emergency contact details or phone number,
So that the medical staff always has my accurate information in case of an emergency

```gherkin
Scenario: Successfully updating a phone number
Given the patient is on their profile settings page
And their current phone number is “0245678003”
When they change the phone number to “0276890356”
And submit the change
Then the system should validate that the number matches the valid format
And update the contact record with new contact information
And emit “Patient contact updated” event
And display a success notification confirming the change
And leave all other profile fields unchanged
```






