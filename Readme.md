# Инструкция по работе с git и удалёнными репозиториями

## Что такое git?

_Git_ одна из реализаций распредённых систем контроля версий, что позволяет иметь версионность как в локальном репозитории, так и в удаленном репозитории (общим для всех). Самой популярной реализацией _Git_ является [GitHub](https://github.com)

## Инициализация репозитория

Для создания репозитория используется комада _git init_. В терминале в папке с будущим репозиторием досточно написать

    git init

и эта папка станет репозиторием.

## Состояние репозитория

Для того, чтобы посмотреть состояние репозитория, используется команда _git status_ Для этого в терминале с папкой-репозиторием необходмо написать _git status_, и возможно увидеть несколько состояний:

1. Nothing to commit - репозиторий не содержит изменений
2. Unversioned file - папка содержит файл, к которому не добавлена версионность
3. Modifided - означает, что файл изменен, но изменения не были "сохранены"

# Просмотр сделанных изменений

Для того, что бы проверить различия между данными внесенными в последний коммит используется команда _git diff_ По умолчанию команда git diff выводит все неподтвержденные изменения, внесенные после последнего коммита, другими словами - сравнение файлов в двух коммитах. С помощью терминала в папке с репозиторием вызываем команду

    git diff

### Добавление файла к коммиту

Для добавления файла к коммиту используется команда _git add_. Пишется она следующим образом _git add <имя файла>_ в терминале в папке с созданным репозиторием.

### Создание нового коммита

Для сохранения коммита используется команда _git commit_. Для эого в терминале с папкой репозитория необходимо написать команду

    git commit -m "< сообщение к коммиту>"

Сообщение к коммиту писать **_ОБЯЗАТЕЛЬНО_**

## Журнал изменений

Для просмотра истории коммитов, то есть истории наших изменений используется команда _git log_. Для этого необходимо в терминале с папкой-репозиторием написать

    git log

Команда _git log --graph_ позволяет посмотреть список изменений. Такой вариант просмотра изменений визуально лучше показывает ветки репозитория. Что бы вызвать данную команду, достаточно вызвать её в терминале с папкой - репозиторием:

    git log --graph

## Перемещение между "сохранениями"

Для того, чтобы перемещаться между коммитами необходимо использовать команду _git checkout_. Для этого в терминале с папкой репозитория необходимо написать

    git checkout <номер коммита>

Номер коммита берется из истории изменений. После такого "перемещения" мы попадаем в состояние _Detached dead_. Для возвращения в обычное сосстояние используется команда

    git checkout main

## Ветки в git

Для того чтобы увидеть количество веток и их названия в репозитории, следует вызвать комманду _git branch_. Даная команда показывает информацию о существующих ветках git, а так же указывает на ветку в которой находится пользователь в текущий момент. В терминале команда вызывается

    git branch

Для того что бы создать новую ветку в репозитории следует вызвать комманду _git branch_. Данная команда позволяет создавать множетсво веток, которые можно заполнить отдельной информацией с возможным слиянием в главную ветку _main / master_. В терминале с папкой-репозиторием вызываем команду

    git branch "<название ветки>"

## Слияние веток и разрешение конфликтов

Для того, чтобы сделать слияние веток в git, необходимо вызвать команду _git merge_. Данная команда позволяет совместить данные из двух веток в одну. Для правильного слияния веток, для начала нужно убедиться что в текущий момент мы "стоим" на нужной нам ветке, т.к. слияние будет происходить именно в ту ветку, в которой вы "находитесь". В терминале с папкой репозитория следует ввести команду

    git merge <название ветки>

Следует указывать название ветки, данные которой мы хотим переместить.

Обычно конфликты возникают, когда два человека изменяют **одни и те же строки в файле** или один разработчик удаляет файл, который в это время изменяет другой разработчик. В таких случаях Git не может автоматически определить, какое изменение является правильным. Конфликты затрагивают только того разработчика, который выполняет слияние, остальная часть команды о конфликте не знает. Git помечает файл как конфликтующий и останавливает процесс слияния.

Разрешить конфликт можно несколькими способами. При конфликте слияния Git предлагает 4 способа решения:

1. Accept Current Changes Данный вариант предлагает оставить данные в текущей ветке, в таком случае "приходящие" данные не будут отображаться.
2. Accept Incoming Changes Данный вариант предлагает оставить "приходящие" данные из ветки, которую мы указали для слияния.
3. Accept Both changes Данный вариант предлагает оставить оба варианта данных из текущей ветки и из ветки, которую мы указали для слияния.
4. Compare Changes Данный вариант предлагает открыть конфликт в отдельном окне для их сравнения.

Так же можно решить конфликт **"вручную"**. Для этого можно удалить определяющие знаки (_=_ _<_ _>_), которые указывают на конфликт, после чего самостоятельно решить - что можно удалить, а что нужно оставить.

## Удаление веток

Для того что бы удалить ветку, которая больше нам не требуется следует прибегнуть к команде

    git branch -d

Данная команда удалит ветку и данные, которые в ней находится при условии, что она была использована и внесённые в неё данные были слиты с другой веткой. Команда _git branch -D_ удалит вашу ветку в любом случае, поэтому рекомендуется использовать _git branch -d_, что бы избежать неприятных ситуаций в будущем.

## Получение удалённого репозитория

Для того, чтобы скачать удалённый репозиторий необходимо использовать команду _git clone_. В терминале, в котором открыта любая пустая папка, необходимо написать

     git clone <ссылка на репозиторий>

Репозиторий скачатеся в папку, название которой будет совпадать с названием репозитория.

## Скачивание изменений с удалённого репозитория

Для того, чтобы скачать изменения с удалённого репозитория, необходимо использовать команду _git pull_. В терминале с папкой с репозиторием, связанным с удалённым репозиторием, пишем

    git pull origin <название ветки>

для того, чтобы принять изменения из указанной ветки удалённго репозитория в текущую ветку.

## Отправка изменений Github

Для отправки изменений в удалённый репозиторий необходимо использовать команду _git push_. Для этого в терминале с папкой с репозиторием, связанным с удалённым репозиторием, пишем команду

    git push origin <название ветки>_, <название ветки>

это ветка в удалённом репозитори, куда необходимо отправить совершённые изменения.
