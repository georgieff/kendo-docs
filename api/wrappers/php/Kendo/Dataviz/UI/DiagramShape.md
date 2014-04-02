---
title: DiagramShape
slug: php-dataviz-ui-diagramshape
tags: api, php
publish: true
---

# \Kendo\Dataviz\UI\DiagramShape

A PHP class representing the shape setting of DiagramShapes.


## Methods

### background
Defines the fill-color of the shape.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->background('value');
    ?>

### addConnector

Adds one or more DiagramShapeConnector to the DiagramShape.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value[, $value2, ...] `\Kendo\Dataviz\UI\DiagramShapeConnector|array`

#### Example - using \Kendo\Dataviz\UI\DiagramShapeConnector

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $connector = new \Kendo\Dataviz\UI\DiagramShapeConnector();
    $description = 'value';
    $connector->description($description);
    $shape->addConnector($connector);
    ?>

#### Example - using array

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $description = 'value';
    $shape->addConnector(array('description' => $description));
    ?>

#### Example - adding more than one DiagramShapeConnector

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $first  = new \Kendo\Dataviz\UI\DiagramShapeConnector();
    $second = new \Kendo\Dataviz\UI\DiagramShapeConnector();
    $shape->addConnector($first, $second);
    ?>

### content

Defines the shapes content settings.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeContent|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeContent](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeContent)
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $content = new \Kendo\Dataviz\UI\DiagramShapeContent();
    $align = 'value';
    $content->align($align);
    $shape->content($content);
    ?>

#### Example - using array

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $align = 'value';
    $shape->content(array('align' => $align));
    ?>

### editable
Specifies if the shape is editable by the user.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->editable(true);
    ?>

### height
Defines the height of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->height(1);
    ?>

### hover

Defines the hover configuration.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeHover|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeHover](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeHover)
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $hover = new \Kendo\Dataviz\UI\DiagramShapeHover();
    $background = 'value';
    $hover->background($background);
    $shape->hover($hover);
    ?>

#### Example - using array

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $background = 'value';
    $shape->hover(array('background' => $background));
    ?>

### id
The unique identifier for a Shape.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->id('value');
    ?>

### minHeight
Defines the minimum height the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->minHeight(1);
    ?>

### minWidth
Defines the minimum width the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->minWidth(1);
    ?>

### path
The path option of a Shape is a description of a custom geometry. The format follows the standard SVG format (http://www.w3.org/TR/SVG/paths.html#PathData "SVG Path data.").

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->path('value');
    ?>

### resizable
Specifies if the shape is resizable.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->resizable(true);
    ?>

### rotatable
Specifies if the user is allowed to rotate the shape.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->rotatable(true);
    ?>

### rotation

The function that positions the connector.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeRotation|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeRotation](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeRotation)
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $rotation = new \Kendo\Dataviz\UI\DiagramShapeRotation();
    $angle = 1;
    $rotation->angle($angle);
    $shape->rotation($rotation);
    ?>

#### Example - using array

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $angle = 1;
    $shape->rotation(array('angle' => $angle));
    ?>

### stroke

Defines the stroke configuration.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `\Kendo\Dataviz\UI\DiagramShapeStroke|array`


#### Example - using [\Kendo\Dataviz\UI\DiagramShapeStroke](/kendo-ui/api/wrappers/php/Kendo/Dataviz/UI/DiagramShapeStroke)
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $stroke = new \Kendo\Dataviz\UI\DiagramShapeStroke();
    $color = 'value';
    $stroke->color($color);
    $shape->stroke($stroke);
    ?>

#### Example - using array

    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $color = 'value';
    $shape->stroke(array('color' => $color));
    ?>

### type
Specifies the type of the Shape using any of the built-in shape type.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->type('value');
    ?>

### visual
A function returning a visual element to render for this shape.
See visual.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `\Kendo\JavaScriptFunction`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->visual(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### width
Defines the width of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->width(1);
    ?>

### x
Defines the x-coordinate of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->x(1);
    ?>

### y
Defines the y-coordinate of the shape when added to the diagram.

#### Returns
`\Kendo\Dataviz\UI\DiagramShape`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $shape = new \Kendo\Dataviz\UI\DiagramShape();
    $shape->y(1);
    ?>

