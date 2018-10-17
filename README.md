# Incubator Popup for Flow

Incubator Password Strength for Flow is server-side component of [incubator-popup](https://github.com/vaadin/incubator-popup) web component for Vaadin 10. 
It provides popup that can be bind to element by id, and be opened on clicking to target element. 

## Usage

After creating new Popup object it should be bind to target element by calling method
setFor(id) with id of target element as parameter. Then after clicking on target element, popup will be opened. 
Clicking outside of popup will close it.
 
```
    Popup popup = new Popup();
    popup.setFor("id-of-target-element");
    Div text = new Div();
    text.setText("element 1");
    Div text2 = new Div();
    text2.setText("element 2");
    popup.add(text, text2);
```

In case parameter `closeOnClick` set to `true` popup will be closed also after clicking on popup.

Opening and closing of popup can be done programmatically by calling `show()` and `hide()` functions.
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


Setting parameter `opened` to `true` will open popup. In case popup is not yet rendered, it will be opened after rendering.
```
    popup.setOpened(true);
```


## Demo
To run demo go to `incubator-popup-flow-vaadincom-demo/` subfolder and run `mbn jetty:run`.
After server startup, you'll be able find demo at [http://localhost:8080/popup](http://localhost:8080/popup)

## Setting up for development:

Clone the project in GitHub (or fork it if you plan on contributing)

```
https://github.com/vaadin/incubator-popup-flow
```

To build and install the project into the local repository run 

```mvn install ```

## License & Author

This Add-on is distributed under [Commercial Vaadin Add-on License version 3](http://vaadin.com/license/cval-3) (CVALv3). For license terms, see LICENSE.txt.

Incubator Password Strength is written by Vaadin Ltd.

