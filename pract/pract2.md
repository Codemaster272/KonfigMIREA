# Практическое занятие №2. Менеджеры пакетов
## Задача 1

_Задание: Вывести служебную информацию о пакете matplotlib (Python). Разобрать основные элементы содержимого файла со служебной информацией из пакета. Как получить пакет без менеджера пакетов, прямо из репозитория?_


__Решение:__  
`pip show matplotlib` - выводит служебную информацию о пакете matplotlib  
Вывод:  
![pract2_1](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_1.png)  
![/pract2_1_2](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_1_2.png)

Основные элементы служебной информации пакета matplotlib:

- Name (Имя): Название пакета
- Version (Версия): Текущая версия пакета
- Summary (Описание): Краткое описание 
- Home-page (Домашняя страница): URL официального сайта 
- Author (Автор): Имена авторов и основных участников проекта
- Author-email (Email автора): Контактный email 
- License (Лицензия): Тип лицензии 
- Location (Расположение): Путь к установленному пакету в файловой системе
- Requires (Зависимости): Список зависимых пакетов
- Required-by (Зависимые пакеты): Пакеты, которые зависят от matplotlib


Чтобы получить пакет matplotlib без использования менеджера пакетов, можно скачать его исходный код непосредственно из официального репозитория GitHub.


## Задача 2

_Задание: Вывести служебную информацию о пакете express (JavaScript). Разобрать основные элементы содержимого файла со служебной информацией из пакета. Как получить пакет без менеджера пакетов, прямо из репозитория?_


__Решение:__  
`npm show express` - выводит служебную информацию о пакете express  
Вывод:  
![pract2_2](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_2.png)  

Основные элементы служебной информации пакета express:

- Name (Имя): Название пакетае
- Version (Версия): Текущая версия пакета 
- Fast, unopinionated, minimalist web framework (Быстрый, минималистичный веб-фреймворк без строгих правил)
- Homepage (Домашняя страница)
- Dependencies (Зависимости): Пакеты, от которых зависит express
- Maintainers (Сопроваждающие)
- Dist-tags (Теги дистрибутива)
- Published: Кем и когда опубликован


Чтобы получить пакет express без использования менеджера пакетов, можно скачать его исходный код непосредственно из официального репозитория GitHub.


## Задача 3

_Задание: Сформировать graphviz-код и получить изображения зависимостей matplotlib и express_

### Matplotlib
__Решение:__  
`pipdeptree --packages matplotlib` - Выводит зависимости пакета matplotlib    
Вывод:  
![pract2_3_1](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_3_1.png)  

На основе этих данных формируем graphviz-код  

>digraph MatplotlibDeps {  
    "matplotlib@3.9.2" -> "contourpy@1.3.0";  
    "matplotlib@3.9.2" -> "cycler@0.12.1";  
    "matplotlib@3.9.2" -> "fonttools@4.54.1";  
    "matplotlib@3.9.2" -> "kiwisolver@1.4.7";  
    "matplotlib@3.9.2" -> "numpy@2.1.1";  
    "matplotlib@3.9.2" -> "packaging@24.1";  
    "matplotlib@3.9.2" -> "pillow@10.4.0";  
    "matplotlib@3.9.2" -> "pyparsing@2.4.7";  
    "matplotlib@3.9.2" -> "python-dateutil@2.9.0.post0";  
>      
>    "contourpy@1.3.0" -> "numpy@2.1.1";  
    "python-dateutil@2.9.0.post0" -> "six@1.16.0";  
}  

На основе graphviz-кода генерируем граф  
![MatplotlibGraph](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/MatplotlibGraph.png)  

### Express

`npm ls --depth=1` - Выводит зависимости пакета express  
Вывод  
![pract2_3_2](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_3_2.png)

На основе этих данных формируем graphviz-код  

