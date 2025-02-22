---
-api-id: M:Microsoft.UI.Xaml.Input.FocusManager.TryFocusAsync(Microsoft.UI.Xaml.DependencyObject,Microsoft.UI.Xaml.FocusState)
-api-type: winrt method
---

<!-- Method syntax.
public IAsyncOperation<FocusMovementResult> FocusManager.TryFocusAsync(DependencyObject element, FocusState value)
-->

# Microsoft.UI.Xaml.Input.FocusManager.TryFocusAsync

## -description

Asynchronously attempts to set focus on an element when the application is initialized. 

## -parameters

### -param element

The object on which to set focus.

### -param value

One of the values from the [FocusState](/windows/winui/api/microsoft.ui.xaml.focusstate) enumeration that specify how an element can obtain focus.

## -returns

The [FocusMovementResult](focusmovementresult.md) that indicates whether focus was successfully set.

## -remarks

Some objects, such as a [WebView](/uwp/api/windows.ui.xaml.controls.webview), can run in either the app process or in a separate process (see [WebViewExecutionMode.SeparateProcess](/uwp/api/windows.ui.xaml.controls.webviewexecutionmode)).

When an object runs in the app process, the following focus events occur as expected for both the previously focused object and the newly focused object:

- [GettingFocus](../microsoft.ui.xaml/uielement_gettingfocus.md)
- [LosingFocus](../microsoft.ui.xaml/uielement_losingfocus.md)
- [GotFocus](../microsoft.ui.xaml/uielement_gotfocus.md)
- [LostFocus](../microsoft.ui.xaml/uielement_lostfocus.md)

However, if the newly focused object is running in a separate process some of these event behaviors can differ. 

- [GetFocusedElement](focusmanager_getfocusedelement_1183614552.md) does not return the newly focused object until the TryFocusAsync operation completes. 
- The control losing focus receives its [LosingFocus](../microsoft.ui.xaml/uielement_losingfocus.md) event synchronously, but does not receive [LostFocus](../microsoft.ui.xaml/uielement_lostfocus.md) until the asynchronous operation completes. 
- The control getting focus receieves its [GettingFocus](../microsoft.ui.xaml/uielement_gettingfocus.md) event synchronously, but does not receive [GotFocus](../microsoft.ui.xaml/uielement_gotfocus.md) until the asynchronous operation completes. 
 
TryFocusAsync completes synchronously when called on an element running in the app process. 
 
## -examples

Here, we show how to set focus on a WebView object, and, if that fails, restore focus to the original element. 

```csharp
async void MoveFocus(WebView webView)) 
{ 
    FocusMovementResult result; 
    result = await FocusManager.TryFocusAsync(webView, FocusState.Programmatic); 
    if (!result.Succeeded) 
    { 
        // Restore focus to original element. 
        this.Focus(FocusState.Programmatic); 
    } 
}
```

## -see-also

[Keyboard interactions](/windows/apps/design/input/keyboard-interactions), [Focus navigation for keyboard, gamepad, remote control, and accessibility tools](/windows/apps/design/input/focus-navigation), [Programmatic focus navigation](/windows/apps/design/input/focus-navigation-programmatic)
