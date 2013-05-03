# CSS Notes

## I. Key Points

1. If an element is "taken out of the flow", the parent element will __not__
resize, move, or accomodate that element in anyway. The parent simply doesn't
know what it's doing, even its size. Except the fact that, it is a child.

## II. Positioning

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

## III. Floating

### General Take-aways

1. `float`
    1. Taken __out__ of the document flow
    2. "floats" __do not overlap__ other "floats". They sit next to each other.
    3. __Exception__ to above is the use of __negative margin__

2. `float: left;`
    1. The left margin of the "floated" element moves all the way to the left
    edge of the __immediate parent__ (edge of padding if there are any).

Please see `float.html` for an example.

## IV. Clear

### General

1. `clear: left;`
    1. This element is guaranteed that it will be __below all previously__
    `float: left` elements
    2. It __could__ still be affected by `float: right` elements though

    See `clear_left.html` for an example.
2. `clear: right;`
    1. This element is guaranteed that it will be __below all previously__
    `float: right` elements.
    2. It __could__ still be affected by `float: left` elements though

## V. Float and Clear Combo

Usage:

1. Stacking One Element on Top of the Other

    If you use the following
    ```css
    float: left;
    clear: left;
    ```

    That element will float all the way to the left, and must also be under
    all previously "floated-left" elements.

    If `div-a` is already floated left, and `div-b` has the above CSS, then
    `div-b` has no choice but to sit below `div-a`.

    Explanation:

    1. `div-b` float to towards the left edge of the parent
    2. `div-b` sees `div-a`, since they cannot overlap. It sits next to `div-a`
    3. But `div-b` must also be below all floated-left elements (`clear: left`)
    4. So `div-b` now moves below `div-a`
