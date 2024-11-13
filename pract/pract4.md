# Практическое занятие №4. Системы контроля версий
## Задача 1
_Задание: На сайте https://onlywei.github.io/explain-git-with-d3 или http://git-school.github.io/visualizing-git/ (цвета могут отличаться, есть команды undo/redo) с помощью команд эмулятора git получить следующее состояние проекта (сливаем master с first, перебазируем second на master): см. картинку ниже. Прислать свою картинку._  
![task_image](https://github.com/true-grue/kisscm/raw/main/pract/images/git.png)

__Решение:__  
Вводим следующие команды в эмулятор
```
git commit
git tag in
git checkout in
git checkout -b first
git commit
git checkout in
git checkout -b second
git commit
git commit
git checkout master
git checkout -d second
git commit
git checkout first
git commit
git checkout master
git merge first
git commit
git commit
git checkout -b second
git checkout in
```  
Вывод:
![pract4_1](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract4/pract4_1.png)  

## Задача 2
_Задание: Создать локальный git-репозиторий. Задать свои имя и почту (далее – coder1). Разместить файл prog.py с какими-нибудь данными. Прислать в текстовом виде диалог с git._  

__Решение:__
Вводим следующие команды в командную строку
```
git init
git config user.name "coder1"
git config user.email "coder1@test.com"
echo print > prog.py
git add prog.py
git commit -m "add prog.py"
```
Вывод:  
![pract4_2](https://raw.githubusercontent.com/Codemaster272/KonfigMIREA/refs/heads/main/pract/images/pract4/pract4_2.png)  

Следующие задания в процессе выполнения...
