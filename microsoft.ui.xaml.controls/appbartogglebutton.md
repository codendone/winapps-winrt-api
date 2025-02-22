---
-api-id: T:Microsoft.UI.Xaml.Controls.AppBarToggleButton
-api-type: winrt class
---

<!-- Class syntax.
public class AppBarToggleButton : Windows.UI.Xaml.Controls.Primitives.ToggleButton, Windows.UI.Xaml.Controls.IAppBarToggleButton, Windows.UI.Xaml.Controls.IAppBarToggleButton3, Windows.UI.Xaml.Controls.ICommandBarElement, Windows.UI.Xaml.Controls.ICommandBarElement2
-->

# Microsoft.UI.Xaml.Controls.AppBarToggleButton

## -description

Represents a button control that can switch states and be displayed in an [AppBar](appbar.md).

## -xaml-syntax

```xaml
<AppBarToggleButton .../>
```

## -remarks

An AppBarToggleButton is similar to an [AppBarButton](appbarbutton.md) with an additional toggle state. When used inside a [CommandBar](commandbar.md). the visual appearance changes based on whether the control appears in the primary commands or the overflow menu. Here is an example of a toggled button as both a primary command and secondary command.

<img src="images/AppBarToggleButton_TwoModes.png" alt="App bar button icon examples." />

### Control style and template

You can modify the default [Style](../microsoft.ui.xaml/style.md) and [ControlTemplate](controltemplate.md) to give the control a unique appearance. For information about modifying a control's style and template, see [Styling controls](/windows/uwp/controls-and-patterns/styling-controls). The default style, template, and resources that define the look of the control are included in the generic.xaml file. For design purposes, generic.xaml is available in the \(Program Files)\Windows Kits\10\DesignTime\CommonConfiguration\Neutral\UAP\ &lt;SDK version&gt;\Generic folder from a Windows Software Development Kit (SDK) installation. Styles and resources from different versions of the SDK might have different values.

Starting in Windows 10, version 1607 (SDK 14393), generic.xaml includes resources that you can use to modify the colors of a control in different visual states without modifying the control template. In apps that target this software development kit (SDK) or later, modifying these resources is preferred to setting properties such as [Background](control_background.md) and [Foreground](control_foreground.md). For more info, see the [Light-weight styling](/windows/uwp/controls-and-patterns/styling-controls) section of the [Styling controls](/windows/uwp/controls-and-patterns/styling-controls) article.

This table shows the resources used by the AppBarToggleButton control.

