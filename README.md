# Quality Control - Система управления заявками

Мобильное приложение для контроля качества оборудования на производстве с интеграцией Telegram-бота для диспетчеров.

## 📋 Описание

**Quality Control** — это кроссплатформенная система для автоматизации процесса подачи и обработки заявок на ремонт оборудования. Система состоит из трех компонентов:

- **Мобильное приложение (Flutter)** — для рабочих и мастеров
- **Backend API (Flask + SQLAlchemy)** — серверная часть
- **Telegram-бот** — для оперативного уведомления диспетчеров

## 🎯 Основные возможности

### Для Рабочих

- Создание заявок на ремонт с описанием и фото
- Просмотр статуса своих заявок
- История обращений

### Для Мастеров

- Просмотр назначенных заявок
- Изменение статуса работ (Принять в работу → Завершить)
- Уведомления о новых назначениях

### Для Диспетчеров

- Получение уведомлений о новых заявках в Telegram
- Назначение мастеров на заявки
- Изменение статусов через Telegram-бот
- Просмотр всех заявок в системе

## 🛠 Технологический стек

### Frontend (Mobile)

- **Flutter** 3.x
- **Dart**
- **Dio** (HTTP-клиент)
- **Flutter Secure Storage** (хранение токенов)

### Backend

- **Python** 3.13
- **Flask** (веб-фреймворк)
- **SQLAlchemy** (ORM)
- **PostgreSQL** (база данных)
- **python-telegram-bot** (интеграция с Telegram)

## 📁 Структура проекта

```
olimp/
├── backend/                  # Серверная часть
│   ├── main.py              # Основной файл Flask-приложения
│   ├── models.py            # Модели БД
│   ├── requirements.txt     # Зависимости Python
│   ├── Procfile            # Конфигурация для деплоя
│   └── uploads/            # Загруженные фото
├── lib/                     # Flutter-приложение
│   ├── core/
│   │   └── services/
│   │       └── api_service.dart  # HTTP-клиент
│   └── features/
│       ├── report/          # Экран создания заявки
│       └── master/          # Экран мастера (в разработке)
```

## 🚀 Быстрый старт

### Backend (локально)

1. Перейди в папку backend:

```bash
cd backend
```

2. Создай виртуальное окружение:

```bash
python3 -m venv venv
source venv/bin/activate  # Linux/Mac
# или
venv\Scripts\activate     # Windows
```

3. Установи зависимости:

```bash
pip install -r requirements.txt
```

4. Запусти сервер:

```bash
python main.py
```

Сервер запустится на `http://localhost:8000`

### Mobile App

1. Убедись, что Flutter установлен:

```bash
flutter doctor
```

2. Установи зависимости:

```bash
flutter pub get
```

3. Измени IP в `lib/core/services/api_service.dart`:

```dart
static const String baseUrl = 'http://YOUR_IP:8000';
```

4. Запусти приложение:

```bash
flutter run
```

## 🔧 Конфигурация Telegram-бота

1. Создай бота через [@BotFather](https://t.me/BotFather)
2. Получи токен и chat_id
3. Обнови переменные в `backend/main.py`:

```python
TELEGRAM_BOT_TOKEN = 'your_token'
TELEGRAM_CHAT_ID = 'your_chat_id'
```

## 🔮 Планы развития

- [ ] Динамическое расписание мастеров
- [ ] Расчет ETA (времени прибытия)
- [ ] Offline-режим в приложении
- [ ] Система уведомлений (FCM)

## 📄 Лицензия

Учебный проект. ГАПОУ "Лениногорский нефтяной техникум"

## 👨‍💻 Автор

ltzyarbin
