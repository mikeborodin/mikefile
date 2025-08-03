+++
date = '2025-01-06T21:55:08+01:00'
draft = false
title = 'Flutter vs Native - how to make a splash?'
showAuthor = true
+++

![feature](feature.jpg)




If you're targeting Android 12+  


```dart
void main() async {
  final binding = WidgetsFlutterBinding.ensureInitialized();

  binding.deferFirstFrame();
  
  runApp(MyApp());
}
```


```dart

// somewhere after your async initialization
void init(WidgetsFlutterBinding binding) async {
  await initializeAsyncDependencies();
  binding.allowFirstFrame();
}

```
