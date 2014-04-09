---
title: kendo.mobile.Application
meta_title: Configuration and methods for Mobile Application widget
meta_description: How to hide the browser address bar, set the platform which will force on the application, hide/show a loading animation and more in Kendo UI Mobile Application widget.
slug: mobile-kendo.mobile.application
tags: api,mobile
publish: true
---

# kendo.mobile.Application

## Configuration

### hideAddressBar `Boolean`*(default: true)*

Whether to hide the browser address bar. Supported only in iPhone and iPod. Doesn't affect standalone mode as there the address bar is always hidden.

#### Example

    <div data-role="view"><a data-role="button">Foo</a></div>

    <script>
    new kendo.mobile.Application($(document.body), { hideAddressBar: false });
    </script>

### updateDocumentTitle `Boolean` *(default: true)*

Whether to update the document title.

#### Example

    <div data-role="view"><a data-role="button">Foo</a></div>

    <script>
    new kendo.mobile.Application($(document.body), { updateDocumentTitle: false });
    </script>

### initial `String`

The id of the initial mobile View to display.

#### Example

    <div data-role="view"><a data-role="button">Foo</a></div>

    <div data-role="view" id="bar"><a data-role="button">Bar</a></div>

    <script>
    new kendo.mobile.Application($(document.body), { initial: "#bar" });
    </script>

### layout `String`

The id of the default Application layout.

#### Example

    <div data-role="view">Bar</div>

    <div data-role="layout" data-id="foo">
      <div data-role="header">Header</div>
    </div>

    <script>
    new kendo.mobile.Application($(document.body), { layout: "foo" });
    </script>

### loading `String`*(default: "&lt;h1&gt;Loading...&lt;/h1&gt;")*

The text displayed in the loading popup. Setting this value to false will disable the loading popup.

 *Note*: The text should be wrapped inside `<h1>` tag.

#### Example

    <div data-role="view">Bar</div>

    <script>
    new kendo.mobile.Application($(document.body), {
        loading: "<h1>Please wait...</h1>"
    });
    </script>

### platform `String`

Which platform look to force on the application. Supported values are `"ios"` (meaning iOS 6 look), `"ios7"`,`"android"`, `"blackberry"` and `"wp"`.
You can also set platform variants with it (`"android-light"` or `"android-dark"`), but keep in mind that it will still override the platform. If this is not desired, use the `skin` option.

#### Example

    <div data-role="view">Bar</div>

    <script>
    new kendo.mobile.Application($(document.body), {
        platform: "android"
    });
    </script>

### serverNavigation `Boolean` **(default: false)**

If set to true, the application will not use AJAX to load remote views.

> Using this configuration option will affect the user experience, as blank screens will be visible between application states. As the page will be completely reloaded, the application state will not be transferred to the next view.

#### Example

    <div data-role="view">Bar <a data-role="button" href="another-view.html">Go to another page</a></div>

    <script>
    new kendo.mobile.Application($(document.body), { serverNavigation: true });
    </script>

### skin `String`

The skin to apply to the application. Currently, Kendo UI Mobile ships with a **flat** skin in addition to the native looking ones. You can also set platform variants with it ("android-light" or "android-dark").

> The skin setting will be applied on any device, making the application look the same way.

#### Example

    <div data-role="view"><a data-role="button">Foo</a></div>

    <script>
         new kendo.mobile.Application($(document.body), {
             skin: "flat"
         });
    </script>

### statusBarStyle `String`*(default: "black")*

Set the status bar style meta tag in iOS used to control the styling of the status bar in a pinned to the Home Screen app. Available as of Q2 2013 SP.

