Smart Procurement – Final Consolidated Patch

Copy the contents of this patch into the existing Flutter project and replace the matching files.

Included changes:
- Interactive Aadhaar and OTP keypads with keypad visibility/validation rules.
- 45-second OTP resend countdown from the start of the OTP screen.
- Real Android local notifications for OTP, appointment and centre-change events. Heads-up notifications use high importance and remain in the notification shade after the heads-up presentation ends.
- Notifications are global and independent of the currently open app screen.
- Interactive verification: Identity, Land Record, Bank Account, Crop and Eligibility.
- Bank account validation: 9–18 digits, digits only; IFSC accepts letters/numbers and is forced to uppercase.
- Crop quantity accepts digits only.
- Dialog-owned form controllers to avoid the previously observed controller-disposal crash.
- Attendance card on Home, enabled after appointment assignment and marked before leaving home.
- OpenStreetMap-based Travel map with road-routing fallback; Google Maps dependency removed.
- Open Navigation button removed.
- MSP, Queue, Procurement Status and Payment History retained.
- Flexible rule-based natural-language Assistant using current app state.
- English/Hindi app language selection; Android notification language follows device locale independently.
- Prototype/mock/demo wording removed from normal Profile/Admin UI.
- Logout resets the authenticated session and navigation stack.

Notification note:
Android controls the exact duration of a heads-up notification. The notification is intentionally not auto-cancelled after five seconds, so it can remain in the Android notification shade as requested.

No Google Maps API key or billing setup is required.
