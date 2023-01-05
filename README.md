# flutter_timer_1

- 뽀모도로 타이머 : 25초 일하고 5초 쉬는 타이머

- dependency
# pubspec.yaml
```DART
dependencies:
  flutter:
    sdk: flutter
  sprintf: "^6.0.0"
  fluttertoast: "^8.0.7"
```

## 프로젝트 구성
- main<br>
  lib/main.dart
```DART
import 'package:flutter/material.dart';
import 'package:flutter_timer_1/screens/timer_screen.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: '뽀모도로 타이머',
      home: TimerScreen(),
    );
  }
}
```

- 화면<br>
  lib/screens/timer_screen.dart<br>
  

- 타이머 : aync
```DART
import dart:async;

void runTimer() async {
  Timer.periodic(Duration(seconds:1), (Timer t) {
    setState((){
      print("Timer is working");
      _timer -= 1;
    });
  });  
}
```

- Container : BoxDecoration BoxShape.circle

- enum Type : 
 enum TimerStatus = { running, paused, stopped, resting }
 실행시점에 type이 fix 됨
 int _timerStatus = TimerStatus.stopped;

- sprintf
```DART
import 'package:sprintf/sprintf.dart';

String secondsToString(int seconds){
  return sprintf("%02d:%02d", [seconds ~/ 60, seconds % 60]);
}
```
 
## 실행화면
- [https://dabbyp.github.io/flutter_timer_1/build/web/index.html](https://dabbyp.github.io/flutter_timer_1/build/web/index.html)
