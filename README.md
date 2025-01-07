# Руководство по запуску сервисов: TODO и ShortURL

## 1. Запуск сервисов локально

### Шаги:

1. Перейдите в папку с проектом:
   ```bash
   cd /path/to/<service_name>
   ```

2. Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```

3. Запустите приложение:
   ```bash
   uvicorn main:app --reload
   ```

4. Приложение будет доступно по адресу:
   [http://localhost:8000](http://localhost:8000)

5. Для тестирования API:
   [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 2. Запуск сервисов через Docker

### Шаги:

#### 2.1 Загрузка и запуск образа из Docker Hub

1. Загрузите образ из Docker Hub:
   ```bash
   docker pull aaauuuu/<service_name>:latest
   ```

2. Запустите контейнер:
   ```bash
   docker run -d -p 8000:80 -v todo_data:/app/data aaauuuu/<service_name>:latest
   ```

3. Приложение будет доступно по адресу:
   [http://localhost:8000](http://localhost:8000)

#### 2.2 Создание контейнера локально

1. Перейдите в папку с проектом:
   ```bash
   cd /path/to/<service_name>
   ```

2. Соберите Docker-образ:
   ```bash
   docker build -t <service_name>:latest .
   ```

3. Запустите контейнер:
   ```bash
   docker run -d -p 8000:80 -v todo_data:/app/data <service_name>:latest
   ```

4. Приложение будет доступно по адресу:
   [http://localhost:8000](http://localhost:8000)

---

## 3. Остановка запущенных контейнеров

1. Узнайте ID запущенных контейнеров:
   ```bash
   docker ps
   ```

2. Остановите нужный контейнер:
   ```bash
   docker stop <CONTAINER_ID>
   ```

