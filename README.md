# Flutter CI/CD Project

This project demonstrates a complete CI/CD pipeline for a Flutter application using GitHub Actions.

## CI/CD Pipeline

The project includes a comprehensive CI/CD pipeline that:

1. **Runs Tests**
   - Executes all unit and widget tests
   - Performs code analysis
   - Verifies code formatting

2. **Builds Applications**
   - Creates Android APK
   - Builds iOS application
   - Stores artifacts for deployment

3. **Deployment**
   - Deploys to Firebase App Distribution
   - Supports both Android and iOS platforms
   - Automatic distribution to testers

## Getting Started

### Prerequisites

- Flutter SDK (version 3.19.0 or higher)
- Android Studio / Xcode
- Git
- Firebase project setup
- Firebase CLI installed locally

### Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Install dependencies:
   ```bash
   flutter pub get
   ```

3. Run the application:
   ```bash
   flutter run
   ```

### Firebase Setup

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)

2. Add your Android and iOS apps to the Firebase project

3. Configure GitHub Secrets:
   - `FIREBASE_TOKEN`: Firebase CI token (generate using `firebase login:ci`)
   - `FIREBASE_ANDROID_APP_ID`: Your Android app ID from Firebase
   - `FIREBASE_IOS_APP_ID`: Your iOS app ID from Firebase

4. Set up Firebase App Distribution:
   ```bash
   firebase login
   firebase init appdistribution
   ```

### CI/CD Workflow

The CI/CD pipeline is triggered on:
- Push to main branch
- Pull requests to main branch

The workflow includes:
1. Running tests and code analysis
2. Building Android and iOS applications
3. Deploying to Firebase App Distribution

## Development Guidelines

1. Always run tests before pushing:
   ```bash
   flutter test
   ```

2. Ensure code formatting:
   ```bash
   dart format .
   ```

3. Run code analysis:
   ```bash
   flutter analyze
   ```

## Deployment

The deployment process is automated through GitHub Actions. When code is merged to the main branch:
1. Tests are run
2. Applications are built
3. Apps are distributed to Firebase App Distribution
4. Testers are notified automatically

### Firebase App Distribution

The app is automatically distributed to testers through Firebase App Distribution:
- Android APK is distributed to Android testers
- iOS build is distributed to iOS testers
- Release notes are automatically generated
- Testers receive email notifications

## Contributing

1. Create a new branch for your feature
2. Make your changes
3. Run tests and ensure they pass
4. Create a pull request to main branch

## License

This project is licensed under the MIT License - see the LICENSE file for details.
