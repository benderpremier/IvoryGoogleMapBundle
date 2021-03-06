# Circle

A Circle is similar to a Polygon in that you can define custom colors, weights, and opacities for the edge of the circle (the "stroke") and custom colors and opacities for the area within the enclosed region (the "fill").
Unlike a Polygon, you do not define paths for a Circle. Instead, a circle has two additional properties which define its shape: center of the circle, radius of the circle, in meters.

## Build your circle

### By configuration file

By default, the bundle doesn't need any configuration. Most of the service have a default configuration which allows you to use the given objects like they are.
The ``ivory_google_map.circle`` service is. The configuration describes below is this default configuration.

```
# app/config/config.yml

ivory_goole_map:
    circle:
        # Prefix used for the generation of the circle javascript variable
        prefix_javascript_variable: "circle_"

        # Circle center
        center:
            latitude: 0
            longitude: 0
            no_wrap: true

        # Circle radius
        radius: 1

        # Custom circle options
        # By default, there is no options
        options:
            clickable: false
            strokeWeight: 2
```

``` php
<?php

// Requests the ivory google map circle service
$circle = $this->get('ivory_google_map.circle');
```

### By coding

``` php
<?php

// Requests the ivory google map circle service
$circle = $this->get('ivory_google_map.circle');

// Configure your circle options
$circle->setPrefixJavascriptVariable('circle_');
$circle->setCenter(0, 0, true);
$circle->setRadius(1);

$circle->setOption('clickable', false);
$circle->setOption('strokeWeight', 2);
$circle->setOptions(array(
    'clickable' => false,
    'strokeWeight' => 2
));
```

## Add your circle to the map

``` php
<?php

// Requests the ivory google map circle service
$circle = $this->get('ivory_google_map.circle');

// Add your circle to the map
$map->addCircle($circle);
```
