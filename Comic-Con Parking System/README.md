# Comic-Con Parking System

A relational database schema for managing event parking at Comic-Con, supporting special access categories for VIPs, cosplayers, exhibitors, and staff.

## Entities

| Table | Description |
|---|---|
| `vehicle_category` | Vehicle types — Bike, Car, SUV, Cab, EV |
| `vehicle` | Registered vehicles with owner info and access category |
| `spot_category` | Spot types — Cosplayer, Exhibitor, VIP, Staff, EV Charging |
| `parking_zone` | Top-level parking zones |
| `parking_level` | Floors within a zone (G, L1, L2) |
| `parking_spot` | Individual spots with availability status |
| `spot_vehicle_compatibility` | Maps which vehicle types can use which spot types |
| `parking_session` | Active/completed parking sessions with entry/exit times |
| `parking_ticket` | Ticket issued per session |
| `parking_rate` | Base, hourly, and daily rates per vehicle category |
| `payment` | Payment records per session with method and status |

## Key Relationships

- A **zone** has many **levels**, each level has many **spots**
- A **spot category** defines access rules for **vehicles** and **spots**
- **spot_vehicle_compatibility** resolves the many-to-many between spot and vehicle categories
- Each **parking session** links a vehicle to a spot, generating one **ticket** and one **payment**

## Enums

- `vehicle_category.category_name` — `Bike`, `Car`, `SUVs`, `Cabs`, `EV`
- `parking_level.level_name` — `G`, `L1`, `L2`
- `parking_session.session_status` — `Active`, `TimeUp`
- `parking_ticket.ticket_status` — `Issued`, `Used`, `Expired`
- `payment.payment_method` — `UPI`, `Card`, `Cash`
- `payment.payment_status` — `Pending`, `Paid`, `Failed`

## Files

- `code-export-09-04-2026-18_30_25.txt` — Chen notation schema definition
- `diagram-export-09-04-2026-18_30_22.png` — ER diagram
