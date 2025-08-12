# Flutter GitHub Codespace Development Setup

This repository is configured with a development container for GitHub Codespaces, providing a complete Flutter development environment in the cloud.

## 🚀 Quick Start

### Starting a Codespace

1. Navigate to this repository on GitHub
2. Click the **Code** button
3. Select the **Codespaces** tab
4. Click **Create codespace on main**
5. Wait for the container to build and initialize (2-3 minutes)

### Running the Flutter App

Once your codespace is ready:

1. **Verify Flutter installation:**
   ```bash
   flutter doctor
   ```

2. **Install dependencies:**
   ```bash
   flutter pub get
   ```

3. **Run the app on web:**
   ```bash
   flutter run -d web-server --web-hostname=0.0.0.0 --web-port=3000
   ```

4. **Access your app:**
   - Click the notification that appears when the port is forwarded
   - Or go to the **Ports** tab and click the globe icon next to port 3000
   - Or use the forwarded URL provided in the terminal

## 📋 What's Included

### Pre-installed Tools
- **Flutter SDK** (stable channel)
- **Dart SDK**
- **VS Code Extensions:**
  - Dart-Code.flutter
  - Dart-Code.dart-code
  - ms-vscode.vscode-json

### Development Features
- **Hot Reload:** Automatically enabled on save
- **Auto Format:** Code formatting on save
- **Port Forwarding:** Port 3000 configured for Flutter web
- **Auto Dependencies:** `flutter pub get` runs automatically on container creation

### VS Code Settings Optimized for Flutter
- Dart SDK path configured
- Hot reload on save enabled
- Auto-save configured
- Format on save enabled
- Code actions on save (auto-fix)

## 🔧 Development Workflow

### Making Changes
1. Edit your Dart code in the `lib/` directory
2. Save the file (hot reload triggers automatically)
3. View changes instantly in your forwarded web browser

### Adding Dependencies
1. Edit `pubspec.yaml` to add new dependencies
2. Run `flutter pub get` in the terminal
3. Import and use the new packages in your code

### Testing
```bash
# Run unit tests
flutter test

# Run specific test file
flutter test test/widget_test.dart
```

### Building for Production
```bash
# Build web version
flutter build web

# Build Android APK (limited in Codespaces)
flutter build apk
```

## 🌐 Web Development Focus

**Note:** GitHub Codespaces doesn't support mobile device simulators or emulators. This setup is optimized for:

- **Flutter Web Development**
- **UI/UX prototyping**
- **Cross-platform code development**
- **Package development and testing**

For mobile testing, use browser developer tools to simulate mobile devices.

## ⚡ Performance Tips

1. **Keep codespace running** during active development sessions
2. **Use hot reload** instead of full restarts when possible
3. **Close unused tabs** in VS Code to conserve resources
4. **Stop the Flutter app** (`Ctrl+C`) when not actively developing

## 🔍 Troubleshooting

### Flutter Doctor Issues
If `flutter doctor` shows issues:
```bash
# Rerun flutter doctor with verbose output
flutter doctor -v

# Clear Flutter cache if needed
flutter clean
flutter pub get
```

### Port Access Issues
If you can't access the web app:
1. Check that port 3000 is forwarded in the **Ports** tab
2. Ensure you're using `--web-hostname=0.0.0.0` when running Flutter
3. Try stopping and restarting the Flutter app

### Performance Issues
If the codespace feels slow:
1. Restart the codespace
2. Clear Flutter build cache: `flutter clean`
3. Rebuild dependencies: `flutter pub get`

## 📱 Mobile Development Notes

While this setup focuses on web development, you can still:
- Develop cross-platform Flutter code
- Test responsive layouts using browser dev tools
- Use Flutter's device preview features
- Develop and test mobile-specific logic (without visual testing)

For full mobile development with device testing, consider using this setup for code development and a local Flutter installation for device testing.

## 🤝 Contributing

When working in a team:
1. **Commit frequently** - Codespaces can be rebuilt from git state
2. **Push changes regularly** - Codespaces are temporary environments
3. **Document environment requirements** in this README if you modify the devcontainer

---

**Happy coding! 🎉**