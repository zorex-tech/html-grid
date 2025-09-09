# LAYOUT WITH CSS

When laying out elements using css, there are a couple of things we should have at the back of out mind

1. CSS Box Model
Every element has four sections. Starting from the outer most, we have the 
- margin, which is the space between the element and the next element, it is the outer most space of the element
- next we have the border, which is the edge of the element
- then we have the padding, which is the space between the main content and the border
- finally we have the content itself. This is the actual content.

It is good to know how the browser works to render these based on the setting, because it would save you lots of unexpected/ weird behaviour.

Because of the way elements are renders by the browser, it is important to know that the proper way to space elements is by using the margin property and not the padding property. When you use the margin property, the brower collapses margins of elements next to each other - the process is call margin collapsing.

2. Sizing Elements
When we have an element, any height and/or width given is applied to the elements content box, what that means is that they are applied to the content itself and adding border and/or padding increases the visible box. This happens because by default, every element has the box-sizing set to content box, but we can set it to border box and adding padding and/or border are then taken from the content size.

So adding margin to an element does not impact the size of the visible box, it only moves the element away from other elements.

When giving width and height to elements, note that only block level elements respect them, inline elements do not repect width and height, if you most give inline elements some width and height, then you must change their display type to inline-block

3. Overflow
When dealing with overflowing elements, you can use the overflow property to handle it, you can set it to right or left as appropriate and the clear the overflow to avoid parent collapsing. 
To clear the overflow, you can set clear: both, that way you clear the overflow from left or right. For a more general use case, you can use the ::before and :: after psudo elements to clear the overflow on all elements including psudo elements.   

4. Mearsurement Units
To measeure, there are absolute and relative measuring units. We have px for fixed measurment, then percentages, view height/view width, em and rem which are relative to the container, the view port and the font size respectively.
Note: when using em/rem, to make your calculation simple, you can set the body font-size to 62.5%
5. Positioning elements
To position elements on the screen, we can do it in relation to the view port using the fixed position, or in relation to the containing element by setting the containing element to relative and then the element to be positioned to absolute, with this, we can use the top, bottom, left or right to move the element on the screen or finally we can position the element in relationship to its normal position in the DOM using position relative 
6. Grid
To align items on the screen, we can use display flex to make the item align in a row or a column - single dimention. Using the justify-content, we can align the flex items in the main axis and using align-items, along the cross axis.
To layout elements in multidimentional way, we use grid.
We make the display grid and define the grid-template-rows/columns. The grid-template-rows/columns takes the size of the column/row the number of times that corresponds to the number of rows/columns we need. We can use any measuring unit to add the rows/columns but a unit especially useful is fr, it uses the fraction of the availaible space.
To position grid elements, you use grid-row/column, which takes the start line / the end line.

You can also use named grid cells, you do that setting grid-template: and give the name of the rows, the number of column times, seperated by space and you move to the element you want to position in the named area, and the element is positioned there.
7. Hiding elements
To hide elements, there are 2 ways, you can use display: none which hides the element like nothing was there to start with or visibility: hidden which hides the element but keeps its space on the screen
8. Media query
We can apply specific style on various screen sizes, this is important for creating responsive layouts that change with screen sizes