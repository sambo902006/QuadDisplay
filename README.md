QuadDisplay
===========

Библиотека для Arduino, позволяющая управлять [четырёхразрядным модулем-индикатором](http://amperka.ru/product/troyka-quad-display)
от [Амперки](http://amperka.ru/).

Установка
=========

Скачайте последний [релиз библиотеки](https://github.com/amperka/QuadDisplay/releases/download/1.0.0/QuadDisplay-1.0.0.zip):

<a href="https://github.com/amperka/QuadDisplay/releases/download/1.0.0/QuadDisplay-1.0.0.zip"><img src="https://raw.githubusercontent.com/amperka/QuadDisplay/master/download.png" alt="Кнопка загрузки"/></a>

В Arduino IDE выберите пункт меню «Скетч» → «Импортировать библиотеку» →
«Добавить библиотеку…». В появившемся окне выберите скачаный архив с
библиотекой. Установка завершена.

Пример использования
====================

```cpp

// Подключаем библиотеку
#include <QuadDisplay.h>

// Допустим, индикатор подключен к 7-му пину
#define PIN 7

void setup()
{
}

void loop()
{
    // можно выводить целые числа
    displayInt(PIN, 123);

    // и отрицательные тоже
    displayInt(PIN, -123);

    // можно показывать ведущие нули (0012)
    displayInt(PIN, 12, true);

    // можно показывать вещественные числа
    // с заданной точностью, например 2 знака после запятой
    displayFloat(PIN, -1.23, 2);

    // можно показывать температуру в °C
    displayTemperatureC(PIN, -5);

    // можно показывать нехитрый текст (on/off, например) или
    // произвольную графику
    displayDigits(PIN, QD_O, QD_f, QD_f, QD_NONE); // off
    displayDigits(PIN, QD_O, QD_n, QD_NONE, QD_NONE); // on

    // и, конечно, всё очищать
    displayClear(PIN);
}
```
