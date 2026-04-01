# ✨ AI Plugin for exteraGram

> Google Gemini & OpenRouter AI — прямо в вашем Telegram-клиенте

[![Version](https://img.shields.io/badge/version-1.3.0-7C4DFF?style=for-the-badge&logo=github)](https://github.com/)
[![Platform](https://img.shields.io/badge/platform-Android-3DDC84?style=for-the-badge&logo=android)](https://plugins.exteragram.app)
[![Python](https://img.shields.io/badge/python-3.11-3776AB?style=for-the-badge&logo=python)](https://chaquo.com/chaquopy/)
[![License](https://img.shields.io/badge/license-MIT-555555?style=for-the-badge)](LICENSE)

---

## 🚀 Возможности

| Команда | Провайдер | Модель |
|:-------:|:---------:|:------:|
| `.g <запрос>` | **Google Gemini** | `gemini-2.5-flash-lite` |
| `.o <запрос>` | **OpenRouter** | Любая (по умолчанию `openai/gpt-5.2`) |
| `.gfix <текст>` | **Google Gemini** | Исправление текста |

- 🎨 **Material Design 3** — уведомления в стиле M3 с тёмной темой
- ⚡ **Асинхронность** — UI не блокируется во время запросов
- 📝 **Markdown** — автоматическая конвертация ответов в форматирование Telegram
- ⏱ **Live-таймер** — баннер показывает время обработки запроса
- 🔧 **Гибкие настройки** — выбор модели, позиция уведомлений, режим отправки

---

## 📦 Установка

1. Скачайте `gemini_ai.plugin` 
2. Отправьте файл в **Избранное** (или любой другой чат)
3. Нажмите на файл в чате и выберите **Установить**
4. Включите плагин в **exteraGram Preferences → Plugins**

---

## ⚙️ Настройка

После установки откройте настройки плагина:

| Параметр | Описание | По умолчанию |
|----------|----------|:------------:|
| **API Ключ** | Ключ от [Google AI Studio](https://aistudio.google.com) | — |
| **API Ключ OpenRouter** | Ключ от [openrouter.ai](https://openrouter.ai) | — |
| **Модель OpenRouter** | Модель для OpenRouter (напр. `anthropic/claude-3.5`) | `openai/gpt-5.2` |
| **Сразу отправлять ответ** | `true` — отправить, `false` — в поле ввода | `true` |
| **Где показывать уведомление** | `top` — сверху, `bottom` — снизу | `top` |

---

## 💡 Примеры использования

```
.g Напиши хайку о программировании
.g Переведи на английский: Привет, мир!
.g Объясни как работает рекурсия

.o Напиши Python-скрипт для парсинга погоды
.o Составь план изучения машинного обучения
.o Что такое квантовые вычисления?

.gfix привет как дела
.gfix исправь этот текст пжлст
```

---

## 🎨 UI

Уведомления выполнены в стиле **Material Design 3**:

- **Surface Container** (`#2D2D2D`) — фон карточки
- **Primary** (`#D0BCFF`) — акцентный цвет иконки
- **On Surface** (`#E6E1E5`) — цвет текста
- **Medium Shape** — скругление 16dp
- **Elevation Level 2** — тень 6dp

---

## 🏗 Архитектура

```
gemini_ai.plugin
├── Мета-данные          (__id__, __name__, __version__, ...)
├── GeminiPlugin         (основной класс, наследует BasePlugin)
│   ├── on_plugin_load()         — регистрация хука сообщений
│   ├── create_settings()        — экран настроек
│   ├── on_send_message_hook()   — перехват команд .g / .o
│   ├── _fetch_gemini()          — запрос к Google Gemini API
│   ├── _fetch_openrouter()      — запрос к OpenRouter API
│   ├── _show_top_banner()       — M3-уведомление с таймером
│   └── _insert_into_input()     — вставка текста в поле ввода
├── gemini_to_tg_markdown()      — конвертация Markdown → Telegram
└── Импорт: requests, re, time   — стандартные библиотеки
```

---

## 📚 Технологии

| Технология | Назначение |
|-----------|-----------|
| [Chaquopy v16](https://chaquo.com/chaquopy/) | Python 3.11 на Android |
| [exteraGram Plugin SDK](https://plugins.exteragram.app) | Фреймворк плагинов |
| Google Gemini API | Генерация ответов |
| OpenRouter API | Мульти-модельный доступ к AI |
| Material Design 3 | Дизайн интерфейса |

---

## 🤝 Контрибьют

1. Форкните репозиторий
2. Создайте ветку (`git checkout -b feature/amazing-feature`)
3. Закоммитьте изменения (`git commit -m 'Add amazing feature'`)
4. Пушните (`git push origin feature/amazing-feature`)
5. Откройте Pull Request

---

## 📄 Лицензия

Этот проект распространяется под лицензией **MIT**. Подробности в файле [LICENSE](LICENSE).

---

## 👤 Автор

**[@Tyta_Zdesyaa777](https://t.me/Tyta_Zdesyaa777)**

---

<p align="center">
  <sub>Сделано с 💜 для сообщества exteraGram</sub>
</p>
