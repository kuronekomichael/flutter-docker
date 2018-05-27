# flutter-docker

Dockerfile for Flutter App Development

```
docker pull kuronekomichael/flutter:jenkins-slave
```

## Run flutter test

```bash
docker run -it kuronekomichael/flutter:jenkins-slave bash
```

```bash
git clone https://github.com/kuronekomichael/github-grass.git
cd github-grass/
flutter test
```

Sample output
```
$ flutter test
Running "flutter packages get" in github-grass...            9.2s
00:05 +0: loading /home/jenkins/github-grass/test/api_test.dart                                                                                        Shell: /usr/local/flutter/bin/cache/artifacts/engine/linux-x64/flutter_tester: error while loading shared libraries: libGLU.so.1: cannot open shared object file: No such file or directory
00:05 +0 -1: loading /home/jenkins/github-grass/test/api_test.dart [E]
  Failed to load "/home/jenkins/github-grass/test/api_test.dart":
  Shell subprocess crashed with unexpected exit code 127 before connecting to test harness.
  Test: /home/jenkins/github-grass/test/api_test.dart
  Shell: /usr/local/flutter/bin/cache/artifacts/engine/linux-x64/flutter_tester


00:05 +0 -2: loading /home/jenkins/github-grass/test/widget_test.dart [E]
  Failed to load "/home/jenkins/github-grass/test/widget_test.dart":
  Shell subprocess crashed with unexpected exit code 127 before connecting to test harness.
  Test: /home/jenkins/github-grass/test/widget_test.dart
  Shell: /usr/local/flutter/bin/cache/artifacts/engine/linux-x64/flutter_tester


Shell: /usr/local/flutter/bin/cache/artifacts/engine/linux-x64/flutter_tester: error while loading shared libraries: libGLU.so.1: cannot open shared object file: No such file or directory
Shell: /usr/local/flutter/bin/cache/artifacts/engine/linux-x64/flutter_tester: error while loading shared libraries: libGLU.so.1: cannot open shared object file: No such file or directory
00:05 +0 -3: loading /home/jenkins/github-grass/test/simple_test.dart [E]
  Failed to load "/home/jenkins/github-grass/test/simple_test.dart":
  Shell subprocess crashed with unexpected exit code 127 before connecting to test harness.
  Test: /home/jenkins/github-grass/test/simple_test.dart
  Shell: /usr/local/flutter/bin/cache/artifacts/engine/linux-x64/flutter_tester


00:05 +0 -3: Some tests failed.
```

## Run static code analyzer

```bash
docker run -it kuronekomichael/flutter:jenkins-slave bash
```

```bash
git clone https://github.com/kuronekomichael/github-grass.git
cd github-grass/
dartanalyzer .
```

Sample output
```
$ dartanalyzer .
Analyzing github-grass...
  lint • Avoid using braces in interpolation when not needed at lib/api/github.dart:15:50 • unnecessary_brace_in_string_interps
  lint • Avoid using braces in interpolation when not needed at lib/api/github.dart:42:50 • unnecessary_brace_in_string_interps
  lint • Avoid using braces in interpolation when not needed at lib/pages/home.dart:35:25 • unnecessary_brace_in_string_interps
  lint • Use => for short members whose body is a single return statement at lib/pages/home.dart:64:38 • prefer_expression_function_bodies
  lint • Avoid using braces in interpolation when not needed at lib/pages/home.dart:116:47 • unnecessary_brace_in_string_interps
  lint • Avoid using braces in interpolation when not needed at lib/pages/home.dart:123:22 • unnecessary_brace_in_string_interps
  lint • Use => for short members whose body is a single return statement at lib/pages/home.dart:134:74 • prefer_expression_function_bodies
7 lints found.
```
