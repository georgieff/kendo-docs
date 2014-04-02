---
title: DiagramShapeDefaults
slug: php-dataviz-ui-diagramshapedefaults
tags: api, php
publish: true
---

# \Kendo\Dataviz\UI\DiagramShapeDefaults

A PHP class representing the shapeDefaults setting of Diagram.


## Methods

### background
Defines the fill-color of the shape.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->background('value');
    ?>

### addConnector

Adds one or more DiagramShapeDefaultsConnector to the DiagramShapeDefaults.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value[, $value2, ...] `\Kendo\Dataviz\UI\DiagramShapeDefaultsConnector|array`

#### Example - using \Kendo\Dataviz\UI\DiagramShapeDefaultsConnector

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $connector = new \Kendo\Dataviz\UI\DiagramShapeDefaultsConnector();
    $description = 'value';
    $connector->description($description);
    $shapeDefaults->addConnector($connector);
    ?>

#### Example - using array

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $description = 'value';
    $shapeDefaults->addConnector(array('description' => $description));
    ?>

#### Example - adding more than one DiagramShapeDefaultsConnector

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $first  = new \Kendo\Dataviz\UI\DiagramShapeDefaultsConnector();
    $second = new \Kendo\Dataviz\UI\DiagramShapeDefaultsConnector();
    $shapeDefaults->addConnector($first, $second);
    ?>

### content

Defines the shapes content settings.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeDefaultsContent|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeDefaultsContent](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeDefaultsContent)
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $content = new \Kendo\Dataviz\UI\DiagramShapeDefaultsContent();
    $align = 'value';
    $content->align($align);
    $shapeDefaults->content($content);
    ?>

#### Example - using array

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $align = 'value';
    $shapeDefaults->content(array('align' => $align));
    ?>

### editable
Specifies if the shape is editable by the user.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->editable(true);
    ?>

### height
Defines the height of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->height(1);
    ?>

### hover

Defines the hover configuration.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeDefaultsHover|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeDefaultsHover](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeDefaultsHover)
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $hover = new \Kendo\Dataviz\UI\DiagramShapeDefaultsHover();
    $background = 'value';
    $hover->background($background);
    $shapeDefaults->hover($hover);
    ?>

#### Example - using array

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $background = 'value';
    $shapeDefaults->hover(array('background' => $background));
    ?>

### minHeight
Defines the minimum height the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->minHeight(1);
    ?>

### minWidth
Defines the minimum width the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->minWidth(1);
    ?>

### path
The path option of a Shape is a description of a custom geometry. The format follows the standard SVG format (http://www.w3.org/TR/SVG/paths.html#PathData "SVG Path data.").

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->path('value');
    ?>

### resizable
Specifies if the shape is resizable.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->resizable(true);
    ?>

### rotatable
Specifies if the user is allowed to rotate the shape.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->rotatable(true);
    ?>

### rotation



#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeDefaultsRotation|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeDefaultsRotation](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeDefaultsRotation)
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $rotation = new \Kendo\Dataviz\UI\DiagramShapeDefaultsRotation();
    $angle = 1;
    $rotation->angle($angle);
    $shapeDefaults->rotation($rotation);
    ?>

#### Example - using array

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $angle = 1;
    $shapeDefaults->rotation(array('angle' => $angle));
    ?>

### stroke

Defines the stroke configuration.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeDefaultsStroke|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeDefaultsStroke](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeDefaultsStroke)
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $stroke = new \Kendo\Dataviz\UI\DiagramShapeDefaultsStroke();
    $color = 'value';
    $stroke->color($color);
    $shapeDefaults->stroke($stroke);
    ?>

#### Example - using array

    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $color = 'value';
    $shapeDefaults->stroke(array('color' => $color));
    ?>

### type
Specifies the type of the Shape using any of the built-in shape type.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->type('value');
    ?>

### visual
A function returning a visual element to render for a given shape. The following primitives can be used to construct a composite visual:

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `\Kendo\JavaScriptFunction`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->visual(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### width
Defines the width of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->width(1);
    ?>

### x
Defines the x-coordinate of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->x(1);
    ?>

### y
Defines the y-coordinate of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShapeDefaults`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shapeDefaults = new \Kendo\Dataviz\UI\DiagramShapeDefaults();
    $shapeDefaults->y(1);
    ?>

