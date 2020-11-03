# Responsive Web Design

## TL;DR
set view port in main HTML:  
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
* Size content to the viewport  
    * using flexbox
        ```css
        .items {
            display: flex;
            justify-content: space-between;
        }
        ```
    * using CSS Grid Layout
         ```css
        .container {
            display: grid;
        }
        ```
* Use CSS media queries for responsiveness  
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            …
            <link rel="stylesheet" href="print.css" media="print">
            …
        </head>
        …
    ```
    ```css
    @media print {
        /* print styles go here */
    }
    @media (max-width: 600px) {
        /* if the max-width is 600px */
    }

    @media (min-width: 601px) {
        /* if the min-width is 601px */
    }
    ```

## Detail notes
* view port  
    The viewport varies with the device, and will be smaller on a mobile phone than on a computer screen.
    include the following <meta> viewport element in all your web pages:
    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```
    This gives the browser instructions on how to control the page's dimensions and scaling.

    ```width=device-width```  
    this instructs the page to match the screen's width in device-independent pixels. A device (or density) independent pixel being a representation of a single pixel, which may on a high density screen consist of many physical pixels. This allows the page to reflow content to match different screen sizes, whether rendered on a small mobile phone or a large desktop monitor.

    ```initial-scale=1```  
    Some browsers keep the page's width constant when rotating to landscape mode, and zoom rather than reflow to fill the screen. Adding the value  instructs browsers to establish a 1:1 relationship between CSS pixels and device-independent pixels regardless of device orientation, and allows the page to take advantage of the full landscape width.

* Size content to the viewport
    * Flexbox  
        This layout method is ideal when you have a set of items of different sizes and you would like them to fit comfortably in a row or rows, with smaller items taking less space and larger ones getting more space.
        ```css
        .items {
            display: flex;
            justify-content: space-between;
        }
        ```
    * CSS Grid Layout  
        CSS Grid Layout allows for the straightforward creation of flexible grids. If we consider the earlier floated example, rather than creating our columns with percentages, we could use grid layout and the fr unit, which represents a portion of the available space in the container.
        ```css
        .container {
            display: grid;
        }
        ```
* Use CSS media queries for responsiveness 
    Media queries are simple filters that can be applied to CSS styles. They make it easy to change styles based on the types of device rendering the content, or the features of that device, for example width, height, orientation, ability to hover, and whether the device is being used as a touchscreen.  
    To provide different styles for printing, you need to target a type of output so you could include a stylesheet with print styles as follows:
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            …
            <link rel="stylesheet" href="print.css" media="print">
            …
        </head>
        …
    ```
    ```css
    @media print {
        /* print styles go here */
    }
    @media (max-width: 600px) {
        /* if the max-width is 600px */
    }

    @media (min-width: 601px) {
        /* if the min-width is 601px */
    }
    ```
