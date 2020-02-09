# Kotlin Mobile Mutiplatform - tips

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
