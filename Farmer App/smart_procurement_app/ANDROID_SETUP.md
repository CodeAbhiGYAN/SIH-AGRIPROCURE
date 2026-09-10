# Android / Firebase setup

The included Flutter prototype intentionally starts with mock services so it runs without credentials.

For production/prototype cloud integration:
1. Add Firebase to the Flutter project with FlutterFire CLI.
2. Add `firebase_core`, `firebase_auth`, `cloud_firestore`, `firebase_messaging`.
3. Initialize Firebase in `main()`.
4. Replace the service classes one at a time.
5. Put allocation/reassignment/prediction behind callable Cloud Functions.
6. Keep government credentials server-side only.
7. Never put Aadhaar/bank secrets or API keys in the Flutter source.

Suggested Firestore collections:
- farmers/{farmerId}
- centres/{centreId}
- appointments/{appointmentId}
- queueEvents/{eventId}
- procurementEvents/{eventId}
- notifications/{notificationId}
- weatherSnapshots/{snapshotId}
- allocationEvents/{eventId}
- auditLogs/{logId}