>digraph ExpressDeps {  
    "express" -> "accepts@1.3.8";  
    "express" -> "array-flatten@1.1.1";  
    "express" -> "body-parser@1.20.3";  
    "express" -> "content-disposition@0.5.4";  
    "express" -> "content-type@1.0.5";  
    "express" -> "cookie-signature@1.0.6";  
    "express" -> "cookie@0.6.0";  
    "express" -> "debug@2.6.9";  
    "express" -> "depd@2.0.0";  
    "express" -> "encodeurl@2.0.0";  
    "express" -> "escape-html@1.0.3";  
    "express" -> "etag@1.8.1";  
    "express" -> "finalhandler@1.3.1";  
    "express" -> "fresh@0.5.2";  
    "express" -> "http-errors@2.0.0";  
    "express" -> "merge-descriptors@1.0.3";  
    "express" -> "methods@1.1.2";  
    "express" -> "on-finished@2.4.1";  
    "express" -> "parseurl@1.3.3";  
    "express" -> "path-to-regexp@0.1.10";  
    "express" -> "proxy-addr@2.0.7";  
    "express" -> "qs@6.13.0";  
    "express" -> "range-parser@1.2.1";  
    "express" -> "safe-buffer@5.2.1";  
    "express" -> "send@0.19.0";  
    "express" -> "serve-static@1.16.2";  
    "express" -> "setprototypeof@1.2.0";  
    "express" -> "statuses@2.0.1";  
    "express" -> "type-is@1.6.18";  
    "express" -> "utils-merge@1.0.1";  
    "express" -> "vary@1.1.2";  
}  

На основе graphviz-кода генерируем граф  
![ExpressGraph](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/ExpressGraph.png) 

## Задача 4

_Задание: Решить на MiniZinc задачу о счастливых билетах. Добавить ограничение на то, что все цифры билета должны быть различными (подсказка: используйте all_different). Найти минимальное решение для суммы 3 цифр._


__Решение:__  
Код программы:  
```MiniZinc
include "globals.mzn";

array[1..6] of var 0..9: digits;
constraint all_different(digits);

var int: sum_first = sum(digits[1..3]);
var int: sum_last = sum(digits[4..6]);

constraint sum_first = sum_last;
solve minimize sum_first;
```
Вывод:  
![pract2_4](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_4.png)  

## Задача 5

_Задание: Решить на MiniZinc задачу о зависимостях пакетов для рисунка, приведенного ниже._  
Рисунок к заданию:  

![Task_image](https://raw.githubusercontent.com/true-grue/kisscm/refs/heads/main/pract/images/pubgrub.png)  

__Решение:__  
Код программы:  
```MiniZinc
set of int: MenuVersion = {100, 110, 120, 130, 150};
set of int: DropdownVersion = {230, 220, 210, 200, 180};
set of int: IconsVersion = {100, 200};

var MenuVersion: menu;
var DropdownVersion: dropdown;
var IconsVersion: icons;

constraint if menu >= 110 then dropdown >= 200 else dropdown = 180 endif;

constraint if dropdown <= 200 /\ dropdown > 180 then icons = 200 else icons = 100 endif;

solve satisfy;
```

Вывод:  
![pract2_5](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract2/pract2_5.png)  

## Задача 6

Задание:Решить на MiniZinc задачу о зависимостях пакетов для следующих данных:  

root 1.0.0 зависит от foo ^1.0.0 и target ^2.0.0.  
foo 1.1.0 зависит от left ^1.0.0 и right ^1.0.0.  
foo 1.0.0 не имеет зависимостей.  
left 1.0.0 зависит от shared >=1.0.0.  
right 1.0.0 зависит от shared <2.0.0.  
shared 2.0.0 не имеет зависимостей.  
shared 1.0.0 зависит от target ^1.0.0.  
target 2.0.0 и 1.0.0 не имеют зависимостей.  

__Решение:__  
Код программы:  
```MiniZinc
set of int: FooVersion = {100, 110};   
set of int: LeftVersion = {100};   
set of int: RightVersion = {100};      
set of int: SharedVersion = {200};     
set of int: TargetVersion = {100, 200};

var FooVersion: foo;
var LeftVersion: left;
var RightVersion: right;
var SharedVersion: shared;
var TargetVersion: target;

% root 1.0.0 depends on foo ^1.0.0 and target ^2.0.0
constraint foo >= 100 /\ target = 200;

% foo 1.1.0 depends on left ^1.0.0 and right ^1.0.0
constraint if foo = 110 then left >= 100 /\ right >= 100 else true endif;

% left 1.0.0 depends on shared >= 1.0.0
constraint if left = 100 then shared >= 100 else true endif;

% right 1.0.0 depends on shared < 2.0.0

% constraint if right = 100 then shared < 200 else true endif;

solve satisfy;
```

Вывод:  
![image](https://github.com/user-attachments/assets/cd3be6b1-7315-431e-897e-6a8cfdb44fff)
