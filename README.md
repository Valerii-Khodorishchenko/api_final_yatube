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

## Примеры запросов
### Получение доступа к АPI:

Получить JWT-токен

```
POST http://127.0.0.1:8000/api/v1/jwt/create/

{
  "username": "string",
  "password": "string"
}

Ответ:
200
{
  "refresh": "string",
  "access": "string"
}

400
{
  "username": [
    "Обязательное поле."
  ],
  "password": [
    "Обязательное поле."
  ]
}

401
{
  "detail": "No active account found with the given credentials"
}
```

Обновить JWT-токен

```
POST http://127.0.0.1:8000/api/v1/jwt/refresh/

{
  "refresh": "string"
}

Ответ:
200
{
  "access": "string"
}

400
{
  "refresh": [
    "Обязательное поле."
  ]
}

401
{
  "detail": "Token is invalid or expired",
  "code": "token_not_valid"
}
```

Проверить JWT-токен

```
POST http://127.0.0.1:8000/api/v1/jwt/refresh/

{
  "token": "string"
}

Ответ:
200

400
{
  "token": [
    "Обязательное поле."
  ]
}

401
{
  "detail": "Token is invalid or expired",
  "code": "token_not_valid"
}
```

### Публикации:
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
```
