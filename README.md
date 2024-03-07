# Практика по основам Flask

Задания для закрепления навыков по работе с фреймворком Flask.

## Что представляет из себя репозиторий
В репозитории вы найдете простой работающий проект по созданию заметок в браузера. Доступно создание и удаление заметок.
Все заметки сохраняются в базу данных sqlite.


Так выглядит структура репозитория. Рядом с директориями и файлами их короткое описание и предназначение:
```
├── app.py  # python скрипт с основной логикой приложения
├── LICENSE  # лицензия проекта, не играет роли в работоспособности приложения
├── README.md  # документация к проекту, не играет роли в работоспособности приложения
├── requirements.txt  # файл с зависимостями проекта, содержит список модулей и билиотеку необходимых для запуска приложения
├── static  # содержит статические файлы приложения - картинки, стили и т.д.
└── templates  # содержит все html шаблоны для рендиринга в браузере
   └── index.html  # html-шаблон главной страницы приложения
```

## Как запустить проект локально на unix системе:
1. Запускаем терминал (Ctrl+Alt+T)
2. Переходим в директорию `home` или же любую другую на ваш выбор и копируем данный репозиторий к себе локально:
    ```sh
    cd ~
    git clone git@github.com:MaxFallishe/PTFlaskMastering_part1.git
    ```
3. Создаем виртуальное окружением с помощью venv и активируем его с помощью source:
    ```sh
    python3 -m venv my_venv
    source my_venv/bin/activate 
    ``` 
4. Устанавливаем зависимости из файла requirements.txt:
    ```sh
    pip install -r requirements.txt
    ``` 
5. Запускаем локально веб-приложение на flask:
    ```sh
    python app.py
    ```
   Если вы получаете ошибку о том что 5000 порт занят другим приложением `Address already in use
   Port 5000 is in use by another program. Either identify and stop that program, or start the server with a different port.
   `, вы можете использовать команду `kill -9 $(lsof -t -i:5000)` чтобы исправить эту ошибку.

6. Заходим в браузере по адресу http://127.0.0.1:5000 и  проверяем функциональность приложения. Результат работы должен выглядеть примерно так:
   ![img](https://iili.io/JVXLN3u.png)


## Задания:
1. Локально запустить проект и сделать скриншот получившегося результата
2. Зарефакторить код и сделать его "красивым" - привести в соответствие с PEP-8, использовать линтеры на выбор, добавить комментарии.
3. Добавить возможность ставить статус "выполнено" и "не выполнено" для каждой заметки. Статус должен фиксироваться в базе данных.
4. Добавить возможность редактировать заметки после их добавления.
5. Добавить пароль для доступа к заметкам - прежде чем пользователь сможет зайти на страницу с заметками, запросить у него пароль - если пароль не правильный отказать в доступе. Будет очень круто если получить реализовать механизм автоизации.