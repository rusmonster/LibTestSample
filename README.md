**Issue:** Can't run instrumentation tests in firebase test lab for an android library

**Reproducable:** 100%

**Steps:**
1. Create Empty project in android studio (app without activity)
2. Add library module (call it samplelibrary for instance)
3. Goto "project structure" dialog and remove module "app"
4. Check that the test samplelibrary/src/androidTest/java/com/example/dkalita/samplelibrary/ExampleInstrumentedTest.java runs successfully on emulator
5. Goto "run/debug configurations" dialog and setup target to firebase (see screenshot) for the ExampleInstrumentedTest
6. Try to run the ExampleInstrumentedTest in firebase test lab
7. Error occurred with following logs:
```
Testing started at 13:37 ...
Using Cloud Storage Bucket location test-lab-wihxtbfzx92uw-mi6ii0hb5n3m2/as-build_2019-08-07_13:37:29.389_TrbZ ...
Uploading app APK ...
Uploading test APK ...
Submitting tests to Firebase Test Lab ...
Validating APKs ...

You can also view test results, along with other runs against this app, on the web:
 

Samsung Galaxy Note 8 (SM-N950F), Samsung | Android Q beta, API Level 28 (Q) | English | Portrait
	Infrastructure Failure: Internal error during validation
Pixel 2, Google, Virtual | Android 9.x, API Level 28 (Pie) | English | Portrait
	Infrastructure Failure: Internal error during validation
Pixel 2, Google, Virtual | Android Q beta, API Level 28 (Q) | English | Portrait
	Infrastructure Failure: Internal error during validation
Samsung Galaxy Note 8 (SM-N950F), Samsung | Android 9.x, API Level 28 (Pie) | English | Portrait
	Infrastructure Failure: Internal error during validation
Test running failed: No test results
Finish

Pricing information: https://firebase.google.com/pricing 
```

**Environment:**
Android Studio 3.4.2
MacOS 10.14.6

**Additional info:** 
- It looks like FTL expected app apk, but receives aar instead. Then validation fails.
