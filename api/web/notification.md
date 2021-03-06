---
title: kendo.ui.Notification
meta_description: Configuration, methods and events of the Kendo UI Notification
slug: api-web-notification
relatedDocs: gs-web-notification-overview
tags: api,web,notification
publish: true
---

# kendo.ui.Notification

*It is assumed that the reader of this page is familiar with the [Notification widget Overview](/kendo-ui/getting-started/web/notification/overview/).*

## Configuration

### allowHideAfter `Number` *(default: 0)*

Indicates the period in milliseconds after which a notification can be dismissed (hidden) by the user.

#### Example - set allowHideAfter to 1 second

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		allowHideAfter: 1000
	});
	</script>

### animation `Object|Boolean`

Defines custom show and hide animations via an Kendo UI Animation object. Setting the value to false disables animations.

#### Example - disable animations

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		animation: false
	});
	</script>

### appendTo `String|Element|jQuery` *(default: null)*

Defines the element to which the notifications will be appended or prepended (depending on the [stacking](#configuration-stacking) direction).

#### Example - set appendTo as a selector string

	<span id="notification"></span>
    <div id="container"></div>
	<script>
	$("#notification").kendoNotification({
		appendTo: "#container"
	});
	</script>

#### Example - set appendTo as a DOM element

	<span id="notification"></span>
    <div id="container"></div>
	<script>
    var container = document.getElementById("container");
	$("#notification").kendoNotification({
		appendTo: container
	});
	</script>

#### Example - set appendTo as a jQuery object

	<div id="notification"></div>
	<script>
    var element = $("#notification");
	element.kendoNotification({
		appendTo: element
	});
	</script>

### autoHideAfter `Number` *(default: 5000)*

Indicates the period in milliseconds after which a notification disappears automatically. Setting a zero value disables this behavior.

#### Example - set autoHideAfter to 3 seconds

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		autoHideAfter: 3000
	});
	</script>

#### Example - disable automatic hiding

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		autoHideAfter: 0
	});
	</script>

### button `Boolean` *(default: false)*

Determines whether the notifications will include a hide button. **This setting works with the built-in templates only.**

#### Example - enable hide buttons

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		button: true
	});
	</script>

### height `Number|String` *(default: null)*

Defines the notifications' height. Numbers are treated as pixels.

#### Example - set height as a number

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		height: 50
	});
	</script>

#### Example - set height as a string

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		height: "4em"
	});
	</script>

### hideOnClick `Boolean` *(default: true)*

Determines whether notifications can be hidden by clicking anywhere on their content.

#### Example - disable hideOnClick

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		hideOnClick: false
	});
	</script>

### position `Object`

**This setting applies to popup notifications only, i.e. in cases when `appendTo` is not set.**
It determines the position of the first notification on the screen, as well as whether the notifications will move together with the page content during scrolling.
`top` takes precedence over `bottom` and `left` takes precedence over `right`.

#### Default position settings

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            pinned: true,
            top: null,
            left: null,
            bottom: 20,
            right: 20
        }
	});
	</script>

### position.bottom `Number` *(default: 20)*

Determines the pixel position of the first popup notification with regard to the viewport's bottom edge.

#### Example - set position.bottom

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            bottom: 30
        }
	});
	</script>

### position.left `Number` *(default: null)*

Determines the pixel position of the first popup notification with regard to the viewport's left edge.

#### Example - set position.left

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            left: 30
        }
	});
	</script>

### position.pinned `Boolean` *(default: true)*

Determines whether the popup notifications will move together with the other page content during scrolling.

#### Example - disable pinned notifications

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            pinned: false
        }
	});
	</script>

### position.right `Number` *(default: 20)*

Determines the pixel position of the first popup notification with regard to the viewport's right edge.

#### Example - set position.right

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            right: 30
        }
	});
	</script>

### position.top `Number` *(default: null)*

Determines the position of the first popup notification with regard to the viewport's top edge. Numeric values are treated as pixels.

#### Example - set position.top

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            top: 30
        }
	});
	</script>

### stacking `String` *(default: "default")*

Determines the direction in which multiple notification will stack (arrange) with regard to the first one. Possible values are `"up"`, `"right"`, `"down"`, `"left"` and `"default"`.
The `"default"` setting takes into consideration the applied `position` settings and is evaluated to `"up"` or `"down"`.

#### Example - set downward stacking

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		position: {
            top: 20,
            right: 20
        },
        stacking: "down"
	});
	</script>

### templates `Array` *(default: [])*

Describes the HTML markup of the different notification types as Kendo UI template strings. The built-in types are `"info"`, `"success"`, `"warning"` and `"error"`.

*This documentation section assumes that you are familiar with [Kendo UI templates](/kendo-ui/getting-started/framework/templates/overview)*.

