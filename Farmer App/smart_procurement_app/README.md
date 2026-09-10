# Smart Procurement — Flutter Prototype

A farmer-first Smart India Hackathon prototype for dynamic procurement scheduling and network-wide load balancing.

## Run
1. Install Flutter.
2. Run `flutter pub get`.
3. Run `flutter run`.

This prototype works **without Firebase/API keys** using realistic mock data, so the demo can be shown immediately.

## Demo
- Open Farmer mode.
- Registration/verification is mocked.
- The system assigns a day/window and best centre automatically.
- Live queue and leave-time are calculated from mock conditions.
- Open Admin mode.
- Trigger **Centre A equipment failure**.
- Farmers who have not left are automatically reassigned to B/C.
- The farmer view and notification feed update immediately.

## Replacing mocks later
All external integrations are isolated:
- `services/auth_service.dart`
- `services/verification_service.dart`
- `services/queue_service.dart`
- `services/maps_service.dart`
- `services/weather_service.dart`
- `services/notification_service.dart`
- `services/ai_service.dart`
- `services/data_service.dart`

The allocation/priority/reassignment logic is isolated under `scheduling/`.
No Aadhaar, bank credentials, Firebase credentials, or API keys are hard-coded.

## Production roadmap
- Add Firebase Authentication + Firestore + Cloud Functions + FCM.
- Move authoritative allocation/reassignment decisions to Cloud Functions/Python.
- Connect authorized government verification APIs.
- Connect Google Routes/Maps and a weather provider.
- Add secure server-side AI retrieval/tooling.
