# CSS Specificity
## Specificity Hierarchy  
Every selector has its place in the specificity hierarchy. There are four categories which define the specificity level of a selector:

* Inline styles - An inline style is attached directly to the element to be styled. Example:
    ```html
    <h1 style="color: #ffffff;">.
    ```
* IDs - An ID is a unique identifier for the page elements, such as #navbar.

* Classes, attributes and pseudo-classes - This category includes .classes, [attributes] and pseudo-classes such as :hover, :focus etc.

* Elements and pseudo-elements - This category includes element names and pseudo-elements, such as h1, div, :before and :after.

## Specificity calculation
Start at 0, add 1000 for style attribute, add 100 for each ID, add 10 for each attribute, class or pseudo-class, add 1 for each element name or pseudo-element.

Consider these three code fragments:

Example
```
A: h1
B: #content h1
C: <div id="content"><h1 style="color: #ffffff">Heading</h1></div>
```
The specificity of A is 1 (one element)  
The specificity of B is 101 (one ID reference and one element)  
The specificity of C is 1000 (inline styling)

Since 1 < 101 < 1000, the third rule (C) has a greater level of specificity, and therefore will be applied.

## Specificity Rules
* Equal specificity: the latest rule counts  
If the same rule is written twice into the external style sheet, then the lower rule in the style sheet is closer to the element to be styled, and therefore will be applied:
* ID selectors have a higher specificity than attribute selectors  
Look at the following three code lines:
* Contextual selectors are more specific than a single element selector  
The embedded style sheet is closer to the element to be styled. So in the following situation
* A class selector beats any number of element selectors  
a class selector such as .intro beats h1, p, div, etc:
* The universal selector and inherited values have a specificity of 0  
*, body * and similar have a zero specificity. Inherited values also have a specificity of 0.