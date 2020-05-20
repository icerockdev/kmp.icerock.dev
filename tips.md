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

# TODO
[Source](https://medium.com/xorum-io/kotlin-multiplatform-ready-steady-40b5c48abda6)
Kotlin/Native initialises global variables in alphabetical order, which is quite painful with Redux where you have store, middleware and reducers declared as global variables. As a workaround we needed to add z to package name of store to make sure it's initialised in the last turn.
Changing context in coroutines didn't work, at least with a CustomScope from kotlin-multiplatform-template, which we used. Removed all withContext calls from the common code.
For some reason === didn't work as expected within Kotlin/Native, even though printed addressed were the same. Changed them to ==.
Kotlin libraries aren't accessible in iOS code, if you add them as implementation in KMP module, which is expected. But if you add them as api all classes are prefixed with library name to prevent name clashing.
But your own classes aren't prefixed and sometimes you are trying to use the wrong class from iOS framework. Platform is one of such examples, which we needed to use as common.Platform at the end.
All classes should extend other classes or Any. Otherwise you will have messed up generics, which are limited even without this problem.
