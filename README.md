# Insight

Insight is a Flutter mobile application that provides AI-assisted analysis and
reading tools for Arabic and English content. The app uses a dark Material 3
interface with right-to-left support and connects to the Insight API for
image and document processing.

## Features

- **Form analysis**: check image quality, detect language direction, identify
  form fields, fill them, and preview annotated results.
- **Currency reading**: analyze images of banknotes and currencies.
- **Document reading**: upload and analyze PDF, PowerPoint, and Word files.
- **PDF workflows**: analyze, explain, fill, download, and track PDF processing
  stages.
- **Signature support**: detect and upload signatures for form workflows.
- **Audio assistance**: speech-to-text and audio playback support.
- **Arabic and English**: localized content, RTL layout, and Arabic text
  handling.
- **Connection-aware UX**: network monitoring, loading states, and user-facing
  error handling.

## Technology

- Flutter and Dart
- Provider for state management
- Dio and HTTP for API communication
- File Picker and Image Picker for user files and images
- PDF for PDF processing and generation
- Shared Preferences for local settings
- Speech to Text, Record, and Just Audio for audio features
- Cairo font assets for Arabic typography

## Project structure

```text
lib/
├── models/       API and workflow data models
├── providers/    Application and PDF state management
├── screens/      Home, form, currency, document, and PDF screens
├── services/     API, PDF, and speech services
├── utils/        Theme, networking, storage, and file helpers
└── widgets/      Shared UI and workflow widgets
```

## Requirements

- Flutter SDK compatible with Dart `>=3.0.0 <4.0.0`
- Android Studio or VS Code with a Flutter plugin
- An Android or iOS device/emulator
- Access to the configured Insight API

## Getting started

```bash
git clone https://github.com/Mohamed-Samirr/insight_app.git
cd insight_app
flutter pub get
flutter run
```

Run the analyzer and tests with:

```bash
flutter analyze
flutter test
```

## API configuration

The application currently uses the API base URL defined in
`lib/services/insight_api_service.dart`. Update the `baseUrl` there when
pointing the app at a different backend. The API service includes endpoints for
form quality checks, form analysis, image annotation, currency analysis, and
document processing.

Supported input types and limits are defined in `lib/utils/constants.dart`:

- Images: JPG, JPEG, PNG, BMP, and GIF; maximum 10 MB
- Documents: PDF, PPTX, PPT, DOCX, and DOC; maximum 50 MB

Do not commit private API keys, credentials, or production-only endpoints.

## Building

```bash
# Android APK
flutter build apk --release

# Android App Bundle
flutter build appbundle --release

# iOS
flutter build ios --release
```

## Permissions

Depending on the feature and platform, the app may require camera, photo
library/storage, microphone, and internet permissions. These are configured in
the Android and iOS platform projects.

## Contributing

1. Create a feature branch.
2. Make focused changes and add or update tests where appropriate.
3. Run `flutter analyze` and `flutter test`.
4. Open a pull request with a clear description of the change.

## License

No license file is currently included in this repository. Add a `LICENSE`
file before distributing the project under an open-source license.
