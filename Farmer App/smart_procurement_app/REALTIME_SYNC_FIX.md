# Realtime synchronization fix

The Farmer app now uses two layers for live synchronization:

1. Supabase Realtime subscriptions for database change events.
2. A 2-second lightweight refresh fallback to recover from missed/temporarily disconnected WebSocket events.

Every remote state refresh now calls `notifyListeners()` so the currently visible UI rebuilds immediately after remote state changes.

The refresh request is queued if a previous remote fetch is still running, preventing a Realtime event from being dropped by the loading guard.

For the backend, run the companion Supabase SQL fix again. It keeps the Realtime publication membership and sets `REPLICA IDENTITY FULL` on the shared tables.
