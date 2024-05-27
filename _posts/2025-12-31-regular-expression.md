---
title: Основы регулярных выражений
description: >-
  Разберемся как работают регулярные выражения на реальных примерах
  Постепенно перейдем от простого к сложному
author: alex
date: 2025-12-31 18:00:00 +0300
categories: [Basics]
tags: [regular Expression]
---

Регулярные выражения используются повсеместно редакторы кода, различные языки программирования. Уметь их использовать очень важно.

## Модификаторы

Модифицировать дефолтное поведение регулярных выражений можно с помощью флагов (модификаторов) они указываются после строки-шаблона.

- `g` ищет все совпадения, а не только первое вхождение
- `i` регистронезависимый поиск
- `m` мультистроковость
- `u` поддержка юникода

## Базовый поиск

````regexp
/при/gu
````

Это пока обычный поиск, найдем все упоминания `при` в тексте, никакого профита в этом нет, но гибкость регулярок в символьных классах.

## Символьные классы
 
Комбинация символов в квадратных скобках

Найдем в тексте все упоминания телефона.

````text
телефоны и на телефоне и не тот телефон
````

````regexp
/телефон[еы]?/gu
````

> Символьные классы могут быть в любом месте выражения.
{: .prompt-info }
 
Примеры

| Строка поиска | Выражение     | Результат     | Описание                   |
|---------------|---------------|---------------|----------------------------|
| `гад сад рад` | `/[гср]ад/gu` | `гад сад рад` | Нашли все упоминания слова |

https://www.youtube.com/watch?v=ozFNilK4qrc&t=1290s

https://regex101.com/

https://devanych.ru/technologies/shpargalka-po-regulyarnym-vyrazheniyam