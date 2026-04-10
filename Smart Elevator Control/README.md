# Smart Elevator Control — LiftGrid Systems

ER diagram for LiftGrid Systems' intelligent elevator control platform used in corporate towers, malls, airports, hospitals and high-rise residential complexes across India.

## Entities (13)

| Entity | Role |
|---|---|
| `building` | Each physical building on the platform |
| `floor` | Every floor inside a building |
| `elevator_shaft` | Physical shaft per building; enforces one elevator per shaft |
| `elevator` | Elevator config — model, capacity, floor range |
| `elevator_floor` | Junction — elevator ↔ floor (many-to-many) |
| `elevator_status` | Live state — current floor, idle/moving/maintenance |
| `floor_request` | Passenger request from a floor with direction (Up/Down) |
| `ride_assignment` | Links one request to one elevator |
| `ride_log` | Trip record — pickup floor, dropoff floor, timestamps |
| `zone` | Named zone inside a building (Low Rise, High Rise, Express, Service, Parking) |
| `elevator_zone` | Junction — elevator ↔ zone (many-to-many) |
| `floor_zone` | Junction — floor ↔ zone (many-to-many) |
| `maintenance` | Append-only maintenance log per elevator |

## Key Design Decisions

- Elevator config is never mixed with live ride data
- `elevator_status` is a separate 1-to-1 table — keeps dynamic state out of elevator config
- `ride_log` stores full trip history for analytics
- `maintenance` is append-only — history is never overwritten
- Zone support handles multi-zone buildings like airports and malls

## Files

| File | Description |
|---|---|
| `code-export-10-04-2026-20_18_54.txt` | Eraser.io ERD source code |
| `diagram-export-10-04-2026-20_18_51.png` | Exported ERD diagram |
