# Airoute 

![totem](https://raw.githubusercontent.com/pdliuw/pdliuw.github.io/master/images/totem_four_logo.jpg)


亮点: ``Airoute:支持无需context的路由操作.``

[Airoute](https://github.com/pdliuw/flutter_route) 在[项目](https://github.com/flutter-app-sample/flutter_app_sample)中的实战应用[flutter sample](https://github.com/flutter-app-sample/flutter_app_sample)

## 1.安装

使用当前包作为依赖库

### 1. 依赖此库

在文件 'pubspec.yaml' 中添加

```

  # Route package.
  airoute:
    git:
      url: https://github.com/pdliuw/airoute.git

```

### 2. 安装此库

你可以通过下面的命令行来安装此库

```

$ flutter pub get


```

你也可以通过项目开发工具通过可视化操作来执行上述步骤

### 3. 导入此库

现在，在你的Dart编辑代码中，你可以使用：

```

import 'package:airoute/airoute.dart';

```

## 2.使用

### 1.在你的项目入口'main.dart'中配置：

Airoute 全局配置

```

void main() {
  runApp(
    ///
    /// 配置Airoute
    Airoute.createMaterialApp(
      home: LaunchPage(),
      routes: <String, AirouteBuilder>{
        "/LaunchPage": () => LaunchPage(),
        "/SecondPage": () => SecondPage(),
      },
    ),
  );
}


```


### 2.调用/应用

*1、跳转新页面

```

              Airoute.pushNamed(routeName: "/routeName");

```

*2、关闭页面

```

              Airoute.pop();

```

*3、跳转新页面，并添加动画

```

              Airoute.pushNamedWithAnimation(
                  routeName: "/routeName",
                  routePageAnimation: AirouteTransition.Slide);

```

*4、传递参数、接收参数

传递参数

```

              Airoute.pushNamed(
                routeName: "/Page",
                argument: "遇见你，我很开心😄😄😄",
              );

```

接收参数

```

class Page extends StatefulWidget with AirArgumentReceiver {

  @override
  State<StatefulWidget> createState() {
    return _PageState();
  }

  @override
  void receive(AirArgument argument) {
    print("收到${argument.argument}参数了,我很开心😄😄😄");
  }
}


```



## LICENSE

   Copyright 2019 pdliuw

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

