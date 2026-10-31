# Raju Video Maker — Flutter starter

This is the first Android UI prototype for **Raju Video Maker**.

## Included in this prototype
- Premium dark interface
- Video file selection (file_picker)
- Bengali story/script input
- Male/female voice selection UI
- 9:16 and 16:9 output selection UI
- Animation style selection UI
- Subtitle and background music toggles

## Important: what is not connected yet
This starter is **not a finished AI video generator and does not create an APK by itself**.
The Create button currently validates the form and displays a setup notice.
The following backend services must be implemented and connected:
1. Upload and securely store the source video.
2. Extract representative frames with FFmpeg / scene detection.
3. Generate visual embeddings/captions for frames and Bengali script segments.
4. Match script segments to the best frames (multimodal model / embedding search).
5. Generate Bengali male/female narration using a licensed TTS provider.
6. Align narration, subtitles, music, and animated stills (FFmpeg).
7. Render 1080p MP4 in 9:16 or 16:9 and return a download URL.

## Run locally
Install Flutter SDK, then from this folder:
```bash
flutter pub get
flutter run
```

To build an Android APK after configuring Android SDK:
```bash
flutter build apk --release
```

## Suggested production architecture
- Android client: Flutter
- API: Python FastAPI
- Video processing: FFmpeg worker
- Storage: private object storage with signed URLs
- AI: vision-language model for frame descriptions/matching
- Bengali narration: TTS provider supporting Bengali voices

Never place AI provider API keys inside the Android app. Keep keys on the backend.
