# GUI details

In the `settings.json` file you should include the following in a table:

* `"describer-version": "0.1.0"` (Pyegi checks this value to know what type of details it should expect)
* `Format` (You may leave this field empty if your script doesn't need a GUI or you want to create the GUI yourself. You may also fill this field with "Lua" to indicate that the parameters defined in the table are Lua elements.)
  * `Windows` (This is a list of windows (each as a table) that your GUI introduces)
    * `name` (Name of the window)
    * `Controls` (A list of the elements in the window. Each element/control is defined as a table and has the similar fields as a Lua GUI element).
      * You have the option of starting the name of each element with "G\_" so that particular element will be considered a **global element**. For a global element, if you change its value in one of the windows it appears on, its value on other windows change respectively.
      * There's also a button element which is a Pyegi-specific element with the following fields:
        * `"class": "Pyegi_button"`
        * `name`
        * `text`
        * `action` ("Apply", "Cancel", or "Transition")
        * `transition to` (If the `action` filed is "Transition", in this field you should type the name of the window that you want to navigate to using this button.)
        * `hint`
        * `x`
        * `y`
        * `width`
        * `height`
