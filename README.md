# Docker
Команды для Docker

## Комнада для создания образа из **Dockerfile**:
```bash
### Директория из которой создается образ, обязательно должна содержать докер файл
docker build --no-cache --rm -t <name> <dir-from>
```

## Команда для запуска контейнера из образа:
```bash
## --net bots: этот параметр отвечает в каком через бридж запускать контейнер
docker run -d --net bots --rm --name <container name> <image name>
```

## Создать свой сетевой бридж
```bash
docker network create --gateway 192.168.90.1 --subnet 192.168.90.0/24 bots
```

## Пример **Dockerfile** для Телеграм бота на Python:
```Docker
FROM python:3.11

RUN mkdir -p /opt/bots/AdminBot/
WORKDIR /opt/bots/AdminBot/

COPY . /opt/bots/AdminBot/
RUN pip install --no-cache-dir -r requirements.txt

CMD ["python", "run.py"]
```