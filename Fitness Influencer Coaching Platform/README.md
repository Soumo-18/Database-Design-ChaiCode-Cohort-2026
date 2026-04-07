# Fitness Influencer Coaching Platform — Database Design

A relational database schema for managing a fitness coaching business, covering clients, trainers, plans, subscriptions, live sessions, check-ins, progress tracking, and payments.

Eraser Link ->  https://app.eraser.io/workspace/T930sKiKo2T2sghLFhaa?origin=share

## Entities

| Table | Description |
|---|---|
| `clients` | Client profiles with contact and social info |
| `trainers` | Trainer profiles |
| `plans` | Coaching plans (Live Consultation, Training Routine, Long Term Coaching) |
| `workouts` | Workout guides and diet plans linked to a plan |
| `subscriptions` | Client plan subscriptions with status and duration |
| `live_consultations` | 1-on-1 sessions between client and trainer |
| `checkin` | Weekly client check-ins with progress images and notes |
| `progress_tracking` | Body metrics recorded per check-in |
| `payment` | Payment records per subscription (UPI / Card) |

## Key Relationships

- A client can have multiple subscriptions, live sessions, check-ins, and progress records
- A trainer can create multiple plans, workouts, and conduct live sessions
- A subscription ties a client to a plan and enables live consultations and payments
- Weekly check-ins feed into progress tracking

## Tools Used

- Schema designed with [dbdiagram.io](https://dbdiagram.io) / DBML-style syntax
