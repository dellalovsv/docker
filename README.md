# Docker
Команды для Docker

## Комнада для создания образа из **Dockerfile**:
```bash
### Директория из которой создается образ, обязательно должна содержать докер файл
docker build --no-cache --rm -t <name> <dir-from>
```

## Команда для запуска контейнера из образа:
```bash
docker run -d --net bots --rm --name <container name> <image name>
```