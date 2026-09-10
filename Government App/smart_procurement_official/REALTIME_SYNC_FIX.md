# Realtime synchronization fix

The Government app now uses two layers for live synchronization:

1. Supabase Realtime subscriptions for database change events.
2. A 2-second lightweight refresh fallback to recover from missed/temporarily disconnected WebSocket events.

Realtime refreshes are queued while an existing shared-data fetch is running so a concurrent event is not silently discarded.

For the backend, run the companion Supabase SQL fix again. It keeps the Realtime publication membership and sets `REPLICA IDENTITY FULL` on the shared tables.
