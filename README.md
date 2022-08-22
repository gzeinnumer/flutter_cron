# flutter_cron

[cron](https://pub.dev/packages/cron)

```dart
cron: ^0.5.0
```
```
import 'package:cron/cron.dart';
```
```dart
final cron = Cron();

cron.schedule(Schedule.parse('*/3 * * * *'), () async {
    print('every three minutes');
});

cron.schedule(Schedule.parse('8-11 * * * *'), () async {
    print('between every 8 and 11 minutes');
});

cron.schedule(Schedule.parse('15 * * * *'), () async {
    print("This code runs every 15 minutes")
});

cron.schedule(Schedule.parse('00 00 * * *'), () async {
    print("This code runs at 12am everyday")
});
```
```
final cron = Cron();

try {
    cron.schedule(Schedule.parse('*/6 * * * * *'), () {
      print(DateTime.now());
    });

    await Future.delayed(Duration(seconds: 20));
    await cron.close();
} on ScheduleParseException {
    // "ScheduleParseException" is thrown if cron parsing is failed.
    await cron.close();
}
```

---

```
Copyright 2022 M. Fadli Zein
```