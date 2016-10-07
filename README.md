### SampleBridgingProject

This is a sample project, including bridging between Objective-C and Swift, in order to confirm that code completion works.

See http://stackoverflow.com/questions/39905349/bridging-swift-and-objective-c-not-working-completely.

The process to create this project was:

1. Create blank iOS Objective-C app and called it `SampleBridgingProject`.

2. Add Swift class, `Foo`, as a subclass of `NSObject`. When prompted, I chose to add the briding header.

3. Add `SampleBridgingProject.pch` to project.

4. Add following `#import` to the `pch` file:

        #import "SampleBridgingProject-Swift.h"

5. Went to target settings and set the "Build Setting" of "Prefix Header" to "`SampleBridgingProject/SampleBridgingProject.pch`"

6. Added method to `Foo.swift`:

        func sampleMethod(string: String) {
            print("sampleMethod: \(string)")
        }

7. Build project. Make sure there are no errors.

8. Go to view controller's `viewDidLoad` and try to write code that uses `Foo` and see if you enjoy code completion:

        Foo *foo = [[Foo alloc] init];
        [foo sampleM...

When I go through those steps, I experience code completion of Swift method in Objective-C. 

---

&copy; 2016. Robert M. Ryan. All Rights Reserved.<br />
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
