# Flutter spreads its wings and goes multi-platform

Flutter is a great way to build mobile apps for iOS and Android from a single codebase. But did you know that Flutter is expanding beyond mobile to run on desktop and the web, too? In this talk, you will see where Flutter future is.

![Flutter Multi-platform](/images/flutter-multiplatform.png)

## Create Flutter Mobile Project from scratch

### Steps
- 


## From mobile to web

### Steps
- First create a flutter web project from vscode
- Copy the entire lib folder from mobile project to web project
- web/Assets folder should create from the scratch
 -> Create AssetManifest.json
 -> Create FontManifest.json 
 with all the images & fonts that you will user for the prohect.
 - Change references from main.dart
  from 
     import 'package:flutter/material.dart';
  to
      import 'package:flutter_web/material.dart';

- Change the to the web project (if it's neccessary):
  from 
      import 'package:heros/pages/hero_screen.dart';
  to
     import 'package:hummingbird/pages/hero_screen.dart';
- Change all the pages to the new references flutter_web instead of flutter


## From mobile to desktop

### Prerequisites

For Flutter to run on Desktop, we must be on the master channel, with the latest release. To ensure the same, fire up a terminal and run the following commands.

```
flutter channel master
flutter upgrade
```

Now if we run

```
flutter doctor
```

you can see:

![Flutter doctor console](/images/console-flutter-doctor.png)


For enable desktop , you should run:

On macOS or Linux:

```
export ENABLE_FLUTTER_DESKTOP=true
```

On Windows:
PowerShell:

```
$env:ENABLE_FLUTTER_DESKTOP="true"
```

CMD:

```
set ENABLE_FLUTTER_DESKTOP=true
```

Please note that this sets the environment variable for the current terminal session, hence we will be doing all the future steps in this terminal itself. Now, let’s run the following command to ensure that our system shows up.

```
flutter devices
```

### Steps
- Go to a terminar and run:
```
git clone https://github.com/google/flutter-desktop-embedding.git
cd example
flutter packages get
```

- Copy example folder like your desktop root project
- Change the name
- Delete "build" folder if exist
- Copy lib folder from mobile project to desktop project
- Replace from main.dart the following header:

import 'package:flutter/foundation.dart'
    show debugDefaultTargetPlatformOverride;
import 'package:flutter/material.dart';

void main() {
  // See https://github.com/flutter/flutter/wiki/Desktop-shells#target-platform-override
  debugDefaultTargetPlatformOverride = TargetPlatform.fuchsia;

  runApp(new MyApp());
}

- Replace the pubspec.yaml from desktop project with the pubspec.yaml from mobile project.
- Change to the correct name inside pubspec.yaml (the same that you wrote in the folder name)

## Tricks & Tips
- Install the plugin from VSCode make more easier to create mobile and web Flutter projects: https://flutter.dev/docs/development/tools/vs-code