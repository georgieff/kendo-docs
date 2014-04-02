---
title: diagram-shape
slug: jsp-diagram-shape
tags: api, java
publish: true
---

# \<kendo:diagram-shape\>

Defines the shape options.

#### Example
    <kendo:diagram-shapes>
        <kendo:diagram-shape></kendo:diagram-shape>
    </kendo:diagram-shapes>

## Configuration Attributes

### background `java.lang.String`

Defines the fill-color of the shape.

#### Example
    <kendo:diagram-shape background="background">
    </kendo:diagram-shape>

### editable `boolean`

Specifies if the shape is editable by the user.

#### Example
    <kendo:diagram-shape editable="editable">
    </kendo:diagram-shape>

### height `float`

Defines the height of the shape when added to the diagram.

#### Example
    <kendo:diagram-shape height="height">
    </kendo:diagram-shape>

### id `java.lang.String`

The unique identifier for a Shape.

#### Example
    <kendo:diagram-shape id="id">
    </kendo:diagram-shape>

### minHeight `float`

Defines the minimum height the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Example
    <kendo:diagram-shape minHeight="minHeight">
    </kendo:diagram-shape>

### minWidth `float`

Defines the minimum width the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Example
    <kendo:diagram-shape minWidth="minWidth">
    </kendo:diagram-shape>

### path `java.lang.String`

The path option of a Shape is a description of a custom geometry. The format follows the standard SVG format (http://www.w3.org/TR/SVG/paths.html#PathData "SVG Path data.").

#### Example
    <kendo:diagram-shape path="path">
    </kendo:diagram-shape>

### resizable `boolean`

Specifies if the shape is resizable.

#### Example
    <kendo:diagram-shape resizable="resizable">
    </kendo:diagram-shape>

### rotatable `boolean`

Specifies if the user is allowed to rotate the shape.

#### Example
    <kendo:diagram-shape rotatable="rotatable">
    </kendo:diagram-shape>

### type `java.lang.String`

Specifies the type of the Shape using any of the built-in shape type.

#### Example
    <kendo:diagram-shape type="type">
    </kendo:diagram-shape>

### visual `java.lang.String`

A function returning a visual element to render for this shape.
See visual.

#### Example
    <kendo:diagram-shape visual="visual">
    </kendo:diagram-shape>

### width `float`

Defines the width of the shape when added to the diagram.

#### Example
    <kendo:diagram-shape width="width">
    </kendo:diagram-shape>

### x `float`

Defines the x-coordinate of the shape when added to the diagram.

#### Example
    <kendo:diagram-shape x="x">
    </kendo:diagram-shape>

### y `float`

Defines the y-coordinate of the shape when added to the diagram.

#### Example
    <kendo:diagram-shape y="y">
    </kendo:diagram-shape>


##  Configuration JSP Tags

### kendo:diagram-shape-connectors

Defines the connectors the shape owns.

More documentation is available at [kendo:diagram-shape-connectors](/kendo-ui/api/wrappers/jsp/diagram/shape-connectors).

#### Example

    <kendo:diagram-shape>
        <kendo:diagram-shape-connectors></kendo:diagram-shape-connectors>
    </kendo:diagram-shape>

### kendo:diagram-shape-content

Defines the shapes content settings.

More documentation is available at [kendo:diagram-shape-content](/kendo-ui/api/wrappers/jsp/diagram/shape-content).

#### Example

    <kendo:diagram-shape>
        <kendo:diagram-shape-content></kendo:diagram-shape-content>
    </kendo:diagram-shape>

### kendo:diagram-shape-hover

Defines the hover configuration.

More documentation is available at [kendo:diagram-shape-hover](/kendo-ui/api/wrappers/jsp/diagram/shape-hover).

#### Example

    <kendo:diagram-shape>
        <kendo:diagram-shape-hover></kendo:diagram-shape-hover>
    </kendo:diagram-shape>

### kendo:diagram-shape-rotation

The function that positions the connector.

More documentation is available at [kendo:diagram-shape-rotation](/kendo-ui/api/wrappers/jsp/diagram/shape-rotation).

#### Example

    <kendo:diagram-shape>
        <kendo:diagram-shape-rotation></kendo:diagram-shape-rotation>
    </kendo:diagram-shape>

### kendo:diagram-shape-stroke

Defines the stroke configuration.

More documentation is available at [kendo:diagram-shape-stroke](/kendo-ui/api/wrappers/jsp/diagram/shape-stroke).

#### Example

    <kendo:diagram-shape>
        <kendo:diagram-shape-stroke></kendo:diagram-shape-stroke>
    </kendo:diagram-shape>


## Event Attributes

### visual `String`

A function returning a visual element to render for this shape.
See visual.


#### Example
    <kendo:diagram-shape visual="handle_visual">
    </kendo:diagram-shape>
    <script>
        function handle_visual(e) {
            // Code to handle the visual event.
        }
    </script>

## Event Tags

### kendo:diagram-shape-visual

A function returning a visual element to render for this shape.
See visual.


#### Example
    <kendo:diagram-shape>
        <kendo:diagram-shape-visual>
            <script>
                function(e) {
                    // Code to handle the visual event.
                }
            </script>
        </kendo:diagram-shape-visual>
    </kendo:diagram-shape>

