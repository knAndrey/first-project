# **Конспект по Git** :pencil:
## **Первый модуль**
### Начало работы. Функции внутри Git.Bash
1. Pwd //- print working directory, в какой сейчас директории

2. ls //- list directoty contents
ls -a //- вывели список, в котором отображаются скрытые файлы ., .., и .git. начинаются с точки
ls ~ //- содержимое домашней директории
ls .. //- содержимое родительское директории

3. cd имя_папки // - change directory
cd .. //- вернуться в родительскую папку
cd . //- переход в текущую директорию

### Создание файла/папки. Копирование содержимого
4.touch имя_файла. расширение //- чтобы создать файл. Расширение лучше писать

5.mkdir new-dir //- создать директорию через терминал
mkdir -p dir1/dir-inside/dir-deeper-inside имя_структуры//- создать структуру директорий

По умолчанию touch и mkdir создают файлы и папки в текущей рабочей директории

mkdir ~/my-git-projects // создаёт папку my-git-projects внутри домашней директории


6. cp что_копируем куда_копируем//- копирование файлов
cp index.html style.css script.js src/ //скопировали три файла в папку src

7. mv что_перемещаем куда// move

8. cat myfile.txt // concatenate(объединить), and print, распечатает(прочитает) то, что содержится в файле. Только текстовые файлы
### Удаление файла/папки
9. rm example.txt // remove, удалить файл
10. rmdir images // директорию
rm -r //- recursive, последовательно удалить папку со всем её содержимым. Удаление необратимо

Сразу несколько команд:
mkdir second-project && cd second project && touch index.html style css

Команды из буфера(buffer- посредник)
Чтобы обратиться к последней введённой команде, нажмите стрелку вверх. Предпоследняя- два раза

### Автозаполнение :trollface:
Название команды: набрать буквы, дважды нажать на Tab
11. Путь: имя папки или файла в одной директории, Tab. Если не заполняется, то есть несколько папок или файлов, которые начинаются точно так же. Tab ещё раз- увидите их список
cd U[Tab]

cd~/[Tab]
Слишком большой вывод: do you wish to see all 426 possibilities(429 line)? Ответ: y , если да. n ,если нет

12. Попасть в корневую директорию:
cd c:/
или cd /c

### Создание имени пользователя для GitHub

git config — global user.name "User Ya" //- команда configuration, ключ —global. Раздел user.name
git config —global user.email user@mail.ru

Все глобальные настройки Git хранит в файле .gitconfig
cat ~/.gitconfig или git config —list
---
## **Второй модуль** :pray:
Git- репозиторий (repository- хранилище)
initialize
### Подготовка репозитория
1. Создать репозиторий:
1)Перейти в папку
2)git init
:exclamation: Не рекомендуется создавать репозиторий внутри другого репозитория, потому что это может вызвать ошибки с отслеживанием изменений
В подпапке .git репозитория вся служебная информация

2. Разгитить папку: cd <папка с репозиторием> && rm -rf .git
f- force. Удалить без вопросов
git status //- текущее состояние репозитория
Коммит- фиксация состояний в Git

3. git add —all //- подготовить к сохранению все файлы в репозитории
Или git add . //- добавить текущую папку целиком
Команда git add не сохраняет содержимое файлов в репозитории. Как добавление товаров в корзину, а сохранение- оформление/оплата. Сохранение/фиксация- через коммит
Можно без ключа —all: git add todo.txt

4. git commit -m 'Мой первый коммит'//- сделать коммит' с ключом message(в чем именно изменения) :dizzy_face:
[master (room-commit) baa3b6e]:
Коммит был в ветке master;
room-commit -это самый первый, корневой коммит в ветке
baa3b6e- аббревиатура сокращённого идентификатора комммита

create(или delete) mode 100644
mode 100644- то есть обычный файл
mode 100755 для исполняемых файлов( например, file.exe). 120000- файлы-ссылки в Linux
Фотография. Просишь встать в ряд - git add. Фотографируешь- git commit

5. git log //- увидеть число всех коммитов

