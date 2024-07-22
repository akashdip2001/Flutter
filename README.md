# Flutter

Setup + create a "Hello World" apk. using Flutter:

### Step 1: Download and Install Android Studio

1. **Download Android Studio:**
   - Go to the [Android Studio download page](https://developer.android.com/studio).
   - Click on "Download Android Studio" and agree to the terms and conditions to start the download.

2. **Install Android Studio:**
   - Run the downloaded installer.
   - Follow the on-screen instructions to complete the installation.
   - During the installation, make sure to check the option to install the Android Virtual Device (AVD).

### Step 2: Set Up Flutter and Dart

1. **Download Flutter SDK:**
   - Go to the [Flutter download page](https://flutter.dev/docs/get-started/install).
   - Download the appropriate version for your operating system.

2. **Extract the Flutter SDK:**
   - Extract the downloaded Flutter SDK to a desired location on your computer.

3. **Add Flutter to Your Path:**
   - Add the `flutter/bin` directory to your system's PATH environment variable.

4. **Verify Installation:**
   - Open a terminal or command prompt.
   - Run `flutter doctor` to ensure everything is set up correctly.

### Step 3: Create a New Flutter Project

1. **Create a New Flutter Project:**
   - Open a terminal or command prompt.
   - Navigate to the directory where you want to create your project.
   - Run the following command to create a new Flutter project:
     ```sh
     flutter create hello_world
     ```

2. **Open the Project in Android Studio:**
   - Open Android Studio.
   - Select `Open an existing Android Studio project`.
   - Navigate to the `hello_world` directory and open it.

### Step 4: Modify the Flutter Project

1. **Edit the Main Dart File:**
   - In Android Studio, open the `lib/main.dart` file.
   - Replace the existing code with the following code:
     ```dart
     import 'package:flutter/material.dart';

     void main() {
       runApp(MyApp());
     }

     class MyApp extends StatelessWidget {
       @override
       Widget build(BuildContext context) {
         return MaterialApp(
           home: Scaffold(
             appBar: AppBar(
               title: Text('Hello World'),
             ),
             body: Center(
               child: Text('Hello World!'),
             ),
           ),
         );
       }
     }
     ```

### Step 5: Set Up an Emulator

1. **Create a Virtual Device:**
   - Go to `Tools` > `AVD Manager`.
   - Click on `Create Virtual Device`.
   - Select a device from the list (e.g., Pixel 4) and click `Next`.
   - Choose a system image (e.g., `R` for Android 11) and click `Next`.
   - Click `Finish` to create the virtual device.

2. **Start the Emulator:**
   - In the AVD Manager, click the play button next to the device you created to start the emulator.

### Step 6: Run the Flutter Project

1. **Run the Project:**
   - In Android Studio, click on the green play button or go to `Run` > `Run 'main.dart'`.
   - Select your emulator if it's not already selected.
   - Flutter will build the APK and launch it on the emulator.

### Step 7: Generate the APK

1. **Generate APK:**
   - Open a terminal or command prompt.
   - Navigate to your Flutter project directory (`hello_world`).
   - Run the following command to build the APK:
     ```sh
     flutter build apk --release
     ```

2. **Locate the APK:**
   - After the build is completed, the APK file will be located in `build/app/outputs/flutter-apk/app-release.apk`.

### apk file

Now you have a "Hello World" Flutter application. The APK file can be found in the `build/app/outputs/flutter-apk` directory of your project.

---

Sets up a directory structure for your application. Here’s an overview of the file structure you'll see in a typical Flutter project:

### Project Directory Structure

```
hello_world/
├── android/
├── build/
├── ios/
├── lib/
│   └── main.dart
├── test/
│   └── widget_test.dart
├── .gitignore
├── .metadata
├── pubspec.yaml
└── README.md
```

### Directory and File Descriptions

1. **android/**:
   - Contains the Android-specific code and configuration files. This directory is where you can make platform-specific changes if needed.
   - `build.gradle`, `AndroidManifest.xml`, etc.

2. **build/**:
   - This directory contains the output files of the build process. You generally don't need to interact with this directory directly.

3. **ios/**:
   - Contains the iOS-specific code and configuration files. Similar to the Android directory, this is where you can make platform-specific changes.
   - `Runner.xcodeproj`, `Info.plist`, etc.

4. **lib/**:
   - This is where your Dart code lives. The `main.dart` file is the entry point of your application.
   - `main.dart`: The main file containing the root of your Flutter application.

5. **test/**:
   - Contains the unit tests and widget tests for your application.
   - `widget_test.dart`: A basic test file to get you started with writing tests in Flutter.

6. **.gitignore**:
   - Specifies files and directories that should be ignored by Git.

7. **.metadata**:
   - Metadata about the Flutter project. Typically you don't need to modify this file.

8. **pubspec.yaml**:
   - A key file for your Flutter project. It manages the project's dependencies, assets, and more.
   - You define your dependencies (packages) and assets (images, fonts, etc.) here.

9. **README.md**:
   - A Markdown file where you can describe your project. This file is helpful for documentation purposes.

### Example of `pubspec.yaml` File

Here's an example content of the `pubspec.yaml` file:

```yaml
name: hello_world
description: A new Flutter project.

publish_to: 'none' # Remove this line if you wish to publish to pub.dev

version: 1.0.0+1

environment:
  sdk: ">=2.12.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter

  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.2

dev_dependencies:
  flutter_test:
    sdk: flutter

flutter:

  uses-material-design: true

  # To add assets to your application, add an assets section, like this:
  # assets:
  #   - images/a_dot_burr.jpeg
  #   - images/a_dot_ham.jpeg

  # An image asset can refer to one or more resolution-specific "variants", see
  # https://flutter.dev/assets-and-images/#resolution-aware.

  # For details regarding adding assets from package dependencies, see
  # https://flutter.dev/assets-and-images/#from-packages

  # To add custom fonts to your application, add a fonts section here,
  # in this "flutter" section. Each entry in this list should have a
  # "family" key with the family name, and a "fonts" key with a list
  # giving the asset and other descriptors for the font. For example:
  # fonts:
  #   - family: Schyler
  #     fonts:
  #       - asset: fonts/Schyler-Regular.ttf
  #       - asset: fonts/Schyler-Italic.ttf
  #         style: italic
  #   - family: Trajan Pro
  #     fonts:
  #       - asset: fonts/TrajanPro.ttf
  #       - asset: fonts/TrajanPro_Bold.ttf
  #         weight: 700
  #
  # For details regarding fonts from package dependencies,
  # see https://flutter.dev/custom-fonts/#from-packages
```

### Customizing the `main.dart` File

Here is the basic "Hello World" example in `lib/main.dart`:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Hello World'),
        ),
        body: Center(
          child: Text('Hello World!'),
        ),
      ),
    );
  }
}
```
