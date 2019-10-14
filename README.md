# gradle-showcase
## ear-platform
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

## custom configuration
the root cause seems to be a problem with non transitive configurations, see the `customConf` project
```
gradle show
Starting a Gradle Daemon, 1 incompatible and 1 stopped Daemons could not be reused, use --status for details
> Task :customConf:showNonTransitiveDeps FAILED

FAILURE: Build failed with an exception.

* Where:
Build file 'C:\Java\Sources\experimental\gradle-ear-platform\customConf\build.gradle' line: 17

* What went wrong:
Execution failed for task ':customConf:showNonTransitiveDeps'.
> Could not resolve all files for configuration ':customConf:nonTransitive'.
   > Could not find commons-lang:commons-lang:.
     Required by:
         project :customConf

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 12s
1 actionable task: 1 executed

```