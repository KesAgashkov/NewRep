## Инструкция по GIT 2.0
### 1. инициализация репозитория
    git init
### 2. проверка состояния репозитория
    git status (просмотр файлов подготовленных для коммита Staging Area)
### 3. добавление в индекс
    git add 
### 4. фиксация изменений
    git commit -m "название"
    git commit -am "название" команда объединение команд add и commit
### 5. показать историю коммитов
    git log - подробное описание коммитов до ветки мастер
    git log --oneline -краткий формат представления коммитов
    git log --all -полное представление всех коммитов, включая те коммиты, с которых мы откатили файл.
### 6. переход на другой коммит или ветку
    git checkout 7 значный номер коммита. Удобно добавлять к команду с помощью нажатия правой кнопки мыши на индекс коммита
### 7. удаление ненужного коммита
    git reset --hard 7 знаков индекса
### 8. просмотр невнесённых изменений и сравнение коммитов между собой
    git diff показывает изменения внесенные в файл, но не зафиксированные
    git diff хэш показывает какие изменения были внесены c опред коммита до последнего
    git diff хэш хэш показывет изменения между двумя коммитами (может показывать приращение инфо или вычитание в зависимости хэш какого коммита поставить на первое место)
### 9. сделать git более политкоректным (переименовать ветку)
    git branch -m main (замена имени текущей ветки)
### 10. посмотреть содержимое проекта в терминале (рабочая директория)
    ls
### 11. добавить новый файл через терминал
    echo >название файла и расширение
### 12. прочитать содержимое файла
    cat <название файла с расширением>
### 13. создать папку в репозитории 
    mkdir <название папки> 
### 14. посмотреть что за сущность зашифрована в хэше и посмотреть содержимое коммита
    git cat-file -t хэш - что это (tree, blob или commit)
    git cat-file -p хэш (содержимое сущности в виде гномика) более полное описание коммита
    или git show хэш сущности
### 15. удаление файла или папка 
    rm <файл и расширение>
### 16. переименование последнего коммита
    git commit --amend -m "название коммита"
### 17. отменить последний коммит с сохранением изменений и без сохранения
    git reset --soft HEAD~ (с сохранением изменений) или хэш коммита с которого будут удалены все последующие коммиты
    git reset --hard HEAD~ (без сохранения изменений)
### 18. Посмотреть доступные ветки; создать новую ветку; удалить ветку
    git branch - просмотр
    git branch имя -создание ветки
    git branch -d <имя ветки> - удалить ветку. Текущую ветку удалить нельзя
<<<<<<< HEAD

### 19. Слияние веток. Обязательно находиться в той ветке, в которую хотим добавить приращение информации. После слияния ненужную ветку можно удалить
    git merge <имя ветки>
    git merge -m "<>" название коммита

### 20. Создание ветки и переход на неё
    git checkout -b <имя ветки>

=======
### 19. Слияние веток. Обязательно находиться в той ветке, в которую хотим добавить приращение информации. После слияния ненужную ветку можно удалить
    git merge <имя ветки>
    git merge -m "<>" название коммита
### 20. Создание ветки и переход на неё
    git checkout -b <имя ветки>

### 21. Клонирование удаленного репозитория в локальный репозиторий. 
Заходим в любой публичный репозиторий гитхаб, открываем его, кликаем мышью на кнопку код, копируем url для клонирования в локальный репозиторий

    git clone <url>

### 22. Посмотреть все ветки включая ветки удаленных репозиториев

    git branch -a

### 23. Добавить локальный репозиторий в хранилище удалённых репозиториев на GitHub. На гитхабе нужно создать удаленный репозиторий и написать его название. Далее у этого репозитория появится свой url
    git remote add origin <url>

### 24. Посмотреть все ветки включая ветки удаленных репозиториев

    git branch -a

### 25. Переименовать текущую ветку на main для синхронизации
    git branch -m main

### 26. Добавить файлы в удаленный репозиторий (первое использование)
    git push -u origin main

### 27. Просмотреть все доступные удалённые репозитории
    git remote show

### 28. Отключение удаленного репозитория от локального
    git remote remove <название репозитория>

### 29. Получение изменений из удаленного репозитория
    git pull <название удалённого репозитория>Получение изменений из удаленного репозитория

### 30. Внесение изменений в удаленный репозиторий

    git push <имя удалённого репозитория> <имя ветки>

    По умолчанию команда git push добавляет только ветку main. Для добавления других веток указываем название удалённого репозитория и ту ветку, которую хотим добавить. Если есть много веток используем флаг --all

### 31. Получение изменений из удаленного репозитория. Команда не обновляет рабочую копию в соответствии с удаленным репозиторием. Она обновляет только ссылочные объекты (указатели, ветки и теги) и скачивает все необходимые файлы в директорию. Внесение изменений в рабочую копиб проекта осуществляется вручную

    git fetch <имя удал репоз>

### 32. Перевести файл из категории changes to be com в категории untracked 

    git rm --cached <назв файла>

### 33. Отменить последние коммиты. Можно один, а можно и серию. Информация в файлах остаётся
    git reset <[хэш коммита]> 

### 34. Посмотреть информацию обо всех совершенных операциях в репозитории, включая удалённые коммиты.
    git reflog

### 35. Отменить изменения совершенные последним коммитом с созданием нового коммита 

    git revert <[хэш коммита]> 

### 36. Операции с тэгами. 

    добавить тег к текущему коммиту git tag <номер тэга>
    посмотреть тэги git tag
    добавить тэги в удалённый репозиторий git push --tags
    удалить тэг git taf -d <номер тэга>
    удалить тэг из удалённого репозитория git push --delete origin <номер тэга>
    