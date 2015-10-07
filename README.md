Android Gradle plugin bug report

Summary: 
Missing META-INF directory in resulting jar when building release version with minifyEnabled=true

Expected result:
When the library project is built using `assembleRelease`, the resulting classes.jar (inside the aar) should contain the `src/main/resources/META-INF` folder

Actual result:
When running `assembleRelease`, the resulting jar does not contain the `META-INF` folder at all. However, when running the task WITHOUT proguard, the folder is added to the jar as expected. 
We also tried to add `-keepdirectories META-INF/**` but it had no effect.

Steps to reproduce:
1, Run `assemble` on the project
2, Check build/outputs/aar/mylibrary-release.aar/classes.jar
3, The META-INF folder is missing (its there for the debug aar)

Versions:
-Java: JRE 1.7.0_45
-OS: OSX 10.9.5

Associated issue:
https://code.google.com/p/android/issues/detail?id=188994&thanks=188994&ts=1444217495



