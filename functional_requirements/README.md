# Functional Requirements

Эта папка содержит функциональные требования и технические спецификации для проекта AIHR Telegram Bot.

## Содержимое папки

### 🏗️ Архитектура и модели данных:

| Файл | Описание |
|------|-----------|
| `architecture.drawio.png` | **Архитектурная диаграмма** - Общая структура системы |
| `AIHR_ERD.drawio.png` | **ERD диаграмма** - Модель данных базы данных |
| `AIHR_data_model.pdf` | **Модель данных** - Детальное описание сущностей и атрибутов |

### 🔄 Процессы и взаимодействия:

| Файл | Описание |
|------|-----------|
| `AIHR_sequence_diagram.png` | **Sequence диаграмма** - Взаимодействие компонентов системы |

### 🌐 API спецификации:

| Файл | Описание |
|------|-----------|
| `AIHR_swagger.yaml` | **OpenAPI спецификация** - Полное описание REST API |
| `AIHR_REST_upd.pdf` | **REST API документация** - Табличное описание эндпоинтов |

## Детальное описание

### Архитектура системы
- **Компоненты**: Telegram Bot, Backend API, Database, AI Service (DeepSeek)
- **Взаимодействие**: Асинхронная обработка запросов через REST API

### Модель данных
**Основные сущности:**
- **Вакансии** (vacancies): vacancy_id, hr_user_id, title, description, created_at
- **Резюме** (resumes): resume_id, uploaded_by_id, file_path, file_hash, original_name, file_size, uploaded_at
- **Соответствия** (matches): match_id, vacancy_id, resume_id, score, details, analyzed_at

### API Endpoints
**Основные группы эндпоинтов:**
- `/resumes` - Управление резюме (GET, POST, DELETE)
- `/vacancies` - Управление вакансиями (GET, POST)
- `/analyze` - Запуск анализа соответствия (POST)

### Sequence диаграмма
Визуализирует процесс:
1. Загрузка вакансии
2. Загрузка резюме
3. Запуск анализа
4. Обработка AI
5. Возврат результатов
