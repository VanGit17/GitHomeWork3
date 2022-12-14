# Базовые команды для git 
## начальное знакомство

Для началаработы git нужно инициализировать папку(сделать её репозиторием), чтобы система git фиксировала изменения происходящие в ней. Для этого используется команда:
* **git init**

При первом входе, необходимо представиться системе, используя команды:

* **git config --global user.name "Ваше имя"**
* **git config --global user.email "Ваш имейл"**
## Фиксация изменений в файле

для того, чтобы git зафиксировал изменения в файле 
необходимо выполнить **обязательную последовательность из трёх действий**:

1. Сохранить файл на жесткий диск, нажатием ***ctrl+S*** Поскольку git фиксирует только сохраненные изменения
2. Нужно сообщить git, что мы хотим зафиксировать
 изменения в конкретном файле командой:
 * **git add** имя файла
3. сохранить изменение в фале в git и оствить комментарий при помощи команды:
* **git commit -m**"*Текст комментария*"

## Работа с сохраненными версиями
1. Чтобы увидеть все сохраненные версии проекта нужно воспользоваться командой:
* **git log**
> По началу она показывает две последнии вариации.
>Чтобы увидеть все сохранения - необходимо нажать ***пробел***

>Для выхода из меню выбора сохранений - нужно нажать ***Q***
2. Чтобы загрузить выбранное сохранение состояния проекта существует команда:
* **git checkout имя сохранения** 
>Достаточно указать первые пять символов имени


<code>![иллюстрация](/Pic1.jpg "выбор сохранения")
</code>

>Для работы нужно указать не только
интересующий вас коммит, но и вернуться 
в тот, где работаем, при помощи команды ***git checkout master***

## Дополнительные команды 
* **git --version** Показывает версию git, если он установлен

* **git status** Показывает есть ли изменения которые можно сохранить в git

* **git diff** Показывает разницу между текущим сохраненным файлом изменениями, сохраненными в git 
<code>[см иллюстрацию](/gd.jpg "git diff")
</code>

# Работа с ветками

## Создание веток

1. Перед созданием новой ветки необходимо удостовериться в какой ветке мы находимся и какие ветки уже есть, для этого существует команда:
* **git branch** выводит существующие ветки, указывая зеленым актуальную ветку, в которой мы находимся 
2. Новая ветка создается этой же коандой с указанием имени создаваемой ветки
* **git branch _имя создаваемой ветки_**

3. Для перехода между ветками используем команду
* **git checkout _имя ветки в которую хотим перейти_**

## Слияние веток
 1. Для слияния веток используется команда 
 * **git merge _имя ветки_** Сливает ветку, в которой мы находимся, с веткой имя которой мы указали
 2. Если при слиянии веток в файле на одной и той же строке содержится разный текст возникает **конфликт** Самый удобный способ разрешить его вручную, приняв оба варианта текста в файл и самостоятельно внеся необходимые исправления.


## Файл .gitignore

* для того, чтобы git игнорировал выбранные файлы в папке проекта, необходимо создать файл без имени с расширением **_.gitignore_**
* в данном файле необходимо разместить список имен файлов, изменение которых программе git необходимо игнорировать

## Дополнительные команды

* **git branch -d _Имя ветки_** удаляет ветку, если все изменения в ней сохранены
* **git log --graph** выводит удобное графическое изображение веток

# Работа с удаленными репозиториями

1. для скачивания открытого репозитория на ваш компьтер существует команда:
* **git clone _адрес ссылки на удаленный репозиторий_**

## если вы хотите работать с собственным удаленным репозитоием:

1. Необходимо создать аккаунт на сайте **GitHub.com** Самый популярный сайт для создания удаленных репозиториев и работы с ними. 
 
2. Чтобы связать свой локальный репозиторий и удаленый, воспользуйтесь набором команд:
* **git remote add origin _ссылка на ваш удаленный репозиторий_** - устанавливает связь с удаленным репозиторием, origin - стандартное название удаленногго репозитория.
* **git branch -M main** - определяет главную ветку репозитория (?удаленного или обоих)
* **git push -u origin main** - отправляет файлы из локального репозитория в удаленный

3. После связи вашего локального и удаленного репозиториев 
* **git push** - отправляет сделанные commit'ы с вашего локального репозитория на удаленный
* **git pull** - вносит в ваш локальный репозиторий commit'ы с удаленного репозитория.

## Для создания pull request'ов необходимо выполнить следующую последовательность действий:

1. Делаем **fork** интересующего нас репозитория.Чтобы сделать копию интересующего репозитория в своём аккаунте.
2. Делаем **git clone** для нашей версии этого репозитория у себя на компьютере
3. Создаем ветку с предлагаемыми изменениями
4. Производим все изменения только в этой ветке
5. Отправляем эти изменения на свой аккаунт (**git push**)
6. В окне GitHub появляется возможность отправить pullrequest с нашими изменениями