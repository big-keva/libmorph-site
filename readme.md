# libmorph

![License: MIT](https://img.shields.io)
![Platform: Linux | Windows](https://img.shields.io)
![Language: C++](https://img.shields.io)

Высокопроизводительные морфологические анализаторы русского, английского и украинского языков. 

## Ключевые особенности
* **Встроенный словарь:** уже интегрирован в библиотеки.
* **Минимальный размер:** Не более 4MB RAM.
* **Производительность:** Свыше миллиона слов в секунду на одном ядре.
* **Zero-allocation:** При работе не происходит операций резервирования памяти.
* **Многопоточность:** С внутренними данными работа в режиме read-only.
* **Поддержка кодировок:** Поддержка основных мультибайтовых (`IMlmaMb`) и UTF-16 (`IMlmaWc`) кодировок.

## Быстрый старт (C++)

```cpp
# include <libmorph/rus.h>

...

// Лемматизация слова (multibyte-версия)
  IMlmaMbXX*  pmorph;
  SLemmInfoA  lemmas[32];
  char        fmbuff[256];
  SGramInfo   grbuff[32];

  mlmaruGetAPI( "utf-8", (void**)&pmorph );

  nlemma = pmorph->Lemmatize( "стали", lemmas, fmbuff, grbuff );

  for ( int i = 0; i < nlemma; ++i )
    printf( "%s\tIDL:%u\n", lemmas[i].plemma, lemmas[i].nlexid );

...
```

Сборка
Проект использует CMake:
bash
mkdir build && cd build
cmake ..

Лицензия
Распространяется под лицензией MIT. Подробности в файле LICENSE.
