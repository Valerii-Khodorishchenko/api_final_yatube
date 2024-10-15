# api_final
api final
## Описание
Это проект API для Yatube, который позволяет взаимодействовать с публикациями пользователей.

## Установка
Для установки и запустить проекта локально, следуйте этим шагам:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Valerii-Khodorishchenko/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 yatube_api/manage.py migrate
```

Запустить проект:

```
python3 yatube_api/manage.py runserver
```

<!-- ## Примеры запросов
Получение списка публикаций:

```
GET /api/v1/posts/?limit=10&offset=0
Ответ:

{
  "count": 123,
  "next": "http://api.example.org/posts/?offset=10&limit=10",
  "previous": null,
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
``` -->
