# gRPC

## 📌 Определение
**gRPC** — это высокопроизводительный RPC-фреймворк, разработанный Google. Он использует HTTP/2, бинарную сериализацию Protocol Buffers (protobuf) и поддерживает множество языков программирования.

## 📌 Основные характеристики
- Основан на HTTP/2
- Использует Protocol Buffers (protobuf) вместо XML/JSON
- Поддерживает двустороннюю потоковую передачу данных
- Встроенная поддержка аутентификации и авторизации
- Генерация клиентских и серверных SDK на основе `.proto`-файлов

## 📌 Преимущества
✅ Высокая производительность благодаря бинарному формату
✅ Поддержка потоков и асинхронного взаимодействия
✅ Поддержка множества языков программирования
✅ Встроенная поддержка сервисной регистрации и балансировки нагрузки

## 📌 Недостатки
❌ Более сложная настройка по сравнению с REST
❌ Требуется генерация кода на основе `.proto`
❌ Меньшая совместимость с браузерами (нужен gRPC-Web)

## 📌 Пример определения сервиса на gRPC (Protocol Buffers)
```proto
syntax = "proto3";
package example;

service UserService {
  rpc GetUser (UserRequest) returns (UserResponse);
}

message UserRequest {
  int32 user_id = 1;
}

message UserResponse {
  int32 id = 1;
  string name = 2;
}
```

## 📌 Пример серверного кода на Python (gRPC)
```python
import grpc
from concurrent import futures
import user_pb2, user_pb2_grpc

class UserService(user_pb2_grpc.UserServiceServicer):
    def GetUser(self, request, context):
        return user_pb2.UserResponse(id=request.user_id, name="Иван Иванов")

server = grpc.server(futures.ThreadPoolExecutor(max_workers=10))
user_pb2_grpc.add_UserServiceServicer_to_server(UserService(), server)
server.add_insecure_port("[::]:50051")
server.start()
server.wait_for_termination()
```

## 📌 Когда использовать gRPC?
- Когда нужна высокая производительность и низкая задержка
- Когда требуется двусторонняя потоковая передача данных
- В микросервисной архитектуре
- В распределенных системах

---
📚 Следующий файл будет о REST!