# gradle-showcase-ear-platform
Showing dependency management via BOM in ear projects

Building this project with gradle (5.5.1) results in the following error:
```
gradle assemble

> Task :ear:ear FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':ear:ear'.
> Could not resolve all files for configuration ':ear:deploy'.
   > Could not find commons-logging:commons-logging:.
     Required by:
         project :ear

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 3s
1 actionable task: 1 executed
```

the dependency in the ear should be managed but still the version is not resolved.