#### Example - define several custom templates

    <span id="notification"></span>
	
    <script id="myAlertTemplate" type="text/x-kendo-template">
        <div class="myAlert">System alert generated at #= time # : #= myMessage #</div>
    </script>
    
	<script>
	$(function(){
        var notificationElement = $("#notification");
        
		notificationElement.kendoNotification({
            templates: [{
                    // define a custom template for the built-in "warning" notification type
                    type: "warning",
                    template: "<div class='myWarning'>Warning: #= myMessage #</div>"
                }, {
                    // define a template for the custom "timeAlert" notification type
                    type: "timeAlert",
                    template: "<div class='myAlert'>System alert generated at #= time # : #= myMessage #</div>"
                    // template content can also be defined separately
                    //template: $("#myAlertTemplate").html()
            }]
        });
        
        var n = notificationElement.data("kendoNotification");
        
        // show a warning message using the built-in shorthand method
        n.warning({
            myMessage: "some warning message here"
        });
        
        // show a "timeAlert" message using the default show() method
        n.show({
            time: new Date().toLocaleTimeString(),
            myMessage: "Server will be restarted."
        }, "timeAlert");
	});
	</script>

### templates.type `String` *(default: "")*

**Required.** Specified a unique identifier, which is used to retrieve the correct template when a notification of this type is shown.

See the [example above](#configuration-templates).

### templates.template `String` *(default: "")*

Defines a Kendo UI template to be used with the corresponding notification type.

See the [example above](#configuration-templates).

### width `Number|String` *(default: null)*

Defines the notifications' width. Numbers are treated as pixels.

#### Example - set width as a number

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		width: 300
	});
	</script>

#### Example - set width as a string

	<span id="notification"></span>
	<script>
	$("#notification").kendoNotification({
		width: "20em"
	});
	</script>

## Methods

### error

This is a shorthand method for [`show(data, "error")`](#methods-show)

### getNotifications

Returns a jQuery collection of all visible notifications, displayed by the given widget instance. Each item in the collection is a `div.k-notification` element.

#### Example

	<span id="notification"></span>
	<script>
	var notificationWidget = $("#notification").kendoNotification({
        button: false,
        hideOnClick: false,
        autoHideAfter: 0
    }).data("kendoNotification");
    
    notificationWidget.show("foo");
    notificationWidget.show("bar");
    
    // since there is no way for the user to hide notifications,
    // the following expression will return two elements, no matter when it is executed
    var elements = notificationWidget.getNotifications();
	</script>

### hide

Hides all notifications from the given widget instance.

#### Example

	<span id="notification"></span>
	<script>
	var notificationWidget = $("#notification").kendoNotification().data("kendoNotification");
    
    notificationWidget.show("foo");
    notificationWidget.show("bar");
    
    notificationWidget.hide();
	</script>

### info

This is a shorthand method for [`show(data, "info")`](#methods-show)

### show

Displays a notification.

#### Parameters

##### data `Object|String|Function`

**Required**. The string content for the notification; or the object with the values for the variables inside the notification template; or the function, which returns the required string or an object.

##### type `String`

The notification type. Built-in types include `"info"`, `"success"`, `"warning"` and `"error"`. Custom types should match the types from the [template configuration](#configuration-templates).
If this argument is not supplied, then `"info"` is assumed.

#### Example - use the show method with a string argument

	<span id="notification"></span>
	<script>
	var notificationWidget = $("#notification").kendoNotification().data("kendoNotification");
    
    notificationWidget.show("foo text", "warning");
	</script>

#### Example - use the show method with an object argument

	<span id="notification"></span>
	<script>
	var notificationWidget = $("#notification").kendoNotification({
        templates: {
            myAlert: "<div>System alert: #= myMessage #</div>"
        }
    }).data("kendoNotification");
    
    notificationWidget.show({ myMessage: "foo text" }, "myAlert");
	</script>

#### Example - use the show method with a function argument

	<span id="notification"></span>
	<script>
    function getNotificationMessage() {
        return {
            myMessage: "foo text"
        }
    }
    
	var notificationWidget = $("#notification").kendoNotification({
        templates: {
            myAlert: "<div>System alert: #= myMessage #</div>"
        }
    }).data("kendoNotification");
    
    notificationWidget.show(getNotificationMessage, "myAlert");
	</script>

### success

This is a shorthand method for [`show(data, "success")`](#methods-show)

### warning

This is a shorthand method for [`show(data, "warning")`](#methods-show)

## Events

### hide

Fires when a notification's hiding animation starts.

#### Event Data

##### e.element `jQuery`

The jQuery object, which wraps the element being hidden.

#### Example - subscribe to the "hide" event during initialization

	<span id="notification"></span>
	<script>
    
    function onHide(e) {
        var elementBeingHidden = e.element;
    }
    
	$("#notification").kendoNotification({
		hide: onHide
	});
	</script>

### show

Fires when a notification's showing animation starts.

#### Event Data

##### e.element `jQuery`

The jQuery object, which wraps the element being displayed.

#### Example - subscribe to the "show" event during initialization

	<span id="notification"></span>
	<script>
    
    function onShow(e) {
        var elementBeingShown = e.element;
    }
    
	$("#notification").kendoNotification({
		show: onShow
	});
	</script>