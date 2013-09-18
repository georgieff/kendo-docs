---
title: Overview
meta_title: Summary of Kendo UI Button functionality
meta_description: Find out how to use the Kendo UI Button widget
slug: gs-web-button-overview
relatedDocs: api-web-button
tags: getting-started,web,button
publish: true
---

# Button Overview

The **Kendo UI Button** provides a styled clickable UI widget with arbitrary content.
Apart from consistent Kendo UI styling, the **Button** provides keyboard operability for elements, which natively don't have it (e.g. `span`).

It is assumed that the reader of this page is familiar with the [fundamental Kendo UI widget concepts](/getting-started/widgets).

## Getting Started

The **Button** widget can be initialized from any element with any content. However, using `button` or `a` elements is more reasonable.

The **Button** can include both inline and block elements, but one should take into account web standards, which prohibit placing block elements (e.g. `div`, `p`) inside inline elements (e.g. `a`, `span`).

Placing clickable elements with their own special behavior inside the **Button** (e.g. hyperlinks, textboxes, etc) may cause undesired side efects.

### Button initialization example

    <button type="button" id="refreshButton">Refresh</button>
	
	<script>
	$(function(){
		$("#refreshButton").kendoButton();
	});
	</script>


## Initializing multiple buttons

Although each **Button** represents a separate widget instance on the page, multiple Buttons can be initialized simultaneously.
There are two ways to do this - one is to use a jQuery selector, which returns multiple elements, or via `kendo.init()`.

### Multiple Buttons initialization with a jQuery selector

    <button type="button" class="myButton" id="editButton">Edit</button>
    <button type="button" class="myButton" id="deleteButton">Delete</button>
	<button type="button" class="myButton" id="addButton">Add</button>
	
	<script>
	$(function(){
		$(".myButton").kendoButton();
	});
	</script>

### Multiple Buttons initialization with kendo.init

This approach allows you to initialize multiple **Buttons** at once, but with different configuration options.
For more information, please refer to [Data Attribute Initialization](/getting-started/data-attribute-initialization) and [`kendo.init()` method description](/api/framework/kendo#methods-init).

	<div id="buttonsContainer">
		<button type="button" data-role="button" data-sprite-css-class="myEditIcon" id="editButton">Edit</button>
		<button type="button" data-role="button" data-enable="false" id="deleteButton">Delete</button>
		<button type="button" data-role="button" id="addButton">Add</button>
	</div>
	
	<script>
	$(function(){
		kendo.init("#buttonsContainer");
	});
	</script>

## Using Icons

The **Button** can accommodate an icon, which enhances the meaning of the text content.
The widget provides two ways to add an icon - with a classic `img` element or with a background image (usually a sprite).
From web standarts' point of view, using background images is better, because the icon does not represent structural content, but it's simply a decoration.

### Background icons

Background icons are applied via the `spriteCssClass` property and are displayed as a background of a `span` element.
This element can be rendered by the **Button** automatically, or an existing `span` element can be used, if it has a `k-sprite` CSS class.

#### Example

	<button type="button" id="editButton">Edit</button>
	<button type="button" id="deleteButton"><span class="k-sprite"></span>Delete</button>
	
	<script>
	
	$(function(){
		$("#editButton").kendoButton({
			spriteCssClass: "myEditIcon"
		});
		
		$("#deleteButton").kendoButton({
			spriteCssClass: "myDeleteIcon"
		});
	});
	
	</script>

In some cases you may want to use a **Button** with no text and only an icon inside.
In order to increase the accessibility of the **Button** in this case, a text label can be included inside the sprite `span`.

#### Example

	<button type="button" id="deleteButton"><span class="k-sprite">Delete</span></button>
	
	<script>
	
	$(function(){
		$("#deleteButton").kendoButton({
			spriteCssClass: "myDeleteIcon"
		});
	});
	
	</script>

### Image icons

Image icons are applied via the `imageUrl` property and are displayed as a `img` element.
This element can be rendered by the **Button** automatically, or an existing `img` element can be used, if it has a `k-image` CSS class.

#### Example

	<button type="button" id="editButton">Edit</button>
	<button type="button" id="deleteButton"><img class="k-image" alt="Delete" />Delete</button>
	
	<script>
	
	$(function(){
		$("#editButton").kendoButton({
			imageUrl: "/images/myEditIcon.gif"
		});
		
		$("#deleteButton").kendoButton({
			imageUrl: "/images/myDeleteIcon.gif"
		});
	});
	
	</script>

In order to increase the accessibility of the **Button** when adding an `img` element manually, an `alt` attribute is required.

## Enabled and Disabled buttons

The business logic of an application often requires a certain button to be temporarily disabled or enabled.
The **Button** can be configured to be initially disabled via its `enable` property or by initializing it from an element, which has a `disabled="disabled"` HTML attribute.
The **Button** can also be disabled or enabled at any time with Javascript by using its `enable()` method with a boolean argument.

### Example

	<button type="button" id="editButton">Edit</button>
	
	<script>
	
	$(function(){
		var editButton = $("#editButton").kendoButton({
			enable: false
		}).data("kendoButton");
		
		// ...
		
		// enable button
		editButton.enable(true);
	});
	
	</script>

For more information on the **Button** [`enable` property](/api/web/button#configuration-enable) and the [`enable` method](/api/web/button#methods-enable), please refer to the [Button API](/api/web/button/).

## Accessing the Button instance

Similar to all other Kendo UI widgets, an existing **Button** instance is accessed via the `.data()` jQuery method, executed by the jQuery object of the originating element.

### Example

	<button type="button" id="editButton">Edit</button>
	
	<script>
	
	$(function(){
		$("#editButton").kendoButton();
		
		var editButton = $("#editButton").data("kendoButton");
	});
	
	</script>

The `kendoButton()` method returns the same jQuery object that has been used to execute it.
That's why, if the **Button** will be accessed afterwards, it is a good idea to save it at the time of initialization.

### Example

	<button type="button" id="editButton">Edit</button>
	<button type="button" id="deleteButton">Delete</button>
	
	<script>
	
	$(function(){
		// save button element and then the button widget object
		var editButtonElement = $("#editButton").kendoButton();
		var editButton = editButtonElement.data("kendoButton");
		
		// save the button widget object and then retrieve the DOM element as a jQuery object
		var deleteButton = $("#editButton").kendoButton().data("kendoButton");
		var deleteButtonElement = deleteButton.element;
	});
	
	</script>

For further reading and related information, please refer to the [Button API](/api/web/button/).