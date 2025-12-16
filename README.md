# decisionlater

Роль:
Ты опытный full-stack разработчик. Делай аккуратно, просто и без оверинжиниринга.

Задача:
Создай простой full-stack проект “Decision Later”.

Общая идея

Пользователь создаёт решение, которое хочет принять позже.
Сервис хранит решения и показывает их, когда наступает дата напоминания.


---

Backend (FastAPI)

Стек

Python 3.11

FastAPI

SQLAlchemy

SQLite

Pydantic


Функционал API

Реализуй следующие эндпоинты:

1. POST /decisions

Создать решение

Поля:

title: str

description: str | None

remind_at: datetime




2. GET /decisions

Список всех решений



3. GET /decisions/due

Только решения, у которых:

status == "pending"

remind_at <= now




4. POST /decisions/{id}/resolve

Принять решение

Тело:

resolution_text: str




5. POST /decisions/{id}/postpone

Отложить решение

Тело:

new_remind_at: datetime






---

Модель Decision

id: int
title: str
description: str | None
created_at: datetime
remind_at: datetime
status: pending | resolved | closed
resolution_text: str | None


---

Требования к backend

Чистая структура проекта

Отдельные файлы:

main.py

models.py

schemas.py

database.py

crud.py


Автоматическое создание таблиц

Корректная обработка ошибок

Комментарии в коде, но без лишнего текста



---

Frontend

Требования

Простой фронт без сложных фреймворков

HTML + CSS + vanilla JS

Используй fetch для общения с API


Экраны

1. Список решений

Показывать title, remind_at, status



2. Создание решения

Форма:

title

description

remind_at (datetime-local)




3. Экран “Пора решать”

Загружает /decisions/due

Кнопки:

«Принять решение»

«Отложить»






---

Дополнительно

Backend и frontend в одном репозитории

Frontend можно отдавать через FastAPI (StaticFiles)

Минимальный, аккуратный UI

Код должен быть готов к запуску без доработок



---

Результат:
Сгенерируй весь код проекта целиком и объясни, как его запустить локально.


