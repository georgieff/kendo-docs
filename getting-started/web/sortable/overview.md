---
title: Overview
meta_title: Documentation for Sortable widget in Kendo UI framework
meta_description: How to use the Sortable widget.
slug: gs-web-sortable-overview
relatedDocs: api-web-sortable
tags: getting-started, web
publish: true
---

# Sortable Overview

The **Sortable** widget makes a group of DOM elements sortable by dragging and dropping with mouse/finger.

## Getting Started

### Initialize the Sortable using a jQuery selector

    <ul id="sortable">
        <li>Item1</li>
        <li>Item2</li>
        <li>Item3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable();
    </script>

You can reference an existing **Sortable** instance via
[jQuery.data()](http://api.jquery.com/jQuery.data/).

### Accessing an existing Sortable instance

    var sortable = $("#sortable").data("kendoSortable");

## Placeholder

Placeholder is the element which indicates where the dragged item will be placed after drop. By default the placeholder is a clone of the dragged element with removed `id` attribute and visibility set to hidden. Developer have the ability to change the default placeholder though the `placeholder` configuration option.

> **Important** Placeholder element is appended to the Sortable's DOM element. This is why jQuery's `index` method might return incorrect results. When the developer wants to find the index of a given item inside the Sortable collection it is recommended to use widget's [`indexOf`](../../../api/web/sortable#methods-indexof) method.

### Set the placeholder to a function

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>
    
    <script>
        $("#sortable").kendoSortable({ 
            placeholder: function(element) {
                return element.clone().css({
                    "opacity": 0.3,
                    "border": "1px dashed #000000"
                });
            }
        });
    </script>

### Set the placeholder to a string

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>
    
    <script>
        $("#sortable").kendoSortable({ 
            placeholder: "<li>Drop Here!</li>"
        });
    </script>

## Hint

Hint is the element which represents the dragged. By default the hint is a clone of the dragged. Developer have the ability to change the default hint though the `hint` configuration option.

> **Important** Hint element is appended to the `<body>` element. This might cause styling issues if the CSS rules are applied only to the Sortable's element.

### Set the hint to a function

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>
    
    <script>
        $("#sortable").kendoSortable({ 
            hint: function(element) {
                return $("<span></span>")
                        .text(element.text())
                        .css("color", "#FF0000");
            }
        });
    </script>

### Set the hint to a string

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>
    
    <script>
        $("#sortable").kendoSortable({ 
            hint: "<span>hint!</span>"
        });
    </script>

### Disabling the hint

The Sortable widget can operate without hint. To disable the hint you should set it to an empty function ([jQuery.noop](http://api.jquery.com/jQuery.noop/)).

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>
    
    <script>
        $("#sortable").kendoSortable({ 
            hint: $.noop
        });
    </script>

## Filter/Disable items

The **filter** option specifies which items inside the Sortable's element will be sortable. Items that does not match the filter selector will not be draggable nor reordered when user drags a sortable item over them.

The **disabled** option specifies which items inside the Sortable's element cannot be dragged. Items that match the disabled selector cannot be dragged but will reorder when user drags a sortable item over them.

### Disable all items at runtime

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <button id="btnDisable">Disable</button>
    
    <script>
        $("#sortable").kendoSortable({ 
            disabled: ".disabled"
        });

        $("#btnDisable").click(function() {
            $("#sortable").children().addClass("disabled");
        });
    </script>

## Cursor

Sortable widget provides `cursor` configuration options that is used to specify the cursor that will be shown while user drags sortable item. There are a variety of cursor types you can choose from that are built into the browser or operating system of the user's computer (you can see a list of them on [quirksmode.org](http://quirksmode.org/css/user-interface/cursor.html). Here's an example of how to change the cursor:

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({
            cursor: "move"
        });
    </script>

> Cursor option changes the cursor style only during item dragging. If the developer wants to change the on hover cursor he/she should use CSS.

If a cursor that is not supported by default, or not supported across all browsers, you have the option to include a custom cursor image.

### Example - grab/grabbing cursor

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({
            cursor: "url('http://demos.telerik.com/kendo-ui//content/web/sortable/grabbing.cur'), default"
        });
    </script>

    <style>
        #sortable li {
            cursor: url('http://demos.telerik.com/kendo-ui//content/web/sortable/grabbing.cur'), default;
        }
    </style>

## Movement by axis

By default the widget uses mouse cursor to determine the drop target before/after which sorted item should be placed. This means that if the mouse cursor is not over the target sortable element the placeholder will not be re-positioned.

If the `axis` is set to "x" or "y" however, the widget will start operating in movement by axis mode - the widget will use x/y position of the mouse cursor to determine the current target. To see this feature in action please check [constraints demo page](http://demos.telerik.com/kendo-ui/web/sortable/constraints.html).

## Integration with other Kendo UI Widgets

### Grid

**Sortable widget** gives the ability to the user to sort the Grid's table rows via drag and drop with the mouse.

>**Important:** Sortable widget reorders HTML DOM elements. It will not update automatically the position of the item in the DataSource. It is responsibility of the developer to update the data.

Sortable widget should be initialized for Grid's [`table element`](../../../api/web/grid#fields-table). In the general case filter property of the widget should select all `tr` elements that are direct children of the table's `tbody` element.

> In case Grid's editing is enabled the developer should use a more specific filter selector that excludes the item which is currently in edit mode. For example `.filter(">tbody >tr:not(.k-grid-edit-row)"`. In this way the Sortable functionality will not interfere with Grid's editing feature.

    $("#grid").data("kendoGrid").table.kendoSortable({
        filter: ">tbody >tr", //set the filter
        hint: function(element) { //customize the hint
            var grid = $("#grid").data("kendoGrid"),
                table = grid.table.clone(), //clone Grid's table
                wrapperWidth = grid.wrapper.width(), //get Grid's width
                wrapper = $("<div class='k-grid k-widget'></div>").width(wrapperWidth),
                hint;

            table.find("thead").remove(); //remove Grid's header from the hint
            table.find("tbody").empty(); //remove the existing rows from the hint
            table.wrap(wrapper); //wrap the table
            table.append(element.clone()); //append the dragged element

            hint = table.parent(); //get the wrapper

            return hint; //return the hint element
        },
        placeholder: function(element) { //customize the placeholder
            return element.clone().addClass("k-state-hover").css("opacity", 0.65);
        },
        change: function(e) {
            //handle the change event
            //update the underlying data according to the DOM position change
        }
    });

For more information check [Sortable's events](../../../api/web/sortable#events) and Grid integration [demo page](http://demos.telerik.com/kendo-ui/web/sortable/integration-grid.html).

### ListView

**Sortable widget** gives the ability to the user to sort the ListView's items via drag and drop with the mouse.

>**Important:** Sortable widget reorders HTML DOM elements. It will not update automatically the position of the item in the DataSource. It is responsibility of the developer to update the data.

Sortable widget should be initialized for ListView's element. In the general case filter property of the widget should select all elements that are direct children of the ListView's element.

> In case ListView's editing is enabled the developer should use a more specific filter selector that excludes the item which is currently in edit mode. For example `.filter(">div:not(.k-edit-item)"`. In this way the Sortable functionality will not interfere with ListView's editing feature.

For more information check [Sortable's events](../../../api/web/sortable#events) and ListView integration [demo page](http://demos.telerik.com/kendo-ui/web/sortable/integration-listview.html).

### TabStrip

**Sortable widget** gives the ability to the user to sort the TabStrip's tab via drag and drop with the mouse.

Sortable widget should be initialized for TabStrip's `ul.k-tabstrip-items` element. In the general case filter property of the widget should select all `li.k-item` elements. If required the hint movement can be restricted within the `ul.k-tabstrip-items` element.

    $("#tabstrip ul.k-tabstrip-items").kendoSortable({
        filter: "li.k-item",
        axis: "x",
        container: "ul.k-tabstrip-items",
        hint: function(element) {
            return $("<div id='hint' class='k-widget k-header k-tabstrip'><ul class='k-tabstrip-items k-reset'><li class='k-item k-state-active k-tab-on-top'>" + element.html() + "</li></ul></div>");
        },
        start: function(e) {
            $("#tabstrip").data("kendoTabStrip").activateTab(e.item);
        },
        change: function(e) {
            var tabstrip = $("#tabstrip").data("kendoTabStrip"),
                reference = tabstrip.tabGroup.children().eq(e.newIndex);

            if(e.oldIndex < e.newIndex) {
                tabstrip.insertAfter(e.item, reference);
            } else {
                tabstrip.insertBefore(e.item, reference);
            }
        }
    });

In order to avoid visual glitches it is recommended to activate the current tab in the `start` event handler of the Sortable widget.

    start: function(e) {
        $("#tabstrip").data("kendoTabStrip").activateTab(e.item);
    }

After tab is sorted the developer should update its position in the TabStrip widget.

    change: function(e) {
        var tabstrip = $("#tabstrip").data("kendoTabStrip"),
            reference = tabstrip.tabGroup.children().eq(e.newIndex);

        if(e.oldIndex < e.newIndex) {
            tabstrip.insertAfter(e.item, reference);
        } else {
            tabstrip.insertBefore(e.item, reference);
        }
    }

For more information check [Sortable's events](../../../api/web/sortable#events) and TabStrip integration [demo page](http://demos.telerik.com/kendo-ui/web/sortable/integration-tabstrip.html).

