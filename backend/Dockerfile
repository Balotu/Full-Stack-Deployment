FROM python:3.11-slim

RUN pip install poetry

WORKDIR /application

COPY pyproject.toml poetry.lock ./

RUN poetry install --no-root

COPY . .

ENV PYTHONPATH=/application

CMD poetry run bash ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0