<table>
   <tr><th>Resource key</th><th>Description</th></tr>
   <tr><td>AppBarToggleButtonBackground</td><td>Background color at rest</td></tr>
   <tr><td>AppBarToggleButtonBackgroundDisabled</td><td>Background color when disabled</td></tr>
   <tr><td>AppBarToggleButtonBackgroundChecked</td><td>Background color at rest and checked</td></tr>
   <tr><td>AppBarToggleButtonBackgroundCheckedPointerOver</td><td>Background color on hover and checked</td></tr>
   <tr><td>AppBarToggleButtonBackgroundCheckedPressed</td><td>Background color when pressed and checked</td></tr>
   <tr><td>AppBarToggleButtonBackgroundCheckedDisabled</td><td>Background color when disabled and checked</td></tr>
   <tr><td>AppBarToggleButtonBackgroundHighLightOverlay</td><td>Overlay background color at rest</td></tr>
   <tr><td>AppBarToggleButtonBackgroundHighLightOverlayPointerOver</td><td>Overlay background color on hover</td></tr>
   <tr><td>AppBarToggleButtonBackgroundHighLightOverlayPressed</td><td>Overlay background color when pressed</td></tr>
   <tr><td>AppBarToggleButtonBackgroundHighLightOverlayCheckedPointerOver</td><td>Overlay background color on hover and checked</td></tr>
   <tr><td>AppBarToggleButtonBackgroundHighLightOverlayCheckedPressed</td><td>Overlay background color when pressed and checked</td></tr>
   <tr><td>AppBarToggleButtonForeground</td><td>Label text color at rest</td></tr>
   <tr><td>AppBarToggleButtonForegroundPointerOver</td><td>Label text color on hover</td></tr>
   <tr><td>AppBarToggleButtonForegroundPressed</td><td>Label text color when pressed</td></tr>
   <tr><td>AppBarToggleButtonForegroundDisabled</td><td>Label text color when disabled</td></tr>
   <tr><td>AppBarToggleButtonForegroundChecked</td><td>Label text color at rest and checked</td></tr>
   <tr><td>AppBarToggleButtonForegroundCheckedPointerOver</td><td>Label text color on hover and checked</td></tr>
   <tr><td>AppBarToggleButtonForegroundCheckedPressed</td><td>Label text color when pressed and checked</td></tr>
   <tr><td>AppBarToggleButtonForegroundCheckedDisabled</td><td>Label text color when disabled and checked</td></tr>
   <tr><td>AppBarToggleButtonBorderBrush</td><td>Border color at rest</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushPointerOver</td><td>Border color on hover</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushPressed</td><td>Border color when pressed</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushDisabled</td><td>Border color when disabled</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushChecked</td><td>Border color at rest and checked</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushCheckedPointerOver</td><td>Border color on hover and checked</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushCheckedPressed</td><td>Border color when pressed and checked</td></tr>
   <tr><td>AppBarToggleButtonBorderBrushCheckedDisabled</td><td>Border color when disabled and checked</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForeground</td><td>Check mark color at rest (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundPointerOver</td><td>Check mark color on hover (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundPressed</td><td>Check mark color when pressed (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundDisabled</td><td>Check mark color when disabled (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundChecked</td><td>Check mark color at rest and checked (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundCheckedPointerOver</td><td>Check mark color on hover and checked (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundCheckedPressed</td><td>Check mark color when pressed and checked (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonCheckGlyphForegroundCheckedDisabled</td><td>Check mark color when disabled and checked (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonOverflowLabelForegroundPointerOver</td><td>Label text color on hover (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonOverflowLabelForegroundPressed</td><td>Label text color when pressed (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonOverflowLabelForegroundDisabled</td><td>Label text color when disabled (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonOverflowLabelForegroundCheckedPointerOver</td><td>Label text color on hover and checked (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonOverflowLabelForegroundCheckedPressed</td><td>Label text color when pressed and checked (in overflow)</td></tr>
   <tr><td>AppBarToggleButtonOverflowLabelForegroundCheckedDisabled</td><td>Label text color when disabled and checked (in overflow)</td></tr>
</table>

## -examples

> [!TIP]
> For more info, design guidance, and code examples, see [Command bar](/windows/uwp/controls-and-patterns/app-bars).

> [!div class="nextstepaction"]
> [Open the WinUI 3 Gallery app and see the AppBarToggleButton in action](winui3gallery:/item/AppBarToggleButton).

> The **WinUI 3 Gallery** app includes interactive examples of most WinUI 3 controls, features, and functionality. Get the app from the [Microsoft Store](https://www.microsoft.com/store/productId/9P3JFPWWDZRC) or get the source code on [GitHub](https://github.com/microsoft/WinUI-Gallery).

## -see-also

[Control](control.md), [AppBarToggleButton styles and templates](/windows/apps/design/style/xaml-styles), [AppBar](appbar.md), [AppBarButton](appbarbutton.md), [AppBarSeparator](appbarseparator.md), [CommandBar](commandbar.md), [ToggleButton](../microsoft.ui.xaml.controls.primitives/togglebutton.md), [Controls list](/windows/apps/design/controls/), [Controls by function](/windows/uwp/controls-and-patterns/controls-by-function), [Commanding sample (Windows 10)](https://github.com/Microsoft/Windows-universal-samples/tree/master/Samples/XamlCommanding)
