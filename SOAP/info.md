# SOAP (Simple Object Access Protocol)

## 📌 Определение
SOAP (Simple Object Access Protocol) — это протокол обмена сообщениями, который используется для взаимодействия между веб-службами в распределенных системах. Он основан на XML и обычно передается через HTTP, SMTP или другие транспортные протоколы.

## 📌 Основные характеристики
- Основан на XML для форматирования сообщений
- Использует WSDL (Web Services Description Language) для описания служб
- Поддерживает сложные механизмы безопасности (WS-Security)
- Работает с различными транспортными протоколами (HTTP, SMTP, TCP)
- Поддерживает как синхронное, так и асинхронное взаимодействие

## 📌 Преимущества
✅ Независимость от платформы и языка программирования
✅ Высокая безопасность благодаря WS-Security
✅ Поддержка сложных транзакций и ACID
✅ Возможность работы через брандмауэры благодаря использованию HTTP

## 📌 Недостатки
❌ Высокий оверхед из-за XML
❌ Медленнее по сравнению с REST и gRPC
❌ Требует строгого стандартизированного формата сообщений

## 📌 Пример SOAP-запроса
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:web="http://example.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <web:GetUser>
         <web:UserID>123</web:UserID>
      </web:GetUser>
   </soapenv:Body>
</soapenv:Envelope>
```

## 📌 Пример SOAP-ответа
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/">
   <soapenv:Body>
      <GetUserResponse xmlns="http://example.com/">
         <User>
            <ID>123</ID>
            <Name>Иван Иванов</Name>
         </User>
      </GetUserResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## 📌 Когда использовать SOAP?
- Когда важна безопасность и надежность передачи данных
- Когда требуется сложная транзакционная логика
- В корпоративных системах и банковском секторе

---
📚 Следующий файл будет о gRPC!
