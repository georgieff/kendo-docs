---
title: diagram-shapeDefaults
slug: jsp-diagram-shapeDefaults
tags: api, java
publish: true
---

# \<kendo:diagram-shapeDefaults\>

Defines the shape options.

#### Example
    <kendo:diagram>
        <kendo:diagram-shapeDefaults></kendo:diagram-shapeDefaults>
    </kendo:diagram>

## Configuration Attributes

### background `java.lang.String`

Defines the fill-color of the shape.

#### Example
    <kendo:diagram-shapeDefaults background="background">
    </kendo:diagram-shapeDefaults>

### editable `boolean`

Specifies if the shape is editable by the user.

#### Example
    <kendo:diagram-shapeDefaults editable="editable">
    </kendo:diagram-shapeDefaults>

### height `float`

Defines the height of the shape when added to the diagram.

#### Example
    <kendo:diagram-shapeDefaults height="height">
    </kendo:diagram-shapeDefaults>

### minHeight `float`

Defines the minimum height the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Example
    <kendo:diagram-shapeDefaults minHeight="minHeight">
    </kendo:diagram-shapeDefaults>

### minWidth `float`

Defines the minimum width the shape should have, i.e. it cannot be resized to a value smaller than the given one.

#### Example
    <kendo:diagram-shapeDefaults minWidth="minWidth">
    </kendo:diagram-shapeDefaults>

### path `java.lang.String`

The path option of a Shape is a description of a custom geometry. The format follows the standard SVG format (http://www.w3.org/TR/SVG/paths.html#PathData "SVG Path data.").

#### Example
    <kendo:diagram-shapeDefaults path="path">
    </kendo:diagram-shapeDefaults>

### resizable `boolean`

Specifies if the shape is resizable.

#### Example
    <kendo:diagram-shapeDefaults resizable="resizable">
    </kendo:diagram-shapeDefaults>

### rotatable `boolean`

Specifies if the user is allowed to rotate the shape.

#### Example
    <kendo:diagram-shapeDefaults rotatable="rotatable">
    </kendo:diagram-shapeDefaults>

### type `java.lang.String`

Specifies the type of the Shape using any of the built-in shape type.

#### Example
    <kendo:diagram-shapeDefaults type="type">
    </kendo:diagram-shapeDefaults>

### visual `java.lang.String`

A function returning a visual element to render for a given shape. The following primitives can be used to construct a composite visual:

#### Example
    <kendo:diagram-shapeDefaults visual="visual">
    </kendo:diagram-shapeDefaults>

### width `float`

Defines the width of the shape when added to the diagram.

#### Example
    <kendo:diagram-shapeDefaults width="width">
    </kendo:diagram-shapeDefaults>

### x `float`

Defines the x-coordinate of the shape when added to the diagram.

#### Example
    <kendo:diagram-shapeDefaults x="x">
    </kendo:diagram-shapeDefaults>

### y `float`

Defines the y-coordinate of the shape when added to the diagram.

#### Example
    <kendo:diagram-shapeDefaults y="y">
    </kendo:diagram-shapeDefaults>


##  Configuration JSP Tags

### kendo:diagram-shapeDefaults-connectors

Defines the connectors the shape owns.You can easily define your own custom connectors or mix-match with the above defined custom connectors.Example - custom shape with custom connectorsThe following defines a custom shape with connectors adapted to the shape's outline. Note in particular the various helpful methods (right(), left(), top()) to define positions relative to the shape.

More documentation is available at [kendo:diagram-shapeDefaults-connectors](/kendo-ui/api/wrappers/jsp/diagram/shapedefaults-connectors).

#### Example

    <kendo:diagram-shapeDefaults>
        <kendo:diagram-shapeDefaults-connectors></kendo:diagram-shapeDefaults-connectors>
    </kendo:diagram-shapeDefaults>

### kendo:diagram-shapeDefaults-content

Defines the shapes content settings.

More documentation is available at [kendo:diagram-shapeDefaults-content](/kendo-ui/api/wrappers/jsp/diagram/shapedefaults-content).

#### Example

    <kendo:diagram-shapeDefaults>
        <kendo:diagram-shapeDefaults-content></kendo:diagram-shapeDefaults-content>
    </kendo:diagram-shapeDefaults>

### kendo:diagram-shapeDefaults-hover

Defines the hover configuration.

More documentation is available at [kendo:diagram-shapeDefaults-hover](/kendo-ui/api/wrappers/jsp/diagram/shapedefaults-hover).

#### Example

    <kendo:diagram-shapeDefaults>
        <kendo:diagram-shapeDefaults-hover></kendo:diagram-shapeDefaults-hover>
    </kendo:diagram-shapeDefaults>

### kendo:diagram-shapeDefaults-rotation



More documentation is available at [kendo:diagram-shapeDefaults-rotation](/kendo-ui/api/wrappers/jsp/diagram/shapedefaults-rotation).

#### Example

    <kendo:diagram-shapeDefaults>
        <kendo:diagram-shapeDefaults-rotation></kendo:diagram-shapeDefaults-rotation>
    </kendo:diagram-shapeDefaults>

### kendo:diagram-shapeDefaults-stroke

Defines the stroke configuration.

More documentation is available at [kendo:diagram-shapeDefaults-stroke](/kendo-ui/api/wrappers/jsp/diagram/shapedefaults-stroke).

#### Example

    <kendo:diagram-shapeDefaults>
        <kendo:diagram-shapeDefaults-stroke></kendo:diagram-shapeDefaults-stroke>
    </kendo:diagram-shapeDefaults>


## Event Attributes

### visual `String`

A function returning a visual element to render for a given shape. The following primitives can be used to construct a composite visual:


#### Example
    <kendo:diagram-shapeDefaults visual="handle_visual">
    </kendo:diagram-shapeDefaults>
    <script>
        function handle_visual(e) {
            // Code to handle the visual event.
        }
    </script>

## Event Tags

### kendo:diagram-shapeDefaults-visual

A function returning a visual element to render for a given shape. The following primitives can be used to construct a composite visual:


#### Example
    <kendo:diagram-shapeDefaults>
        <kendo:diagram-shapeDefaults-visual>
            <script>
                function(e) {
                    // Code to handle the visual event.
                }
            </script>
        </kendo:diagram-shapeDefaults-visual>
    </kendo:diagram-shapeDefaults>

