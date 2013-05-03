# CSS Notes

## I. Positioning

### General Take-aways

1. `absolute`
    1. (0,0) is at the top-left corner of the __closest__ `relative` positioned
    parent
    2. It's taken out of the flow. Its "place" is not recognized by the DOM.
    3. It's placed on "top" of the normal flow of the document
2. `relative`
    1. "Relative" to where __it's supposed to be__
    2. Its "place" __is__ recognized by the DOM using "top to bottom" flow.
    3. It __just appears__ to be somewhere else __visually__
3. `static`
    1. The default if no `position` is defined
    2. The location will the same as its position inside the HTML code
    3. Its "place" is recognized by the DOM

Please see `css_positioning.html` for an example.
