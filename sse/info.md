# SSE (Server-Sent Events)

## 📌 Определение
**SSE (Server-Sent Events)** — это технология, позволяющая серверу отправлять события клиенту через однонаправленное соединение по **HTTP**.

## 📌 Основные характеристики
- Соединение открывается клиентом, а сервер отправляет обновления
- Использует **EventSource API** на клиенте
- Основано на **HTTP** (не требует WebSockets)
- Работает только в одном направлении (сервер → клиент)

## 📌 Пример кода
### Сервер (Node.js):
```javascript
const express = require('express');
const app = express();

app.get('/events', (req, res) => {
  res.setHeader('Content-Type', 'text/event-stream');
  res.setHeader('Cache-Control', 'no-cache');
  res.setHeader('Connection', 'keep-alive');

  setInterval(() => {
    res.write(`data: ${JSON.stringify({ time: new Date().toISOString() })}\n\n`);
  }, 2000);
});

app.listen(3000, () => console.log('SSE сервер запущен на порту 3000'));
```

### Клиент (JavaScript):
```javascript
const eventSource = new EventSource('/events');

eventSource.onmessage = (event) => {
  console.log("Новое событие:", event.data);
};
```

## 📌 Преимущества
✅ Простая реализация по сравнению с WebSockets  
✅ Использует стандартный HTTP, не требует дополнительного протокола  
✅ Хорошо работает с **REST API** и кешированием

## 📌 Недостатки
❌ Поддержка только однонаправленного потока данных  
❌ Может не работать за прокси-серверами без дополнительных настроек

## 📌 Когда использовать SSE?
- Для обновлений новостных лент
- В системах уведомлений
- В аналитике и мониторинге в реальном времени
