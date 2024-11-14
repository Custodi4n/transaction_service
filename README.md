# transaction_service
### Проект разделен на несколько микросервисов:
1. **Validation Service** - проверка корректности транзакции.
2. **Fraud Detection Service** - проверка на мошенничество.
3. **Logging Service** - логирование транзакции в базу данных.
4. **Valute Convertor Service** - конвертация валют с использованием курса, сохраненного в Redis.
5. **Transaction Web Interface** - веб-интерфейс для пользователя, позволяющий отправлять транзакции и видеть результат выполнения.
### Общий процесс
1. Пользователь вводит сумму и выбирает валюту в веб-интерфейсе, затем нажимает кнопку "Оплатить".

![image](https://github.com/user-attachments/assets/0b76fac8-0b3d-4316-b958-f97a3f6e6ceb)

2. Транзакция проходит через следующие этапы:
   - **Validation Service** проверяет корректность транзакции.
   - **Valute Convertor Service** конвертирует сумму в нужную валюту.
   - **Fraud Detection Service** проверяет транзакцию на мошенничество.
   - **Logging Service** сохраняет информацию о транзакции в базе данных.
3. После успешного выполнения всех этапов пользователю отображается сообщение "Оплата прошла успешно".

![image](https://github.com/user-attachments/assets/00408592-ae85-4d8c-84fe-130d904fc900)

### Структура проекта
  - main.py - основной файл для запуска микросервисов.
  - web_interface.py - файл для запуска веб-интерфейса.
  - services/validation_service.py - сервис валидации.
  - services/fraud_detection_service.py - сервис проверки на мошенничество.
  - services/logging_service.py - сервис логирования.
  - services/valute_convertor_service.py - сервис конвертации валют.
  - db.py - файл для инициализации базы данных.
  - container_setup.py - скрипт для настройки Docker-контейнеров Kafka и Redis.
