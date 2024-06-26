# Финальный проект 7 спринта курса Яндекс Практикум "Автоматизация тестирования на Java".
## Тестирование API приложения Яндекс Самокат.

Стек технологий:
Java 11, Rest Assured, Maven, Allure

Запуск программы с формированием отчета Allure:

``` shell
mvn clean test
mvn allure:serve
```
--------------------------------------------------------------------------------------

# Техническое задание.

## Документация API: [Сервис Яндекс Самокат](https://qa-scooter.praktikum-services.ru/docs/ "API сервиса Яндекс Самокат")

### Протестируй ручки.

Проверь, что они корректно работают и выдают нужные ошибки.
1. Создание курьера
    - курьера можно создать;
    - нельзя создать двух одинаковых курьеров;
    - чтобы создать курьера, нужно передать в ручку все обязательные поля;
    - запрос возвращает правильный код ответа;
    - успешный запрос возвращает ok: true;
    - если одного из полей нет, запрос возвращает ошибку;
    - если создать пользователя с логином, который уже есть, возвращается ошибка.
2. Логин курьера
    - курьер может авторизоваться;
    - для авторизации нужно передать все обязательные поля;
    - система вернёт ошибку, если неправильно указать логин или пароль;
    - если какого-то поля нет, запрос возвращает ошибку;
    - если авторизоваться под несуществующим пользователем, запрос возвращает ошибку;
    - успешный запрос возвращает id.
3. Создание заказа <br> *Чтобы протестировать создание заказа, нужно использовать параметризацию.
    - можно указать один из цветов — BLACK или GREY;
    - можно указать оба цвета;
    - можно совсем не указывать цвет;
    - тело ответа содержит track.
4. Список заказов.
   Проверь, что в тело ответа возвращается список заказов.

5. Отчёт Allure.
   Сгенерируй его и запушь в репозиторий.

### *Дополнительное задание.

Это задание можешь выполнить по желанию: оно не повлияет на оценку за основную часть, но поможет дополнительно попрактиковаться.
Протестируй ручки:
1. Удалить курьера
    - неуспешный запрос возвращает соответствующую ошибку;
    - успешный запрос возвращает ok: true;
    - если отправить запрос без id, вернётся ошибка;
    - если отправить запрос с несуществующим id, вернётся ошибка.
2. Принять заказ
    - успешный запрос возвращает ok: true;
    - если не передать id курьера, запрос вернёт ошибку;
    - если передать неверный id курьера, запрос вернёт ошибку;
    - если не передать номер заказа, запрос вернёт ошибку;
    - если передать неверный номер заказа, запрос вернёт ошибку.
3. Получить заказ по его номеру
    - успешный запрос возвращает объект с заказом;
    - запрос без номера заказа возвращает ошибку;
    - запрос с несуществующим заказом возвращает ошибку.

### Как будут оценивать твою работу

1. Нейминг элементов корректный. Если не помнишь правила, посмотри в шпаргалку.
2. В pom.xml нет ничего лишнего.
3. Тесты лежат в src/test/java.
4. Для каждой ручки тесты лежат в отдельном классе.
5. Написаны тесты на ручку «Создать курьера».
6. Написаны тесты на ручку «Логин курьера».
7. Написаны тесты на ручку «Создать заказ».
8. Написаны тесты на ручку «Удалить курьера».
9. Написаны тесты на ручку «Принять заказ».
10. Написаны тесты на ручку «Получить заказ по его номеру».
11. Написаны тесты на ручку, которая получает список заказов.
12. Для всех шагов автотестов должна быть использована аннотация @Step.
13. Сделан отчёт с помощью Allure. Не забудь закоммитить его. 
14. В тестах проверяется тело и код ответа. 
15. Все тесты независимы. 
16. Необходимые тестовые данные создаются перед тестом и удаляются после того, как он выполнится. 
17. В тестах нет хардкода. 
18. В проекте используется Java 11.