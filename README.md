# bzlmod-bash-runfiles-grep-warning-demo
Demonstration of Bazel's Bash runfiles library emitting warnings from grep.

## Demonstration command

```
❯ bazel run @dep//folder_with_@_symbol:hello_world
INFO: Analyzed target @dep~0.0.1//folder_with_@_symbol:hello_world (22 packages loaded, 83 targets configured).
INFO: Found 1 target...
Target @dep~0.0.1//folder_with_@_symbol:hello_world up-to-date:
  bazel-bin/external/dep~0.0.1/folder_with_@_symbol/hello_world
INFO: Elapsed time: 0.094s, Critical Path: 0.00s
INFO: 1 process: 1 internal.
INFO: Build completed successfully, 1 total action
INFO: Running command line: bazel-bin/external/dep~0.0.1/folder_with_@_symbol/hello_world dep~0.0.1/folder_with_@_symbol/hello.txt
grep: warning: stray \ before ~
grep: warning: stray \ before @
Hello World!
```

## Relevant software versions

```
❯ bazel version
Bazelisk version: v1.18.0
Aspect CLI version: 5.8.5
Build label: 6.4.0
Build target: bazel-out/k8-opt/bin/src/main/java/com/google/devtools/build/lib/bazel/BazelServer_deploy.jar
Build time: Thu Oct 19 17:07:43 2023 (1697735263)
Build timestamp: 1697735263
Build timestamp as int: 1697735263
```

```
❯ grep --version
grep (GNU grep) 3.8
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Written by Mike Haertel and others; see
<https://git.sv.gnu.org/cgit/grep.git/tree/AUTHORS>.
```
