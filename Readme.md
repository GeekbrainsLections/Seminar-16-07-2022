# Инструкция по работе с git и удалёнными репозиториями

## Что такое git?
*Git* одна из реализаций распредённых систем контроля версий. *Git* на данный момент является самой полулярной реализацией. Самой популярной реализацией *Git* является [GitHub](https://github.com) 

## Подготовка репозитория
Для того, чтобы создать репозиторий используется команда *git init*. Для этого необходимо написать в терминале в папке будущего репозитория *git init* 

## Состояние репозитория
Для того, чтобы посмотреть состояние репозитория, используется команда *git status* Для этого в терминале с папкой-репозиторием необходмо написать *git status*, и возможно увидеть несколько состояний:
1. Nothing to commit - репозиторий не содержит изменений
2. Unversioned file - папка содержит файл, к которому не добавлена версионность

## Просмотр сделанных изменений
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

## Ветки в git
Ветки в *git* нужны, чтобы работать с "чистовиком" и "черновиками". Для того, чтобы создать новую ветку используется команда *git branch*. В терминале в папке с репозиторием, напишите *git branch <название ветки>*.

## Слияние веток и разрешение конфликтов
Для слияния двух веток используется команда *git merge*. Для её использования необходимо перейти в ту веку, куда Вы хотите сделать слияние, после чего в терминале в папке с репозиторием написать *git merge <название сливаемой ветки>*. Чаще всего слияние проиходит автоматически, но возможны **КОНФЛИКТЫ**. В таком случае, необходимо вручную получить желаемую версию файла и сделать коммит.

## Удаление веток
Для удаления ветки используется команда *git branch -d*. Для этого необходимо в папке с репозиторием в терминале написать *git branch -d <название ветки>*. Удаляемая ветка **ОБЯЗАТЕЛЬНО** должна быть **СЛИТА**

## Получение удалённого репозитория
Для того, чтобы скачать удалённый репозиторий необходимо использовать команду *git clone*. В терминале, в котором открыта любая пустая папка, необходимо написать *git clone <ссылка на репозиторий>*. Репозиторий скачатеся в папку, название которой будет совпадать с названием репозитория.

## Скачивание изменений с удалённого репозитория
Для того, чтобы скачать изменения с удалённого репозитория, необходимо использовать команду *git pull*. В терминале с  папкой с репозиторием, связанным с удалённым репозиторием, пишем *git pull origin <название ветки>* для того, чтобы принять изменения из указанной ветки удалённго репозитория в текущую ветку.

## Отправка изменений Github
Для отправки изменений в удалённый репозиторий необходимо использовать команду *git push*. Для этого в терминале с папкой с репозиторием, связанным с удалённым репозиторием, пишем команду *git push origin <название ветки>*, <название ветки> - это ветка в удалённом репозитори, куда необходимо отправить совершённые изменения

## Создание копии удаленного репозитория

Для того, чтобы в своем локальной папке сделать копию удаленного репозитория, необходимо в GitHub сопировать ссылку на удаленный репозиторий и в терминале с локальной папкой написать команду *git clone <ссылка>*. Таким образом, в локальной папке появится папка с репозиторием.

Для того, чтобы сделать изменения в репозитории, необходимо вначле перейти из локальной папки в папку, где находится репозиторий. Для этого в терминале вводится команда *cd <имя папки с репозиторием>*

## Отправка локального репозитория на GitHub

Для этого вначале необходимо создать новый репозиторий на GitРHub, а затем импортировать в него локальный репозиторий. Таким образом, в терминале с локальным репозиторием нужно написать команду *git remote add origin <ссылка на репозиторий в GitHub>.
Далее следует написать команду *git branch -M main*.
И после этого команду *git push -u origin main*, после чего для отправки локального репозитория на GitHub потребуется авторизация, успешно пройдя которую состоится отправка.

## Отправка и прием изменений при работе с удаленным репозиторием

Если удаленный и локальный репозитории уже связаны, то для отправки изменений с локального репозитория на удаленный в терминале с папкой с локальным репозиторием вводится команда *git push*.

И обратно, для получения изменений из удаленного репозитория необходимо в терминале ввести команду *git pull*.

## Создание в GitHub копии чужого репозитория в своем аккаунте

Для этого необходимо перейти в чужой репозиторий и в правом верхнем углу монитора нажать кнопку *Fork*. После этого можно переместить этот репозиторий в локальную папку так как указано выше в пункте "Создание копии удаленного репозитория".

Далее, после работы с этим репозиторием можно предложить свои наработки автору, у которог этот репозиторий был "форкнут". Для этого в GitHub в левом верхнем углу следует нажать кнопку *Pull requests*. После этого правки будут направлены автору и он уже будет решать, принять их или нет.