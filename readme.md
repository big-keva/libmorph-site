# LibMorph (v2.4.1)

![License: MIT](https://img.shields.io)
![Platform: Windows | Linux](https://img.shields.io)
![Language: C++](https://img.shields.io)

Высокопроизводительное ядро морфологического анализа русского языка на базе детерминированных конечных автоматов (DFA). 

## Ключевые особенности
* **Встроенный словарь:** База (~40MB RAM) уже интегрирована в библиотеку.
* **Производительность:** Свыше 1.2 млн слов/сек на одном ядре.
* **Zero-allocation:** Минимальное использование кучи, работа через внешние буферы.
* **Двойной интерфейс:** Нативная поддержка ANSI (`IMlmaMb`) и WideChar (`IMlmaWc`).

## Быстрый старт (C++)

```cpp
#include "libmorph.h"

// Получение интерфейса (ANSI)
IMlmaMb* pMorph;
GetInterface(IID_IMlmaMb, (void**)&pMorph);

pMorph->Attach(); // Инициализация словарей

SLemmInfoA info;
char lemma[256];

// Морфологический разбор
pMorph->Lemmatize("программисты", 0, &info, 1, lemma, 256, nullptr, 0, sfStopAfterFirst);

pMorph->Detach();

Сборка
Проект использует CMake:
bash
mkdir build && cd build
cmake ..
make
Используйте код с осторожностью.

Лицензия
Распространяется под лицензией MIT. Подробности в файле LICENSE.
