# Clinic Appointment & Diagnostics Platform

A relational database schema for managing clinic operations including patient appointments, doctor consultations, diagnostic tests, and payments.

## Entities

| Table | Description |
|---|---|
| `patient` | Patient registration and personal details |
| `doctor` | Doctor profiles linked to specialties |
| `specialty` | Medical specialties (e.g., Cardiology) |
| `appointment` | Scheduled visits between patient and doctor |
| `consultation` | Clinical notes, diagnosis, and advice per appointment |
| `diagnostic_tests` | Available lab tests with pricing |
| `test_prescription` | Tests prescribed during a consultation |
| `reports` | Test results linked to prescriptions |
| `payment` | Billing for OPD consultations or diagnostics |

## Key Relationships

- A **specialty** has many **doctors**
- A **patient/doctor** can have many **appointments**
- Each **appointment** has one **consultation**
- A **consultation** can have many **test prescriptions**
- Each **test prescription** has one **report**
- **Payments** are linked to a patient and consultation

## Enums

- `appointment.status` — `Pending`, `Completed`, `Cancelled`, `Delayed`
- `test_prescription.status` — `Pending`, `Sample Collected`, `Delivered`
- `payment.bill_type` — `OPD Consultation`, `Diagnostics`
- `payment.payment_status` — `Pending`, `Paid`, `Failed`
- `payment.payment_method` — `UPI`, `Card`, `COD`
