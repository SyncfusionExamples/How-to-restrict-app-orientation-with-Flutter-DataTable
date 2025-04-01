# How to restrict app orientation with Flutter DataTable (SfDataGrid)?

In this article, we will show you how to restrict app orientation with [Flutter DataTable](https://www.syncfusion.com/flutter-widgets/flutter-datagrid).

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) with the necessary properties. To restrict the app orientation when using SfDataGrid, we use [SystemChrome.setPreferredOrientations](https://api.flutter.dev/flutter/services/SystemChrome/setPreferredOrientations.html). First, we ensure that Flutter bindings are initialized with [WidgetsFlutterBinding.ensureInitialized()](https://api.flutter.dev/flutter/widgets/WidgetsFlutterBinding/ensureInitialized.html), then call SystemChrome.setPreferredOrientations([DeviceOrientation.portraitUp]) to lock the app in portrait mode. This ensures that the app remains in the specified orientation before launching with runApp(MyApp());. If the orientation needs to be restricted for a specific page (e.g., MyHomePage), we override [didChangeDependencies](https://api.flutter.dev/flutter/widgets/State/didChangeDependencies.html) in a StatefulWidget and reset it in [dispose()](https://api.flutter.dev/flutter/widgets/State/dispose.html).

```dart
void main() {
  // Ensure Flutter binding is initialized.
  WidgetsFlutterBinding.ensureInitialized(); 
  SystemChrome.setPreferredOrientations([
    DeviceOrientation.portraitUp,
  ]).then((_) {
    runApp(MyApp());
  });
}
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-restrict-app-orientation-with-Flutter-DataTable).