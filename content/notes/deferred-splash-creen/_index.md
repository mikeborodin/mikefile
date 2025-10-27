+++
date = '2025-01-06T21:55:08+01:00'
draft = false
title = 'UX Friendly SplashScreen in Flutter'
showAuthor = true
+++

![feature](feature.jpg)


If you're targeting Android 12+ you can configure just a standard native splash screen and then use `deferFirstFrame` to instruct Flutter to start drawing. 

```dart
void main() async {
  final binding = WidgetsFlutterBinding.ensureInitialized();

  binding.deferFirstFrame();
  
  runApp(MyApp());
}
```

Somewhere in your code you can have a function similar to

```dart

// somewhere after your async initialization
void init(WidgetsFlutterBinding binding) async {
  await initializeAsyncDependencies();
  binding.allowFirstFrame();
}

```

This allows us to do avoid switching some screens during the initializaton (e.g. authentication state) and instead present ready loaded data to the user at once.
