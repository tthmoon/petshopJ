Решение тестового задания в Яндекс.Финтех

Реализация:
Java минимум 8 версии.
Gradle 7.2.
Allure.

Используемые библиотеки:
Rest-assured.
JUnit5.
Assertj.
Allure gradle plugin.
Openapi generator gradle plugin.

Предисловие:
Решение написал на Java, так как написание на Python заняло бы слишком много времени (последний раз пару лет назад писал на нем). 
Для решения задачи выбрал кодогенерацию клиента и моделей gradle-плагином. Важно, из-за специфики последнего опыта не имел опыта использования генерации, это мой первый опыт.

Перед написанием тестов был созданы клиенты, модели, шаблоны тестов с использованием плагина (https://github.com/OpenAPITools/openapi-generator/tree/master/modules/openapi-generator-gradle-plugin). Базовые шаблоны генерации были подредактированы, чтобы:
1) Изменение генерации файла build.gradle, где добавлены новые либы + таски для запуска тестов.
2) Шаблон генерации тестов, чтобы они генерировались под формат JUnit5.
После руками написал 3 теста. Дла запуска используется gradle-task. В результате прогона тестов формируется артефакт с allure-results.

Инструкция по запуску:
Из директории с тестами выполнить команду в терминале "gradle petTagTests". Либо запустить таску petTagTests, в случае использование интерфейса.

Инструкция по просмотру результатов:
Из директории с тестами выполнить команду в терминале "allure serve petshopTests/build/allure-results". Необходима установка allure (https://docs.qameta.io/allure/#_commandline).

Важная информация:
1) Тест повторяющийся 10 раз проверяет функциональность с багой, таким образом можно увидеть, что тест мигает.
2) Фреймворк писался с целью показать минимальный функциональность. Реализация архитектуры, способа запуска тестов опущены.
3) Тесты не имеют подробного описания, а также отсутствует пачка аннтация для allure. Пропустил этот момент, так как не определенных правил, как отчет должен выглядеть.