为了整合此类库与TOwebviewcontroller，对这个类库做了一些修改和定制。

TOwebviewcontroller中toolBar的按钮图片是coreGraphics画的，才用它画的那个，不使用原来的素材图片方式。

浏览器Activity也采用TO的，之前的activity非常多且并不实用。一般只要在Safari打开目标页就Ok的，在其他浏览器暂时不支持没有关系。

另外的一些修改，比如present modally时，导航栏右侧的done btn 的添加流程，这个修改的整合这两个类库的工程中https://github.com/github641/WebViewCompatible

DZNWebViewController 3.0
================
[![Pod Version](http://img.shields.io/cocoapods/v/DZNWebViewController.svg)](https://cocoadocs.org/docsets/DZNWebViewController)
[![License](http://img.shields.io/badge/license-MIT-blue.svg)](http://opensource.org/licenses/MIT)

An iPhone/iPad web browser built on top of WebKit with navigation controls and contextual features, useful for in-app web browsing.
Designed to be subclassed and extended.

![DZNWebViewController](Docs/DZNWebViewController_screenshot.png)

### Features
* Load HTTP links or local HTML.
* Navigation tools: backward/foward/stop/reload.
* Back/forward History (optional).
* Dragging gestures for back/forward, like Safari app.
* Progress bar embeded on the navigation bar or activity indicator (optional).
* Hide top and bottom bars when scrolling, like Safari app (optional).
* Contextual features: share link, copy link, read later.
* Open in Safari, Chrome, Opera Mini & Dolphin.
* Customizable toolbar icons.

### Supports
* Portrait/Landscape
* Localization
* iPhone/iPad
* Retina & iPad6+ displays
* iOS8 only
* ARC

## Installation
Available in [CocoaPods](http://cocoapods.org/?q=DZNWebViewController)
```ruby
pod 'DZNWebViewController'
```

If you're importing the source files manually, you must add the `WebKit` framework to your project.

## How to use

Create a new instance of DZNWebViewController, or your custom subclass, and initialize it with a NSURL.
You MUST embed the view controller into a UINavigationController to make it work properly.
```objc
NSURL *URL = [NSURL URLWithString:@"http://www.google.com/"];

DZNWebViewController *WVC = [[DZNWebViewController alloc] initWithURL:URL];
UINavigationController *NC = [[UINavigationController alloc] initWithRootViewController:WVC];

WVC.supportedWebNavigationTools = DZNWebNavigationToolAll;
WVC.supportedWebActions = DZNWebActionAll;
WVC.webNavigationPrompt = DZNWebNavigationPromptAll;
WVC.showLoadingProgress = YES;
WVC.allowHistory = YES;
WVC.hideBarsWithGestures = YES;

[self presentViewController:NC animated:YES completion:NULL];
```

## License
(The MIT License)

Copyright (c) 2014 Ignacio Romero Zurbuchen <iromero@dzen.cl>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
