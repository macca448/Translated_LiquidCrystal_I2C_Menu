## LiquidCrystal_I2C_Menu
**LiquidCrystal_I2C_Menu** - LiquidCrystal_I2C_Menu is a library for creating a user interface on Arduino and a text LCD with an I2C interface. The library provides functionality for formatted output, input and selection of values, menu organization. The control is carried out using a rotation encoder with a button.

## Connection
[![LiquidCrystal_I2C_Menu Подключение](https://github.com/VladimirTsibrov/LiquidCrystal_I2C_Menu/raw/master/wiring/LiquidCrystal_I2C_Menu%20wiring.png "LiquidCrystal_I2C_Menu Подключение")](https://github.com/VladimirTsibrov/LiquidCrystal_I2C_Menu/raw/master/wiring/LiquidCrystal_I2C_Menu%20wiring.png "LiquidCrystal_I2C_Menu Подключение")

## Button control
Buttons can be used instead of a rotation encoder. There is another version of this library for this. - [LiquidCrystal_I2C_Menu_Btns](https://github.com/VladimirTsibrov/LiquidCrystal_I2C_Menu_Btns "LiquidCrystal_I2C_Menu_Btns")

## Functions
Along with the standard functions inherited from the LiquidCrystal_I2C library, this library implements the following:
- **printAt(x, y, text)** – вывод текста на дисплей с указанной позиции.
- **printf(format, …)** – форматированный вывод текста. Действуют те же правила, что и в других функциях форматированного вывода, например, sprintf.
- **printfAt(x, y, format, …)** – форматированный вывод с указанной позиции.
- **attachEncoder(pinA, pinB, pinBtn)** – сообщает библиотеке, к каким выводам Ардуино подключен энкодер.
- **getEncoderState()** – опрос состояния энкодера. Возвращает значение типа eEncoderState (перечисляемый тип, описан в библиотеке как {eNone, eLeft, eRight, eButton}).
- **printMultiline(text)** – вывод длинного текста с возможностью вертикальной прокрутки. Возврат из функции осуществляется при нажатии кнопки энкодера.
- **inputVal(title, min, max, default, [step], [onChangeFunc])** – ввод числового значения. title – заголовок; параметры min и max задают диапазон, в котором может изменяться значение; default – начальное значение; step – величина приращения, по умолчанию равна 1; необязательный параметр onChangeFunc - указатель на функцию, которая должна вызываться при изменении значения.
- **inputValAt(x, y, min, max, default, [step], [onChangeFunc])** – аналогична функции inputVal, но в отличие от нее не очищает дисплей при вызове и ввод значения осуществляется с указанной позиции.
- **inputValBitwise(title, value, precision, [scale], [signed])** – позволяет вводить значения путем редактирования отдельных разрядов числа. Параметр title определяет заголовок; value – ссылка на переменную, в которую будет помещен результат ввода; precision – общее количество разрядов в числе; scale – количество разрядов после запятой, значение по умолчанию 0; signed – разрешает (при значении true) или запрещает (при значении false – по умолчанию) ввод отрицательных чисел. Функция возвращает true, если пользователь подтвердил ввод, false, если отказался.
- **inputStrVal(title, buffer, length, available_symbols)** – аналогично функции inputValBitwise предоставляет возможность поразрядного ввода, но кроме цифр могут быть введены и другие символы. Параметр title определяет заголовок; buffer – ссылка на символьный буфер, в который будет помещен результат ввода; length – количество вводимых символов; параметр available_symbols – это строка символов, доступных для ввода. Функция возвращает true, если пользователь подтвердил ввод, false, если отказался.
- **selectVal(title, list_of_values, count, [show_selected], [selected_index])** – позволяет выбрать значение из списка list и возвращает индекс выбранного элемента.  title – отображаемый на дисплее заголовок; list – список значений для выбора, представляет собой массив значений типа char*, String или int; count – количество элементов в массиве; show_selected - флаг отображения метки на выбранном элементе; selected_index – индекс выбранного по умолчанию элемента.
- **showMenu(menu, menu_length, show_title)** – отображает меню и возвращает ключ выбранного элемента. menu – массив элементов типа sMenuItem; menu_length – длина меню; show_title – признак необходимости отображения заголовка.
- **getSelectedMenuItem()** – возвращает ключ выбранного пункта меню для использования внутри обработчиков.
- **attachIdleFunc(IdleFunc)** – позволяет привязать функцию, которая будет вызываться библиотекой при бездействии.

## Поддержка дисплеев с кириллицей
Для включения поддержки дисплеев с кириллицей необходимо в файле LiquidCrystal_I2C_Menu.h раскомментировать строку #define CYRILLIC_DISPLAY. После этого станет возможным использование русского текста в меню и других функциях библиотеки.


## Более подробно
Более подробную информацию о библиотеке и её функциях вы найдете здесь: [https://tsibrov.blogspot.com/2020/09/LiquidCrystal-I2C-Menu.html](https://tsibrov.blogspot.com/2020/09/LiquidCrystal-I2C-Menu.html "https://tsibrov.blogspot.com/2020/09/LiquidCrystal-I2C-Menu.html")
