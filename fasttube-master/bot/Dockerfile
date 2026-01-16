FROM python:3.11.9

# Корневая рабочая директория
WORKDIR /app

# Копируем весь проект
COPY . /app

# Python-настройки
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# КЛЮЧЕВОЕ: говорим Python, где искать src
ENV PYTHONPATH=/app/fasttube-master/bot

# Обновляем pip и ставим poetry
RUN pip install --upgrade pip setuptools wheel
RUN pip install --no-cache-dir poetry

# Переходим в папку бота
WORKDIR /app/fasttube-master/bot

# Устанавливаем зависимости через poetry
RUN poetry install --no-interaction --no-ansi

# Запускаем ПРАВИЛЬНУЮ точку входа
CMD ["python", "-m", "src.run"]
