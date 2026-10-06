
# OPO LIVE — Flutter Voice Streaming Starter

This is a production-oriented foundation for an Android voice-room app with an OPO LIVE-style UI.

## Included
- Flutter Material 3 dark/neon UI
- Firebase anonymous authentication
- Firestore users, rooms and real-time room chat
- Agora RTC voice room integration
- Secure token-server architecture (Agora certificate stays server-side)
- Host / viewer room flow
- Mic mute/unmute
- Firestore security rules
- Firebase Cloud Function token endpoint

## Important
This is NOT a finished Poppo/Yalla-scale commercial backend. A real production launch still needs:
- Firebase project + FlutterFire configuration
- Agora project + production credentials
- deployed token server
- moderation/report/block system
- anti-abuse/rate limiting
- real wallet/coin ledger and payment verification
- gifts and transaction history
- push notifications
- image/file storage
- admin dashboard
- analytics/crash reporting
- legal/privacy/age-safety compliance
- load testing and security review

Never put the Agora App Certificate in Flutter/Dart code.

## Setup

1. Create a Flutter project or use this folder.
2. Run:
   flutter pub get

3. Configure Firebase:
   dart pub global activate flutterfire_cli
   flutterfire configure

4. Enable Anonymous Authentication and Cloud Firestore in Firebase Console.

5. Create an Agora project and keep the App Certificate private.

6. Deploy the token function:
   cd functions
   npm install
   npm run build
   firebase deploy --only functions

7. Set server environment variables in your deployment:
   AGORA_APP_ID
   AGORA_APP_CERTIFICATE

8. Run Android:
   flutter run --dart-define=AGORA_APP_ID=YOUR_AGORA_APP_ID --dart-define=TOKEN_SERVER_URL=https://YOUR_FUNCTION_URL

## Design
The UI uses the requested OPO LIVE purple/pink/blue neon style. Replace demo room cards with real user avatars, gifts and room artwork from Firebase Storage.

## Production checklist
Use App Check, authenticated callable/server endpoints, strict Firestore rules, App Store/Play policies, payment provider verification, rate limiting, moderation tools, audit logs and automated backups before launch.
