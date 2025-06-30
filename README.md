# Supply Visit Scheduler

An offline Flutter application for recording and managing supply representative visit appointments.

## Features

- 📅 Schedule appointments with representatives
- 🔔 Automatic notifications one day before appointments  
- 💾 Offline storage using Hive database
- ✏️ Edit and delete appointments
- 📱 Clean, intuitive interface
- 🚫 No internet connection required

## APK Generation Instructions

To generate an APK file for Android installation:

### Method 1: Debug APK (Quick Testing)
```bash
flutter build apk --debug
```
The APK will be generated at: `build/app/outputs/flutter-apk/app-debug.apk`

### Method 2: Release APK (Recommended for Distribution)
```bash
flutter build apk --release
```
The APK will be generated at: `build/app/outputs/flutter-apk/app-release.apk`

### Method 3: Split APKs by Architecture (Smaller file sizes)
```bash
flutter build apk --split-per-abi
```
This generates separate APKs for different CPU architectures:
- `app-arm64-v8a-release.apk` (Most modern devices)
- `app-armeabi-v7a-release.apk` (Older devices)
- `app-x86_64-release.apk` (Emulators)

## Installation Instructions

1. Enable "Unknown Sources" or "Install from Unknown Sources" in your Android device settings
2. Transfer the APK file to your Android device
3. Tap on the APK file to install
4. Follow the installation prompts

## App Permissions

The app requires the following permissions:
- **Notifications**: To send appointment reminders
- **Storage**: To save appointment data locally
- **Wake Lock**: To ensure notifications work when device is sleeping

## Getting Started for Development

1. **Prerequisites:**
   - Flutter SDK (≥ 3.10)
   - Dart SDK (≥ 3.0)
   - Android Studio or VS Code
   - Android SDK

2. **Installation:**
   ```bash
   git clone <repository-url>
   cd supply_visit_scheduler
   flutter pub get
   ```

3. **Run the app:**
   ```bash
   flutter run
   ```

## Building for Different Targets

### Android
```bash
# Debug APK
flutter build apk --debug

# Release APK  
flutter build apk --release

# AAB (Android App Bundle) for Play Store
flutter build appbundle --release
```

### iOS (requires macOS)
```bash
flutter build ios --release
```

## Project Structure

```
lib/
├── main.dart                          # App entry point
├── core/
│   └── app_export.dart               # Core exports
├── presentation/
│   ├── appointment_list_screen/      # Main appointments list
│   ├── add_appointment_screen/       # Add new appointment
│   ├── edit_appointment_screen/      # Edit existing appointment
│   └── appointment_detail_screen/    # View appointment details
├── theme/
│   └── app_theme.dart               # App theme configuration
├── widgets/                         # Reusable widgets
└── routes/
    └── app_routes.dart             # App routing
```

## Data Storage

The app uses **Hive** database for local storage:
- All data is stored locally on the device
- No internet connection required
- Data persists between app sessions
- Automatic backup and restore functionality

## Notifications

Local notifications are scheduled automatically:
- Reminder appears 24 hours before appointment
- Works offline without internet
- Notifications persist through device restarts
- Customizable notification settings

## Troubleshooting

### APK Installation Issues
- Make sure "Unknown Sources" is enabled
- Check available storage space
- Try installing via ADB: `adb install app-release.apk`

### Notification Issues
- Check notification permissions in device settings
- Ensure battery optimization is disabled for the app
- Verify date and time settings on device

### Build Issues
- Run `flutter clean` and `flutter pub get`
- Check Flutter and Dart SDK versions
- Update Android SDK and build tools

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License.

## 📱 Responsive Design

The app is built with responsive design using the Sizer package:

```dart
// Example of responsive sizing
Container(
  width: 50.w, // 50% of screen width
  height: 20.h, // 20% of screen height
  child: Text('Responsive Container'),
)
```

## 📦 Deployment

Build the application for production:

```bash
# For Android
flutter build apk --release

# For iOS
flutter build ios --release
```

## 🙏 Acknowledgments
- Built with [Rocket.new](https://rocket.new)
- Powered by [Flutter](https://flutter.dev) & [Dart](https://dart.dev)
- Styled with Material Design

Built with ❤️ on Rocket.new