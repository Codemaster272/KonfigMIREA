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
Вывод в текстовом виде:
```
root@wry-yak :~ # git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: git config -- global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: git branch -m <name>
Initialized empty Git repository in /root/.git/
root@wry-yak :~ # git config user.name "coder1"
root@wry-yak :~ # git config user.email "coder1@test.com"
root@wry-yak :~ # echo print > prog.py
root@wry-yak :~ # git add prog.py
root@wry-yak :~ # git commit -m "add prog.py"
[master (root-commit) 5bd4cb0] add prog.py
1 file changed, 1 insertion(+)
create mode 100644 prog.py
root@wry-yak :~ # git log
commit 5bd4cb0f7fb2948532b8a7a5b21046b429379b11 (HEAD -> master)
Author: coder1 <coderl@test.com>
Date: Wed Nov 13 16:30:27 2024 +0100

  add prog.py
```
Следующие задания в процессе выполнения...
