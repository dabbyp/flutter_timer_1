# flutter_timer_1

- 뽀모도로 타이머 : 25초 일하고 5초 쉬는 타이머

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

- dependency
# pubspec.yaml
dependencies:
  flutter:
    sdk: flutter
  sprintf: "^6.0.0"
  fluttertoast: "^8.0.7"
  
## 프로젝트 구성
- main<br>
  lib/main.dart

  [home 화면 지정]<br>
  home: ListScreen()

- 화면<br>
  lib/screens/list_screen.dart<br>
  lib/screens/detail_screen.dart<br>
  
  [화면이동]<br>
  Navigator.of(context).push());<br>
  
  [화면 범위를 컨텐츠가 넘어설때 buffer overflow 에러 조치]<br>
  width: MediaQuery.of(context).size.width * 0.8,<br>

- 데이터<br>
  lib/model/book.dart<br>
  lib/repositories/book_repository.dart<br>
 
## 실행화면
- [https://dabbyp.github.io/api_samples/flutter_book_list/build/web/index.html](https://dabbyp.github.io/api_samples/flutter_book_list/build/web/index.html)
