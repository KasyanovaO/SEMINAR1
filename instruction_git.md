# **Инструкция для работы с GIT**

## Что такое GIT

GIT - это одна из реализаций распределенных систем контроля версий.

![логотип](git.jpg)

## Подготовка репозитория

Чтобы подготовить (инициализировать) новый репозиторий в текущей папке нужно ввести в терминале команду:

    git init

## Создание коммитов

### *Добавление версионности*

Чтобы отслеживать файл необходимо добавить содержимое папки с файлами в раздел проиндексированных файлов ("черновик" коммита), для этого необходимо ввести команду:

    git add

Следует отметить, что без добавления файла в "черновик" создать коммит не получится.
Также название файла необходимо указывать 
с расширением и использовать пробелы.
Например, вот так:

    git add instruction_git.md

### *Фиксация изменений*

Чтобы сохранить текущее состояние (зафиксировать его) необходимо использовать команду:

    git commit

При этом обязательно нужно описать внесенные изменения (добавить сообщение/комментарий). 
Например, вот так:

 ![пример](gitcommit.jpg)

* Кроме того, существует возможность одновременно проиндексировать файлы (отследить) и зафиксировать их. Для этого используется команда: 

    git commit -a"текст сообщения"

### *Просмотр состояния репозитория*

Чтобы показать, какие изменения были внесены с помощью команд git add и git commit используется команда:

    git status

> Сообщения о состоянии также содержат инструкции по индексированию файлов либо отмене этой операции [https://www.atlassian.com/ru/git/tutorials/inspecting-a-repository].

### *Просмотр истории коммитов*

Чтобы вызвать список действий и сохранений (журнал всех изменений) используется команда:

    git log

При вызове данной команды выводится информация об авторе, дате, идентификатор коммита и сообщение к коммиту.

* Для просмотра изменений также используется команда:

    git log --oneline
    
    Параметр oneline выводит каждый коммит в одну строку. Особенно это удобно, когда требуется просматривать большое количество коммитов.

* Чтобы отобразить весь список изменений  используется команда:

    git log --online --all

### *Просмотр коммита*

Чтобы переключиться на определенный коммит в истории изменений используется команда:

    git checkout d8bbe2f

где d8bbe2f - идентификатор коммита.

Чтобы вернуться к текущему состоянию необходимо ввести команду:
    
    git checkout master

### *Сравнение изменений*

Чтобы показать разницу между текущим и зафиксированным состоянием используется команда:

    git diff

При этом все изменения подсвечиваются разными цветами. 
Кроме того, данная команда используется для сравнения коммитов. Например, 
    
    git diff 15ef16c 1813756

где 15ef16c и 1813756 - идентификаторы коммитов, которые требуется сравнить.

## Ветвление

В основном ветки в Git используется в следующих случаях:
 * чтобы несколько программистов могли вести работу над одним и тем же проектом;
 * чтобы не повредить основному проекту, создается новая ветка, из которой в дальнейшем переносятся изменения на основную ветку. 

### *Просмотр существующих веток*

Для просмотра списка всех существующих веток нужно вести команду: 

    branch

### *Создание новых веток*

Для создания новой ветки нужно вести команду:
    
     git branch <имя_ветки>

### *Переключение между ветками*

Чтобы переключиться между ветками используется комнада:

    git checkout <имя_ветки>

### *Слияние новых веток*

Когда мы правим информацию в текущей ветке, 
автоматического слияния с основной веткой не происходит. Для этого нам необходимо совершить некоторые действия.

Для того чтобы влить другую ветку в текущую нужно:
- переключиться на ту ветку **куда** вливаем
- ввести команду слияния, указав ту ветку, **которую** вливаем.

Команда для слияния:
    
    git merge <имя_ветки>

**Кофликт изменений**.
При работе в двух ветках может 
возникнуть ситуация, когда в одной и другой 
ветке по-разному изменили блок текста. 
Если затем попробовать слить эти ветки, Git 
сообщит о конфликте и предложит выбрать изменения, которые требуется записать. Поэтому у проекта в репозитории должен быть один 
ответственный пользователь, наделённый правом проводить слияния и разрешать конфликты.

### *Удаление веток*

Если ветка в дальнейшем не потребуется ее можно удалить. Для этого используется команда:
 
    git branch -d <имя_ветки>

### *Визуализация веток*
Ключ -graf в связке с командой log позволяет отобразить список коммитов в виде дерева:

    git log --graph 

Кроме того, используются следующие команды:
    
    git log --all --oneline --graph 
    git log --oneline --graph.

## Заключение

Таким образом, в инструкции представлены основные команды Git для создания репозитория Git, добавления файлов (отслеживания) и их фиксации, просмотра изменений, а также показаны некоторые команды ветвления и слияния.

## Работа с удаленными репозиториями
### Создание нового удаленного репозитория
### Отправка изменений в удаленный репозиторий
### Получение изменений 
