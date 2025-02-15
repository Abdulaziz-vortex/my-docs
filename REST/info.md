# REST (Representational State Transfer)

## 📌 Определение
**REST** — это архитектурный стиль взаимодействия между клиентом и сервером через HTTP, основанный на ресурсо-ориентированном подходе. В RESTful-системах используются стандартные HTTP-методы (GET, POST, PUT, DELETE) для выполнения операций над ресурсами.

## 📌 Основные характеристики
- Использует HTTP в качестве транспортного протокола
- Основан на архитектурных принципах REST
- Данные передаются в форматах JSON, XML или других
- Stateless (без сохранения состояния между запросами)
- Кэшируемость запросов

## 📌 Преимущества
✅ Простота и удобство
✅ Высокая совместимость с браузерами
✅ Использует стандартные HTTP-методы
✅ Гибкость форматов передачи данных (JSON, XML)
✅ Хорошо поддерживается в различных языках программирования

## 📌 Недостатки
❌ Может быть медленнее gRPC из-за текстового формата (JSON/XML)
❌ Отсутствие строгой типизации данных
❌ Может потребоваться дополнительная документация (Swagger, OpenAPI)

## 📌 Примеры HTTP-запросов
### 🔹 Получение данных (GET)
```http
GET /users/123 HTTP/1.1
Host: example.com
Accept: application/json
```
**Ответ:**
```json
{
  "id": 123,
  "name": "Иван Иванов"
}
```

### 🔹 Создание ресурса (POST)
```http
POST /users HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "Иван Иванов"
}
```
**Ответ:**
```json
{
  "id": 124,
  "name": "Иван Иванов"
}
```

### 🔹 Обновление ресурса (PUT)
```http
PUT /users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "Иван Иванов"
}
```
**Ответ:** `204 No Content`

### 🔹 Удаление ресурса (DELETE)
```http
DELETE /users/123 HTTP/1.1
Host: example.com
```
**Ответ:** `204 No Content`

## 📌 Naming Conventions (Соглашения по именованию)
### 🔹 Общие принципы
- Используйте **множественное число** для имен ресурсов (`/users`, `/orders`)
- Используйте **подресурсы** для вложенных объектов (`/users/123/orders`)
- Избегайте глаголов в URL, используйте HTTP-методы (`GET /users`, а не `/getUsers`)
- Используйте **kebab-case** или **snake_case**, но не CamelCase (`/user-profile` или `/user_profile`, но не `/UserProfile`)

### 🔹 Примеры корректных URL
```http
GET /products            # Получить список товаров
GET /products/42         # Получить информацию о конкретном товаре
POST /products           # Создать новый товар
PUT /products/42         # Обновить товар с ID 42
DELETE /products/42      # Удалить товар с ID 42
GET /users/42/orders     # Получить все заказы пользователя 42
```

## 📌 Когда использовать REST?
- В веб-приложениях и API для браузеров
- Когда требуется простота и масштабируемость
- В микросервисной архитектуре, где нет строгих требований к скорости
- Когда необходима интеграция с внешними сервисами

---
📚 Теперь у тебя есть файлы для SOAP, gRPC и REST! 🚀
