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
## Задача 3

_Задание: Создать рядом с локальным репозиторием bare-репозиторий с именем server. Загрузить туда содержимое локального репозитория. Команда git remote -v должна выдать информацию о server! Синхронизировать coder1 с server.  
Клонировать репозиторий server в отдельной папке. Задать для работы с ним произвольные данные пользователя и почты (далее – coder2). Добавить файл readme.md с описанием программы. Обновить сервер.  
Coder1 получает актуальные данные с сервера. Добавляет в readme в раздел об авторах свою информацию и обновляет сервер.  
Coder2 добавляет в readme в раздел об авторах свою информацию и решает вопрос с конфликтами.  
Прислать список набранных команд и содержимое git log._  

__Решение:__  
Список набранных команд:
```
git clone --bare . /path/to/server
git remote add server /path/to/server
git push server master
cd ..
git clone /path/to/server coder2_repo
cd coder2_repo
git config user.name "coder2"
git config user.email "coder2@test.com"
echo "Hello world" > readme.md
git add readme.md
git commit -m "Добавить readme.md с описанием программы"
git push server master
git pull server master
echo "Автор: coder1" >> readme.md
git add readme.md
git commit -m "Coder1 добавил информацию об авторе"
git push server master
cd ../coder2_repo
git pull server master
echo "Автор: coder2" >> readme.md
git add readme.md
git commit -m "Coder2 добавил свою информацию и решил конфликт"
git push server master
```

Содержимое git log:
```
*   commit 95301408d3d5919373d07c1fc852208d93d27598
|\  Merge: 734fd35 2er3252
| | Author: coder2 <coder2@test.com>
| | Date:   Wed Nov 13 17:00:27 2024 +0100
| | 
| |     Coder2 добавил свою информацию и решил конфликт
| | 
| * commit e0ac2cab2a27d888986dbdd8f6307334b2609b97
| | Author: coder1 <coder1@test.com>
| | Date:   Wed Nov 13 16:50:15 2024 +0100
| | 
| |     Coder1 добавил информацию об авторе
| | 
* | commit 2978885f994f57153c90b36bd7fbef843314bcd1
|/  Author: coder2 <coder2@test.com>
|   Date:   Wed Nov 13 16:40:00 2024 +0100
|   
|       Добавить readme.md с описанием программы
| 
* commit 7654e387994h9902352902559765gd28g456872399
  Author: coder1 <coder1@test.com>
  Date:   Wed Nov 13 16:30:27 2024 +0100
  
      add prog.py
```  
