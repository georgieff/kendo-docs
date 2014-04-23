---
title: Using Kendo with AngularJS
slug: gs-using-kendo-with-angularjs
tags: 101, Getting Started, AngularJS
publish: true
---

# Using Kendo with AngularJS

Kendo UI can be used seamlessly with AngularJS.  The two frameworks have some overlapping features though; if you are using AngularJS then you probably want to use Angular's own routing mechanism and data binding.

For a good integration we provide [angular-kendo](http://kendo-labs.github.io/angular-kendo/), a small library which creates Angular directives for Kendo widgets, allowing you to build your UI in a declarative way.

## Using Angular-Kendo bindings

Download the latest version of `angular-kendo.js` from the Github repository: [https://github.com/kendo-labs/angular-kendo](https://github.com/kendo-labs/angular-kendo).  You can also find it on NuGet and on Bower, but the packages might sometimes be out of date.

`angular-kendo.js` depends on Kendo and Angular, and Kendo itself depends on jQuery.  Therefore, load the scripts in this order:

    <script src="jquery.js"></script>
    <script src="kendo.all.js"></script>
    <script src="angular.js"></script>
    <script src="angular-kendo.js"></script>

Don't forget to load the Kendo UI stylesheets too.

Next, when creating your AngularJS application you must declare dependency on "kendo.directives":

    var app = angular.module("your-angular-app", [ "kendo.directives" ]);

### Creating widgets the Angular way

The directives kick in on attributes like `kendo-widget-name`.  For example to get a `DatePicker` widget, you'd write the following:

    <label>Birthday: <input kendo-date-picker /></label>

When AngularJS compiles the HTML, the Kendo UI directive will turn the `<input>` field into a nice date picker widget.

### Scope bindings (`ng-model`)

For all widgets which provide a `value()` method you can use the standard `ng-model` directive to bind their value into the AngularJS scope.  Example:

    <label>Birthday: <input kendo-date-picker ng-model="birthday" /></label>
    <p>
      Your selection: {{ birthday }}
    </p>

The input field is now bound to the scope variable.  When you select a date, the `birthday` variable will be set to the input field's value (as a string).

### Scope bindings (`k-ng-model`)

If your element is a form field like `<input>` or `<textarea>` (which has a text value), the `ng-model` will bind the field contents, which is what most AngularJS users would expect.  So for the DatePicker example above, you would get a string date, instead of a JavaScript Date object, in the scope.

If you need to get the actual `widget.value()` you can use `k-ng-model`:

    <input kendo-date-picker k-ng-model="birthday" />

The directive will update the `birthday` variable with the selected `Date` object whenever the `change` event occurs on the widget.

### Widget configuration in markup

Kendo UI widgets provide tons of configuration options.  When using the Kendo API you pass those options in widget constructors, e.g.:

    $("#birthday").kendoDatePicker({
      format : "dddd MMMM d, yyyy"
    });

To do the same with AngularJS bindings, you can use attributes prefixed with `k-`:

    <label>
      Birthday:
      <input kendo-date-picker k-format="'dddd MMMM d, yyyy'" />
    </label>

Note that we had to 'quote' the string attribute.  This is because the `k-` attributes are evaluated against the AngularJS scope.  If you need to store the date format as a scope variable you can do:

    // in your controller:
    $scope.dateFormat = "dddd MMMM d, yyyy";

    <!-- in HTML: -->
    <input kendo-date-picker k-format="dateFormat" />

### Widget configuration in controller

If you'd like to store all widget configuration in the controller, you can use the special `k-options` attribute:

    // in controller:
    $scope.monthPickerConfig = {
      start  : "year",
      depth  : "year",
      format : "MMMM yyyy"
    };

    <!-- in HTML: -->
    <input kendo-date-picker k-options="monthPickerConfig" />

### Event handlers

If you store the whole configuration in the controller, like above, then adding an event handler is done the same you would do with plain Kendo:

    // in controller:
    $scope.monthPickerConfig = {
      start  : "year",
      depth  : "year",
      format : "MMMM yyyy",
      change : function(e) {
        var datePicker = e.sender;
        console.log(datePicker.value());
        $scope.selected = true;
        $scope.$digest();
      }
    };

    <!-- in HTML: -->
    <input kendo-date-picker k-options="monthPickerConfig" />
    <p ng-show="selected">A month was picked</p>

The sample above includes a paragraph that's using Angular's `ng-show` directive and will be displayed only after a month was picked.  Notice in the event handler that we had to call `$scope.$digest()` in order for this trick to work.

It is possible to specify event handlers using attributes as well.  They require the `k-on-` prefix:

    // in controller:
    $scope.onDateSelected = function(e) {
      var datePicker = e.sender;
      console.log(datePicker.value());
      $scope.selected = true;
    };

    <!-- in HTML: -->
    <input kendo-date-picker k-on-change="onDateSelected(kendoEvent)" />
    <p ng-show="selected">A month was picked</p>

Notice that the `kendoEvent` variable will be defined in scope and we must pass it to the event handler.  If we are using the `k-on-` attributes, there is no need to call `$digest()` on the scope (it's taken care of by angular-kendo.js).

### Updating widgets when options change

You can use the special `k-rebind` attribute to create a widget which automatically updates when some scope variable changes:

    // in controller:
    $scope.orientation = "horizontal";

    <!-- in HTML: -->
    <ul kendo-menu k-orientation="orientation" k-rebind="orientation">
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>

    <select kendo-drop-down-list k-ng-model="orientation">
      <option>horizontal</option>
      <option>vertical</option>
    </select>

To watch multiple options for change, just use `k-options` and pass the same variable to `k-rebind`:

    <ul kendo-menu k-options="menuOptions" k-rebind="menuOptions"> ... </ul>

### Getting widget references

Sometimes you might need a reference to the widgets in order to call methods on it from your controller.  To get one, just assign a name to the `kendo-widget-name` attribute, for example:

    // in controller:
    $scope.onChange = function() {
      // $scope.datePicker will be initialized by the directive
      alert($scope.datePicker.value());
    };

    <!-- in HTML: -->
    <input kendo-date-picker="datePicker" k-on-change="onChange()" />

## Get involved

[Angular-Kendo](https://github.com/kendo-labs/angular-kendo) is free software.  If you find any issues or have suggestions, please use the issue tracker.
