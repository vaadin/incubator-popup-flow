# Deprecated 
This repository has been deprecated. Please find the latest code here: 
https://github.com/vaadin-component-factory/popup

# Incubator Popup for Flow
Incubator Popup for Flow is a server-side component of the [incubator-popup](https://github.com/vaadin/incubator-popup) web component for Vaadin 10. 
It provides a popup that can be bound to element by id, and be opened on clicking to target element. 
## Usage
After creating new Popup object it should be bound to a target element by calling the method
`setFor(id)` with the id of the target element as parameter. Then after clicking on the target element, the popup will be opened. 
Clicking outside of the popup will close it.
 
```
    Popup popup = new Popup();
    popup.setFor("id-of-target-element");
    Div text = new Div();
    text.setText("element 1");
    Div text2 = new Div();
    text2.setText("element 2");
    popup.add(text, text2);
```
If the parameter `closeOnClick` is set to `true`, the popup will be closed also after clicking on the popup.
Opening and closing of the popup can be done programmatically by calling the methods `show()` and `hide()`.
```
    Button button = new Button("Show/Hide");
    button.addClickListener(e -> {
        if (popup.isOpened()) {
            popup.hide();
        } else {
            popup.show();
        }
    });
```  
Setting the parameter `opened` to `true` will open the popup. In case the popup is not yet rendered, it will be opened after rendering.
```
    popup.setOpened(true);
```
## Demo
To run the demo, go to `incubator-popup-flow-vaadincom-demo/` subfolder and run `mbn jetty:run`.
After server startup, you'll be able find the demo at [http://localhost:8080/popup](http://localhost:8080/popup)
## Setting up for development:
Clone the project in GitHub (or fork it if you plan on contributing)
```
https://github.com/vaadin/incubator-popup-flow
```
To build and install the project into the local repository, run 
```mvn install ```
## License & Author
This Add-on is distributed under [Commercial Vaadin Add-on License version 3](http://vaadin.com/license/cval-3) (CVALv3). For license terms, see LICENSE.txt.
Incubator Popup is written by Vaadin Ltd.
