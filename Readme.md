# Инструкция по работе с git и удалёнными репозиториями

## Что такое git?
*Git* одна из реализаций распредённых систем контроля версий. *Git* на данный момент является самой полулярной реализацией. 

С помощью Git-a мы можем откатить свой проект до более старой версии, сравнивать, анализировать или сливать свои изменения в репозиторий.

Репозиторием называют хранилище кода и историю его изменений. 

## Подготовка репозитория
Для того, чтобы создать репозиторий используется команда *git init*. Для этого необходимо написать в терминале в папке будущего репозитория *git init* 

## Состояние репозитория
Для того, чтобы посмотреть состояние репозитория, используется команда *git status* Для этого в терминале с папкой-репозиторием необходмо написать *git status*, и возможно увидеть несколько состояний:
1. Изменённый - файл который поменялся, но ещё не был зафиксирован.

2. Индексированный — это изменённый файл в его текущей версии, отмеченный для включения в следующий коммит.

3. Зафиксированный - файл уже сохранён в локальной базе.

# Просмотр сделанных изменений
Для того, чторбы просмотреть разницу между текущей версией файла, и версией файла в полследнем коммите, используется команда *git diff*. Для этого в терминале с папкой с репозиторием, напишите *git diff*

## Создание коммитов

### Добавление файла к коммиту

Для добавления файла к коммиту используется команда *git add*. Пишется она следующим образом *git add <имя файла>* в терминале в папке с созданным репозиторием.

### Создание нового коммита

Для создание нового "сохранения" испольузется команда *git commit*. Используется она следующим образом: в терминале с папкой-репозиторием пишется *git commit -m <сообщение к коммиту>*. Сообщение к коммиту писать **ОБЯЗАТЕЛЬНО**!!! 

## Журнал изменений
Для просмотра журнала измений используется команда *git log*. Для этого в терминале в папке с репозиторием достаточно написать *git log*

## Перемещение между "сохранениями"
Для перемещения между сохранениями используется команда *git checkout*. Для того, чтобы перемиститься на указанный коммит в терминале в папке с репозиторием пишем *git checkout <номер коммита>*. **Номер коммита** берется из журнала изменений, о котором сказано выше. После перемещния на указанный коммит мы попадаем в состояние **detached head*. Чтобы вернуться к обычной работе, необходимо написать *git checkout master*.

## Отправка изменений удаленного репозитория
 Для отправки изменений в удаленный репозиторий необходимо использовать команду *git push*. Для этого втерминале с папкой с репозиторием, связанным с репозиторием, пишем команду *git push origin <название ветки>*, <название ветки> - это ветка в удаленном репозитории, куда необходимо отправить совершенные изменени

## Ветки в git
Ветки в *git* нужны, чтобы работать с "чистовиком" и "черновиками". Для того, чтобы создать новую ветку используется команда *git branch*. В терминале в папке с репозиторием, напишите *git branch <название ветки>*.

## Слияние веток и разрешение конфликтов

Чтобы слить любую ветку с текущей, вызываем команду *git merge 
<имя ветки для слияния с текущей>*.
При работе в двух ветках одновременно может возникнуть ситуация, когда в одной и другой ветке мы по-разному изменили блок текста. Если затем мы попробуем слить эти ветки, Git сообщит о конфликте и предложит выбрать, какие же изменения записать.

*git log -- graf* позволяет отобразить коммиты в виде дерева.
## Удаление веток
Для удаления ветки используется команда *git branch -d*. Для этого необходимо в папке с репозиторием в терминале написать *git branch -d <название ветки>*. Удаляемая ветка **ОБЯЗАТЕЛЬНО** должна быть **СЛИТА**

## Получение удалённого репозитория
Для того, чтобы скачать удалённый репозиторий необходимо использовать команду *git clone*. В терминале, в котором открыта любая пустая папка, необходимо написать *git clone <ссылка на репозиторий>*. Репозиторий скачатеся в папку, название которой будет совпадать с названием репозитория.

## Скачивание изменений с удалённого репозитория
Для того, чтобы скачать изменения с удалённого репозитория, необходимо использовать команду *git pull*. В терминале с  папкой с репозиторием, связанным с удалённым репозиторием, пишем *git pull origin <название ветки>* для того, чтобы принять изменения из указанной ветки удалённго репозитория в текущую ветку.

## Отправка изменений Github
Для отправки изменений в удалённый репозиторий необходимо использовать команду *git push*. Для этого в терминале с папкой с репозиторием, связанным с удалённым репозиторием, пишем команду *git push origin <название ветки>*, <название ветки> - это ветка в удалённом репозитори, куда необходимо отправить совершённые изменения