> The default setting of "black" pushes down the content of the page, while the rest overlay it. To create seamless status bar in iOS7,
check [Seamless Status Bar in iOS7](/kendo-ui/getting-started/mobile/application#seamless-status-bar-in-ios7) section in Mobile Application's Getting Started page.

#### Example

    <div data-role="view" id="foo"><a data-role="button" href="#bar">Bar</a></div>

    <script>
        new kendo.mobile.Application($(document.body), {
            statusBarStyle: "black"
        });
    </script>

### transition `String`

The default View transition.

#### Example

    <div data-role="view" id="foo"><a data-role="button" href="#bar">Bar</a></div>
    <div data-role="view" id="bar"><a data-role="button" href="#foo">Foo</a></div>

    <script>
    new kendo.mobile.Application($(document.body), { transition: "slide" });
    </script>

### webAppCapable `Boolean` **(default: true)**

Disables the default behavior of Kendo UI Mobile apps to be web app capable (open in a chromeless browser). Introduced in Q2 2013.

#### Example

    <div data-role="view" id="foo"><a data-role="button" href="#bar">Bar</a></div>

    <script>
    new kendo.mobile.Application($(document.body), { webAppCapable: false });
    </script>

##### pushState `Boolean` *(default: false)*

If set to true, the application router instance will use the [history pushState API](https://developer.mozilla.org/en-US/docs/Web/Guide/API/DOM/Manipulating_the_browser_history#The_pushState().C2.A0method).

> The history pushState API currently has [limited support accross current browsers](http://caniuse.com/#search=pushstate).

##### root `String` *(default: "/")*

Applicable if `pushState` is used and the application is deployed to a path different than `/`. If the application start page is hosted on `http://foo.com/myapp/`, the root option should be set to `/myapp/`.

##### options.hashBang `Boolean` *(default: false)*

Introduced in the 2014 Q1 Service Pack 1 release. If set to `true`, the navigation will parse and prefix the url fragment value with `!`,
which [should be SEO friendly](http://googlewebmastercentral.blogspot.com/2009/10/proposal-for-making-ajax-crawlable.html).

## Methods

### changeLoadingMessage

Changes the loading message.

#### Example

    <div data-role="view">
        <a data-role="button" data-click="showLoading">Show loading</a>
    </div>

    <script>
        var app = new kendo.mobile.Application();
        function showLoading() {
            app.showLoading();
            setTimeout(function() {
                app.changeLoadingMessage("Please wait...");
            }, 1000);
        }
    </script>

#### Parameters

##### text `String`

New text of the loading animation.

### hideLoading

Hide the loading animation.

#### Example

    <div data-role="view" id="foo"><a data-role="button" href="#bar">Bar</a></div>

    <script>
      var app = new kendo.mobile.Application();
      $(function() {
        app.showLoading();
        setTimeout(function() {
            app.hideLoading();
        }, 2000);
      });
    </script>

### navigate

Navigate to local or to remote view.

#### Navigate to a remote view

    <div data-role="view" id="foo"><a data-role="button" data-click="navigateToSettings">Bar</a></div>

    <script>
        var app = new kendo.mobile.Application();

        function navigateToSettings() {
            app.navigate("settings.html"); // the url of the remote view
        }
    </script>

#### Navigate to a local view

    <div data-role="view" id="foo"><a data-role="button" data-click="navigateToSettings">Bar</a></div>
    <div data-role="view" id="settings">Settings</div>

    <script>
        var app = new kendo.mobile.Application();

        function navigateToSettings() {
            app.navigate("#settings"); // the id of the local view
        }
    </script>

#### Navigate backwards to the previously visited mobile View

    <div data-role="view" id="foo"><a data-role="button" href="#settings">Bar</a></div>
    <div data-role="view" id="settings"><a data-role="button" data-click="goBack">Back</a></div>

    <script>
        var app = new kendo.mobile.Application();

        function goBack() {
            app.navigate("#:back");
        }
    </script>

#### Parameters

##### url `String`

The id or url of the view.

##### transition `String`

Optional. The transition to apply when navigating. See [View Transitions section](/kendo-ui/getting-started/mobile/application#view-transitions) for more information.

###### Example

    <div data-role="view" id="foo"><a data-role="button" data-click="navigateToSettings">Bar</a></div>
    <div data-role="view" id="settings">Settings</div>

    <script>
        var app = new kendo.mobile.Application();

        function navigateToSettings() {
            app.navigate("#settings", "slide");
        }
    </script>

### replace

Navigate to local or to remote view. The view will replace the current one in the history stack.

#### Parameters

##### url `String`

The id or url of the view.

##### transition `String`

Optional. The transition to apply when navigating. See [View Transitions section](/kendo-ui/getting-started/mobile/application#view-transitions) for more information.

###### Example

    <div data-role="view" id="foo">
        Foo
        <a href="#bar" data-role="button">Bar</a>
    </div>

    <div data-role="view" id="bar">
        <a data-role="button" data-click="replaceBar">Baz</a>
    </div>

    <div data-role="view" id="baz">
        <a data-role="backbutton">Back (will show Foo view)</a>
        Baz
    </div>

    <script type="text/javascript" charset="utf-8">
        function replaceBar() {
            kendo.mobile.application.replace("#baz");
        }

        new kendo.mobile.Application(document.body);
    </script>

### scroller

Get a reference to the current view's scroller widget instance.

#### Example

    <div data-role="view" id="foo"><div style="height: 1000px">Scroll a bit... </div><a data-role="button" data-click="resetScroller">Bar</a></div>

    <script>
        var app = new kendo.mobile.Application();

        function resetScroller() {
            app.scroller().reset();
        }
    </script>

#### Returns

`kendo.mobile.ui.Scroller` the scroller widget instance.

### showLoading

Show the loading animation.

#### Example

    <div data-role="view" id="foo"><a data-role="button" href="#bar">Bar</a></div>

    <script>
      var app = new kendo.mobile.Application();
      $(function() {
        app.showLoading();
        setTimeout(function() {
            app.hideLoading();
        }, 2000);
      });
    </script>

### skin

Change the current skin of the mobile application. When used without parameters, returns the currently used skin. Available as of Q2 2013.

#### Example

    <div data-role="view" id="foo"><a data-role="button" href="#bar">Bar</a></div>

    <script>
      var app = new kendo.mobile.Application();
      $(function() {
              app.skin("flat");
      });

    </script>

#### Parameters

##### skin `String`

The skin name to switch to or empty string ("") to return to native.

#### Returns

`String` Current skin in effect.

### view

Get a reference to the current view.

#### Example
    <div data-role="view" id="foo">
        <a id="button" data-role="button" data-click="logCurrentView">I am a mobile button</a>
    </div>

    <script>
        var app = new kendo.mobile.Application();
        function logCurrentView() {
            console.log(app.view()); // the foo mobile view instance
        }
    </script>

#### Returns

`kendo.mobile.ui.View` the view instance.

## Events

### init

Fires after the mobile application is instantiated.

#### Example

    <div data-role="view" id="foo">
        <a id="button" data-role="button" data-click="logCurrentView">I am a mobile button</a>
    </div>

    <script>
        var app = new kendo.mobile.Application(document.body, {
            init: function() {
                console.log("Kendo UI Mobile application is ready");
            }
        });
    </script>