### Синхронизация репозитория.
SSH ключ- Secure Shell Protocol
Private key
Public key. Доступен всем
По умолчанию SSHключи находятся в домашней директории пользователя
1. ls -la .ssh/ //вывели список создания ключей. В директории .ssh/

2. ssh-keygen -t ed25519 -C"электронная почта, к которой привязан ваш аккаунт на GitHub"
passphrase: pustbudettrest

проверить наличие созданных ключей :
ls -a ~/.ssh
ls -la ~/.ssh

3. Скопировать содержимое файла с публичным ключом в буфер обмена:
clip < ~/.ssh/id_ed25519.pub

4. Проверить правильность ключа:
ssh -T git@github.com
URL- uniform resour
ce locator
git remote add origin ссылка из ssh
5. Убедиться, что репозитории связаны:
git remote -v
Флаг -v это короткая форма флага —verbose(подробный). Показать больше информации о выводе

Ветка main или master  :japanese_ogre:

6. git push. //- загрузить содержимое локального репозитория на GitHub
В первый раз:
git push -u origin master
Потом можно без -u

7. Markdown- язык разметки(отступы)
Заголовки разных уровней создаются решётками:
# H1 //- заголовок 1 уровня, самый большой
## Н2 //- 2 уровня
###### //- заголовок 6 уровн,, самый меленький

Добавить черту между заголовками:
#### Заголовок 4
Текст над чертой
---
Текст под чертой

Разрыв строки: два пробела или

Новый параграф: enter 2 раза
line

another line
Если 1 Enter, текст сольётся в 1 строку на
Выделение текста
Курсив *текст* или _текст_
Полужирный **текст** или __текст__
или **текст и _текст_**
Зачеркнуть текст ~~текст~~

Списки: цифры с точкой в начале строки
1. Первый пункт нумерованного списка
2. Второй пункт
Не нумерованный список:
*Первый пункт
*второй пункт
Или
-первый пункт
-второй пункт

Ссылка:
[Яндекс] (https///www.yandex.ru)
With title:
[Яндекс] (https///www.yandex.ru 'I am Yandex)

Чтобы оформить текст, как код:
Тройные косые кавычки, грависы
```bash
ls -la
```
``` html
<h1>А я текст </h1>

## **Тема 5. Кэширование**
Хэширование- способ преобразовать набор данных и получить их "отпечаток"
Secure Hash Algorithm( SHA-1)
Хэш- обычно короткая строка из цифр от 0 до 9, букв от А до F
букв
Хэш- основной идентификатор коммита

log- журнал записей
Сокращённый log:
git log —oneline
Если выход из просмотра logов не прошел автоматически, нажмите кнопку "Q" (Quit)

*Файл Head- один из служебных файлов папки .git*
cd .git
cat Head //- показывает содержимое файла

Делаем коммит-> git обновляет refs/heads/master, записывает в него хэш последнего коммита
Head- это файл в папке .git, не команда

Файл добавили в staging area с помощью команды git add. Файл в состоянии staged
Коммит' как фотография. Git add добавляет персонажей на сцену для общей фотографии. Git commit-делает снимок
Staging area, или index(каталог), или cache(кеш).staged=indexed=cached
Modified- git сравнил содержимое с последней версией и нашёл отличия. Если не написали git add после последнего обновления

git status показывает:
staged(changes to be committed в выводе git status)
modified(changes not staged for commit)
untracked

## Тема 6. Оформление сообщений к коммитам
В выводе команды git log —oneline умещается максимум 72 первых символа сообщения
Корпоративный подход
Jira- система для организации проектов и задач( LGS- logistics) 239- задача
git commit -m "LGS-239: Дополнить список пасхалок новыми числами"

### Стандарт Conventional Commits
Подходит для репозиториев с исходным кодом программ
Формат коммита: <type>: <сообщение>
Type:
Feat( от "feature")- для новой функциональности
Fix- для исправления ошибок
Пример: git commit -m "feat: добавить подсчет суммы заказов заказов за неделю"

### GitHub стиль
GitHub можно использовать не только для хранения, но и для ведения списка задач проекта. Ссылка на номер задачи в любом месте
git commit -m "Исправить #334, добавить график температуры)