# Solanum2

Starter project for ["iOS UI Testing with KIF"](http://www.raywenderlich.com/61419/ios-ui-testing-with-kif) tutorial, updated for Xcode 6.4 and iOS 8.4.1.

1. Started from a clean single-view app template
2. Copied over the main app files
3. Manually transfered `import` statments that had been in the old precompiled header file
4. Supplied missing app icons to address warnings
5. Added KIF via Cocoapods

To complete the tutorial, I needed to...
- Open "Solanum2.xcworkspace" instead of "Solanum2.xcproject" (for Cocoapods)
- Add test files to group "Solanum2Tests" instead of "UI Tests"
- Add `#import <KIF/KIF.h>` to the top of "UITests.m"
- Replace `STAssert` with `XCTAssert` everywhere in the tutorial (but change `STAssertEqualsWithAccuracy` to `XCTAssertEqualWithAccuracy`)
- Use `tapRowAtIndexPath:inTableViewWithAccessibilityIdentifier:` instead of `tapRowInTableViewWithAccessibilityLabel:atIndexPath:` (deprecated) to tap a specific table row. This required setting `setAccessibilityIdentifier:` in addition to `setAccessibilityLabel:` in "PresetsViewController.m".

I also noticed that no automation played when only a `beforeAll` method was present.
