## Подготовка к бассейну Школы 21
В данном репозитории представлены материалы, собранные при подготовке к бассейну Школы 21 в Новосибирске, а также примеры решения задача на языке С. Задачи никак не связаны с заданиями Школы 21, найдены на просторах интеренета. Решения выполнены владельцем репозитория и не являютя единственным верным вариантом. Репозиторий писался на основании той информации, которую можно найти и собрать по кусочкам на тех же простора интеренат. Может не являться истинной, т.к. в Новосибирском кампусе обучение может отличаться от Московского и Казанского кампусов.

#### Оглавление <a name="content"></a>
- [Введение](#intro)
- [1 Работа с терминалом](#terminal)
- [2 Устанавливаем и настраиваем vim](#vim)
- [3 Компилятор gcc](#gcc)
- [4 Устанавливаем и настраиваем norminette](#norminette)
- [5 Работа с git](#git)
- [6 Hello, World!](#helloWorld)

### Введение <a name="intro"></a>
Если ты нашёл этот репозиторий, то наверняка уже много прочитал разлиной информации про Школу 21, про франшизу Школы 42, про peer-to-peer (P2P) метод обучения, про бассейн (интенсив) и т.д. и т.п. Скорей всего ты уже прошёл первый отбор: 2 игры, видео-интервью и онлайн встрчечу. Перед тобой следующий этпа - это бассейн. Как раз о нём я и постараюсь рассказать, основываясь на информации, которую смог найти сам. Опишу этапы моей подготовки.

Первое, что нужно понять, - вся работа во время интенсива будет проходить на iMac, компьютерах от Apple. Из чего можно сделать вывод, что в работе будут использоваться bash-команды (но это неточно), может быть ещё установлена zsh-командная оболочка. Командные оболочки позволяют работать в терминале с операционой системой с помощью простых команд без GUI. Прежде всего командные оболочки нужны системным администраторам для работы с серверами, где GUI вообще по факту не нужен. Но и программистам навыки работы с терминалом очень пригождаются в работе. Потому нужно научиться работать с Bash. Один из способов потренироваться, это через терминал дистрибутивов Linux, в которых уже предустановлен Bash. Будете ли вы устанавливать новую ОС, или ставить виртуальную машину, или пользоваться Live-режимом с USB-флешки - это решать вам.  

Второ - языком программирования интенсива является язык Си. Да, язык не самый популярный у новичков и не прост в понимании для начинающих. Но таковы правила Школы 21, начинать с азов. Это компилируемый статически типизированный язык программирования, потому для работы с ним нужен компилятор. По разныи источником в Школе 21 может быть компилятором как Clang, так и gcc. Я для тренировки выбрал gcc.

Третье - текстовые редакторы. На интенсиве скорей всего будут доступны только nano, emacs и vim. Советую заранее выбрать один из этих редакторов и научиться в нём работать, чтобы не тратить драгоценное время на интенсиве. Я выбрал редактор vim. Мне так вкусней.

Четвёртое - правила написания кода в Школ 21. Они есть и их нужно саблюдать, иначе можно отхватить 0 баллов за выплнение задания. Да, всё настолько строго, да, для новичков.

Пятое - работа с git. Git - это система управления версиями. У Git две основных задачи: первая - хранить информацию о всех изменениях в вашем коде, начиная с самой первой строчки, а вторая - обеспечение удобства командной работы над кодом. Каждый программист должен уметь пользоваться Git-ом. Именно сейчас вы читаете данный репозиторий на веб-сервисе GitHub, который основан на системе контроля версий Git. На бассйне работа будет завязана на локаьном git-репозитории, с помощью git-команд нужно будет отправльять решения на проверку.

И наконец, шестое - первая программа "Hello, World!", на которой я покажу все описанные выше инструменты. 

P.S. Все примеры и команды, показанные мной ниже, я выполнял в терминале дистрибутива Linux Mint 20.1 MATE в командной оболочке Bash. 

[Оглавление](#content)

### 1 Работа с терминалом <a name="terminal"><a>

Под терминалом принято понимать окружение, где можно вводить команды и получать на них ответ, это может быть физический терминал или терминал на компьютере.

Запуск терминала в Linux Mint осуществляется сочетаниями клавиш:

	Ctrl + Alt + T

Запуск терминала в macOS осущестляется другой комбинаций (не проверял):

	Command(⌘) + T

Другой способ запуска терминала в macOS:

	Ctrl + пробел

Во всплывающем окошке введите слово «Терминал» (terminal). После того, как увидите нужное приложение, просто кликните на него (не проверял).

Так выглядит терминла в Linux Mint:
![Terminal](https://github.com/robotrainer/tasks_C/blob/master/img/terminal.jpg)

**Основные команды навигации в терминале:**

Узнать, в какой рабочей папке вы находитесь:
```
$ pwd
```
Вывести список файлов и каталогов в рабочей папке:
```
$ ls
```
Вывести список файлов и каталогов в рабочей папке, включая скрытые:
```
$ ls -a
```
Вывести список файлов и каталогов с полной информацией о них в рабочей папке, включая скрытые:
```
$ ls -all
```
Команда cd используется очень часто при работе с папками в терминале. Она позволяет сменить текущую папку на произвольную. Можно использовать чтобы не набирать длинные пути, также она необходима при компиляции. По умолчанию, текущая папка - домашняя.

Перейи в подпапку домашней папки:
```
$ cd Загрузки/
```
Вернуться в предыдущую папку:
```
$ cd -
```
Перейти в родительский каталог:
```
$ cd ..
```
Быстрый переход в домашнюю папку:
```
$ cd
```
Создание файла в рабочей папке:
```
$ touch file_name.expansion
```
Создание каталога в рабочей папке:
```
$ mkdir dir_name
```
Удаление файла в рабочей папке:
```
$ rm file_name
```
Удаление каталога и рекурсивно всё его содержимое:
```
$ rm -r dir_name
```
Переименовать файл:
```
$ mv file_name file_new_name
```
Переместить файл в другой каталог:
```
$ mv file_name dir_name/
```
Копировать файл в рабочую папку:
```
$ cp file_name copy_file_name
```
Копировать каталог в другой каталог:
```
$ cp -a dir_name_1/ dir_name_2/
```
Копировать файл в каталог:
```
$ cp frile_name dir_name/
```

**Справка о командах**

Если не знаешь, как работает команда и её параметры, спроси у "мужика":
```
$ man cp
$ man ls
$ man mkdir
...
```
Чтобы узнать о параметрах команды, используйте параметр `--help`:
```
$ ls --help
$ cd --help
$ rm --help
...
```

**Прочее**

Команда `bg` позволяет посмотреть команды, которые выполняются в фоне. Если вы нажмете сочетание клавиш `Ctrl+Z`, то утилита будет свернута в фоновый режим (такое может случиться при работе в vim). Этой командой вы можете посмотреть все такие процессы для данной оболочки.
```
$ bg
```
Эта команда позволяет восстановить команду из фона, в параметрах ей нужно передать только идентификатор нужного процесса, который вы можете узнать с помощью `bg`.
```
$ fg id_process
```
[Оглавление](#content)

### 2 Устанавливаем и настраиваем vim <a name="vim"><a>

**Vim** (сокр. от **V**i **Im**proved, произносится «вим») — свободный текстовый редактор, созданный на основе более старого vi. Ныне это мощный текстовый редактор с полной свободой настройки и автоматизации, возможными благодаря расширениям и надстройкам. Пользовательский интерфейс Vim’а может работать в чистом текстовом (консольном) режиме.

Прежде чем устанавливать vim, необходимо обновить базы данных пактов (необязательно), чтобы установить последнюю версию vim:
```
$ sudo apt update
```
Установка vim:
```
$ sudo apt install vim
```
Узнать версию vim, также выводит информацию о пользовательсом файле vimrc, он нам понадобиться для настройки vim:
```
$ vim --version
```
Открыть туториал по vim:
```
$ vimtutor
```
Создать файл через vim в рабочей папке:
```
$ vim file_name.expansion
Пример:
$ vim main.c
```
Основные команды vim:

[Оглавление](#content)

---
### 3 Компилятор gcc <a name="gcc"><a>
...

[Оглавление](#content)

---
### 4 Устанавливаем и настраиваем norminette <a name="norminette"><a>
...

[Оглавление](#content)

---
### 5 Работа с git <a name="git"><a>
...

[Оглавление](#content)

---
### 6 Hello, World! <a name="helloWorld"><a>
...

[Оглавление](#content)

---  
