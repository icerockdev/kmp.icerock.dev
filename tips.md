# Kotlin Mobile Mutiplatform - tips

## Override iOS extensions methods in Kotlin
Methods like `UIView::layoutSubviews()` or `UIViewController::shouldAutorotate` in iOS SDK added into Objective-C Category (or Swift extension) and mapped in Kotlin as extension functions. In common case Kotlin not accept overriding of extension functions, but not in case of K/N ObjC interop.
This code
```kotlin
class MyView: UIView(frame = CGRectZero.readValue()) {

    override fun layoutSubviews() {
        super.layoutSubviews()

    }
}
```
in IDE, and in compilation, show errors:
- `'layoutSubviews' overrides nothing`
- `'super' is not an expression, it can not be used as a receiver for extension functions`

but it's just tooling bug, you can do suppress of errors and successful compile code:
```kotlin
class MyView: UIView(frame = CGRectZero.readValue()) {

    @Suppress("NOTHING_TO_OVERRIDE", "SUPER_CANT_BE_EXTENSION_RECEIVER")
    override fun layoutSubviews() {
        super.layoutSubviews()

    }
}
```

## Implement iOS protocol with same kotlin signature
Objective-C and Swift can have protocols like this:
```objective-c
@protocol WKNavigationDelegate <NSObject>

@optional

- (void)webView:(WKWebView *)webView didStartProvisionalNavigation:(WK_NULL_UNSPECIFIED WKNavigation *)navigation;
- (void)webView:(WKWebView *)webView didFinishNavigation:(WK_NULL_UNSPECIFIED WKNavigation *)navigation;

@end
```
for `Kotlin` it have one method signature - function name `webView` with two arguments `WKWebView` and `WKNavigation`. 
```kotlin
class NavigationDelegate: NSObject(), WKNavigationDelegateProtocol {

    override fun webView(webView: WKWebView, didStartProvisionalNavigation: WKNavigation?) { }

    override fun webView(webView: WKWebView, didFinishNavigation: WKNavigation?) { }
}
```
And IDE, compiler will be show error if you try implement both methods:
- `Conflicting overloads: public open fun webView(webView: WKWebView, didStartProvisionalNavigation: WKNavigation?): Unit defined in ...`
- `public open fun webView(webView: WKWebView, didFinishNavigation: WKNavigation?): Unit defined in ...`

To support this case you can use Suppress:
```kotlin
@Suppress("CONFLICTING_OVERLOADS")
class NavigationDelegate: NSObject(), WKNavigationDelegateProtocol {

    override fun webView(webView: WKWebView, didStartProvisionalNavigation: WKNavigation?) { }

    override fun webView(webView: WKWebView, didFinishNavigation: WKNavigation?) { }
}
```
