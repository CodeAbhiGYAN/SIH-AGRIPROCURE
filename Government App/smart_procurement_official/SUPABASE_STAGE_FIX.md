# Supabase stage/appointment fix

This build fixes procurement-stage persistence:

- Attendance/location is written before procurement status, satisfying the database workflow guard.
- Every selected Government stage is stored independently in `procurement.stages`.
- Valid stage combinations are enforced as a sequential workflow prefix.
- Farmer-side Procurement Status can therefore display exactly what Government saved.
