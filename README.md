## LiquidCrystal_I2C_Menu
**LiquidCrystal_I2C_Menu** - LiquidCrystal_I2C_Menu is a library for creating a user interface on Arduino and a text LCD with an I2C interface. The library provides functionality for formatted output, input and selection of values, menu organization. The control is carried out using a rotation encoder with a button.

## Connection
[![LiquidCrystal_I2C_Menu Подключение](https://github.com/VladimirTsibrov/LiquidCrystal_I2C_Menu/raw/master/wiring/LiquidCrystal_I2C_Menu%20wiring.png "LiquidCrystal_I2C_Menu Подключение")](https://github.com/VladimirTsibrov/LiquidCrystal_I2C_Menu/raw/master/wiring/LiquidCrystal_I2C_Menu%20wiring.png "LiquidCrystal_I2C_Menu Подключение")

## Button control
Buttons can be used instead of a rotation encoder. There is another version of this library for this. - [LiquidCrystal_I2C_Menu_Btns](https://github.com/VladimirTsibrov/LiquidCrystal_I2C_Menu_Btns "LiquidCrystal_I2C_Menu_Btns")

## Functions
Along with the standard functions inherited from the LiquidCrystal_I2C library, this library implements the following:
- **printAt(x, y, text)** - output text to the display from the specified position.
- **printf(format, …)** – formatted text output. The same rules apply as in other formatted output functions, such as sprintf.
- **printfAt(x, y, format, …)** – formatted output from the specified position.
- **attachEncoder(pinA, pinB, pinBtn)** - tells the library which Arduino pins the encoder is connected to.
- **getEncoderState()** – encoder state poll. Returns a value of type eEncoderState (enumerated type, described in the library as {eNone, eLeft, eRight, eButton}).
- **printMultiline(text)** - print long text with vertical scrolling. The function returns when the encoder button is pressed.
- **inputVal(title, min, max, default, [step], [onChangeFunc])** – enter a numeric value. title - title; the min and max parameters specify the range in which the value can change; default - initial value; step – increment value, default is 1; optional parameter onChangeFunc - a pointer to a function that should be called when the value changes.
- **inputValAt(x, y, min, max, default, [step], [onChangeFunc])** – similar to the inputVal function, but unlike it, it does not clear the display when called, and the value is entered from the specified position.
- **inputValBitwise(title, value, precision, [scale], [signed])** – allows you to enter values by editing individual bits of a number. The title parameter specifies the title; value - a reference to a variable in which the input result will be placed; precision - the total number of digits in the number; scale – number of decimal places, default value 0; signed - allows (if true) or prohibits (if false - the default) the input of negative numbers. The function returns true if the user approved the input, false if he refused.
- **inputStrVal(title, buffer, length, available_symbols)** - similar to the inputValBitwise function, it provides the possibility of bitwise input, but other characters can be entered besides numbers. The title parameter specifies the title; buffer - a reference to a character buffer in which the input result will be placed; length - the number of input characters; the available_symbols parameter is a string of characters available for input. The function returns true if the user approved the input, false if he refused.
- **selectVal(title, list_of_values, count, [show_selected], [selected_index])** - allows you to select a value from the list list and returns the index of the selected element. title - the title displayed on the display; list – list of values to select, is an array of values of type char*, String or int; count - the number of elements in the array; show_selected - flag for displaying the label on the selected element; selected_index - The index of the default selected element.
- **showMenu(menu, menu_length, show_title)** - Displays the menu and returns the key of the selected item. menu is an array of elements of type sMenuItem; menu_length - menu length; show_title - a sign of the need to display the title.
- **getSelectedMenuItem()** - returns the key of the selected menu item for use inside handlers.
- **attachIdleFunc(IdleFunc)** – allows you to attach a function that will be called by the library when idle.

## Cyrillic display support
To enable support for Cyrillic displays, uncomment the #define CYRILLIC_DISPLAY line in the LiquidCrystal_I2C_Menu.h file. After that, it will be possible to use Russian text in the menu and other functions of the library.


## In details
You can find more information about the library and its functions here: [https://tsibrov.blogspot.com/2020/09/LiquidCrystal-I2C-Menu.html](https://tsibrov.blogspot.com/2020/09/ LiquidCrystal-I2C-Menu.html "https://tsibrov.blogspot.com/2020/09/LiquidCrystal-I2C-Menu.html")
