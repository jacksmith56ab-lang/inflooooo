# Telegram AI Userbot — Infrlo / SESSION_STRING

Готовый проект для запуска Telegram userbot на Infrlo.

## Что уже есть

- Telethon + `SESSION_STRING` — без интерактивного ввода телефона/кода на сервере.
- OpenRouter для обычных AI-ответов.
- Подстройка стиля под собеседника, включая умеренный мат в ответах, если он уместен.
- `/image <описание>` — генерация изображения через OpenRouter Images API.
- Автоматическое скачивание TikTok по ссылке и отправка видео в чат.
- `/clear` — очистка истории диалога.
- `/ignore` и `/ignored` — игнорирование текущего приватного чата.
- `/dickgroup` — выбрать текущую группу для ежедневного `/dick`.
- `/dickstatus` — показать выбранную группу.
- `/dick` отправляется каждый день в 00:00 по времени Казахстана.
- `+фарма` — включить отправку `фарма` в текущей группе.
- `-фарма` — выключить фарму.
- `+фарма статус` — статус фармы.
- `фарма` отправляется в 00:00, 04:00, 08:00, 12:00, 16:00 и 20:00 по времени Казахстана.
- Настройки групп и игнор сохраняются в JSON-файлах и переживают перезапуск.

## Переменные Infrlo

Обязательные:

- `API_ID`
- `API_HASH`
- `SESSION_STRING`
- `OPENROUTER_API_KEY`

Необязательные:

- `OPENROUTER_MODEL` — по умолчанию `openrouter/free`
- `IMAGE_MODEL` — по умолчанию `black-forest-labs/flux.2-klein-4b`

## Настройки Infrlo

Build command:

`pip install -r requirements.txt`

Run command:

`python main.py`

Python version:

`3.12` (в проекте уже есть `.python-version`)

## Важно про SESSION_STRING

Не отправляй `SESSION_STRING` в чат и не публикуй его в GitHub.
Он даёт доступ к Telegram-сессии.

Если у тебя уже есть готовый `SESSION_STRING`, просто вставь его в Environment Variables на Infrlo.

Если session string ещё нет, сгенерируй Telethon StringSession локально и только получившуюся строку добавь в Infrlo.

## Первый запуск

1. Загрузи этот проект в GitHub.
2. Подключи репозиторий к Infrlo.
3. Укажи Build command и Run command выше.
4. Добавь 4 обязательные переменные.
5. Запусти deployment.
6. В Telegram в нужной группе отправь:
   - `/dickgroup`
   - `+фарма`
7. После этого scheduler будет использовать эти группы.

Команды управления рассчитаны на владельца userbot и работают даже как исходящие сообщения самого аккаунта.

## Файлы состояния

- `ignored.json`
- `dick_group.json`
- `farma_group.json`

Они создаются/обновляются автоматически.
