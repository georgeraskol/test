# QA Internship – API tests (Avito ads microservice)

Base URL: https://qa-internship.avito.com

Проект содержит автотесты для API микросервиса объявлений:
- POST /api/1/item — создать объявление
- GET /api/1/item/{id} — получить объявление по id
- GET /api/1/{sellerID}/item — получить объявления продавца
- GET /api/1/statistic/{id} — получить статистику объявления
# 1) Требования

- Python 3.9+ (рекомендуется 3.10/3.11)
- pip
- Доступ в интернет к `https://qa-internship.avito.com`

Проверить версию Python:
```bash
python --version
2) Установка
2.1 Клонировать/скачать проект
Если это репозиторий — клонируйте его, либо просто создайте папку проекта и поместите туда файлы.

Рекомендуемая структура:

Копировать код
project/
├── tests/
│   ├── test_create_item.py
│   ├── test_get_item.py
│   ├── test_get_items_by_seller.py
│   └── test_statistics.py
├── utils/
│   └── helpers.py
├── requirements.txt
├── README.md
├── TESTCASES.md
└── BUGS.md
2.2 Создать и активировать виртуальное окружение (рекомендуется)
Windows (PowerShell):

bash
Копировать код
python -m venv venv
venv\Scripts\activate
Windows (cmd):

bash
Копировать код
python -m venv venv
venv\Scripts\activate.bat
macOS / Linux:

bash
Копировать код
python3 -m venv venv
source venv/bin/activate
2.3 Установить зависимости
Создайте файл requirements.txt со следующим содержимым:

ini
Копировать код
pytest==8.3.3
requests==2.32.3
Установка:

bash
Копировать код
pip install -r requirements.txt
Проверка:

bash
Копировать код
pytest --version
3) Запуск тестов
Запуск всех тестов:

bash
Копировать код
pytest -v
Запуск конкретного файла:

bash
Копировать код
pytest -v tests/test_create_item.py
Запуск конкретного теста:

bash
Копировать код
pytest -v -k test_get_statistics
4) Что проверяют тесты
Тесты выполняют следующие проверки:

Успешное создание объявления возвращает 200 и содержит поля id, sellerId, createdAt

Получение объявления по id возвращает 200 для существующего объявления

Получение списка объявлений по sellerID возвращает массив и содержит созданные объявления

Получение статистики по item id возвращает 200 и поля likes, viewCount, contacts

5) Важные замечания
sellerID должен быть уникальным в диапазоне 111111–999999, поэтому в тестах он генерируется случайно.

В некоторых эндпоинтах ответы возвращаются массивом — это зафиксировано в BUGS.md как потенциальные дефекты/особенности API.

Тесты не требуют авторизации.
