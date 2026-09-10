# Supabase stage/appointment fix

This build fixes two backend-sync issues:

1. After verification, the Farmer app remains in "appointment being arranged" for 12 seconds before Centre A is assigned. Queue and Travel remain unavailable until the appointment exists.
2. Government procurement stages are stored independently in `procurement.stages`, so the Farmer Procurement Status screen reflects exactly the stages saved by Government.
