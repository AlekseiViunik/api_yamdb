# api_yamdb
![Python version](https://img.shields.io/badge/python-3.7-yellow) ![Django version](https://img.shields.io/badge/django-2.2-orange)

This is a group project. Team lead was [Aleksandr Usolcev](https://github.com/AleksandrUsolcev/api-yamdb) 

```sh
YaMDb project collects user's review of the compositions. It doesn't store the compositions. 
Here you can not listen the music or watch the movie.
The are types of compositions like "books", "Movies", "Music". There can be more types.
A genre from the genre's list can be assigned to the compositions.
Only Administrator can add compositions, types and genres.
Users can add a review to the composition and rate it from 1 to 10 (integer number) which forms composition's rating. 
1 composition = 1 review for each user.
Users can add comments to reviews.
Only authorized users can rate, add reviews and comments.


Проект YaMDb собирает отзывы пользователей на произведения. 
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка». Список категорий может быть расширен.
Произведению может быть присвоен жанр из списка предустановленных. 
Добавлять произведения, категории и жанры может только администратор.
Пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от одного до десяти.
Из пользовательских оценок формируется рейтинг. 
На одно произведение пользователь может оставить только один отзыв.
Пользователи могут оставлять комментарии к отзывам.
Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные пользователи.
```
## Technologies/Технологии

- Python 3.7+
- [django](https://github.com/django/django) 2.2.16
- [django-rest-framework](https://github.com/encode/django-rest-framework)
  3.12.4
- [Simple JWT](https://github.com/jazzband/djangorestframework-simplejwt) 5.2.0

## Running project in dev-mode/Запуск проекта в dev-режиме

Clone repository. Install and activate virtual environment/

Клонировать репозиторий. Установить и активировать виртуальное окружение

```
# For Mac or Linux:
$ python3 -m venv venv
$ source venv/bin/activate

# For Windows
$ python3 -m venv venv
$ source venv/Scripts/activate 
``` 

Install dependencies  from requirements.txt
Установить зависимости из файла requirements.txt

```
pip install -r requirements.txt
``` 

Run migrations and run the project
Выполнить миграции и запустить проект

```
python3 manage.py migrate
python3 manage.py runserver
``` 

## Getting personal token/Получение персонального токена

You need to make an account of user or superuser and get a token for interaction with API.
To do this you need to send POST request with name and e-mail on.../api/v1/auth/signup/

Для взаимодействия с API необходимо завести учетную запись пользователя,
или суперпользователя и иметь персональный токен, для чего необходимо
перейти по адресу .../api/v1/auth/signup/ и отправить POST запрос с
именем и адресом электронной почты пользователя

```
{
    "username": "example_name",
    "email": "example_email"
}
``` 
After successfull registration the secret code will be sent on e-mail.
You need to copy it in the "confirmation_code" field on .../api/v1/auth/token/
And you'll get the token.

После успешной регистрации на указаный email придет секретный код, который
необходимо скопировать в поле "confirmation_code" по адресу ...
/api/v1/auth/token/ и получить персональный токен

```
{
    "username": "example_name",
    "confirmation_code": "your_code"
}
``` 

Pass the token in headers
Далее передаем полученный токен в headers

```
KEY: Authorization
VALUE: Bearer <ваш токен>
``` 

## Request examples/Примеры запросов

**Full list of requests you can see by going to .../redoc/ of the running project

Полный список запросов можно посмотреть перейдя на .../redoc/
развернутого проекта**
