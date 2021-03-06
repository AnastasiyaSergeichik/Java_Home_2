# Отчет о проверке Credit Card Number Validator.
**Проведено:**
 - тестирование установки IntelliJ IDEA на Windows 10, его запуск и совместимость с Java 11, работает ли приложение согласно руководству пользования.
 - функциональное тестирование приложения "Credit Card Number Validator"

**Дата начала** - 09.09.2020

**Дата окончания** - 09.09.2020

**На тестирование затрачено** - 1 час 

**В процессе тестирования использовались следующие артефакты:**
1. Руководство по установке IntelliJ IDEA
2. Код от предыдущего программиста по [ссылке](https://github.com/netology-code/javaqa-homeworks/tree/master/intro)

**В результате тестирования выявлены следующие дефекты:**
 * Программа считает валидными только 16-ти значные номера банковских карт. Сообщение "Result is OK"
 * Номера карт с длинной 14, 15, 19 цифр программа считает невалидными. Сообщение "Result is FAIL"

Ссылка [https://github.com/AnastasiyaSergeichik/Java_Home_2/issues/1](https://github.com/AnastasiyaSergeichik/Java_Home_2/issues/1)

## Описание процесса тестирования
1. Установить IntelliJ IDEA согласно [Руководство по установке IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)
2. В IntelliJ IDEA открыть созданный проект
3. В панеле проекта (Alt + 1) раскрыть структуру каталогов и на каталоге src правой кнопкой мыши выбрать "New" -> "Java Class"
4. В открывшемся окне ввести Main и нажать клавишу "Enter"
5. В файл Main.java вставить код оставленный предыдущим программистом.
6. Проверить работу кода запуская программу с разными тестовыми данными.

**В качестве тестовых данных использовались данные с сервиса [freeformatter.com](https://www.freeformatter.com/credit-card-number-generator-validator.html)**
Сервис генерирует валидные номера карт.
 
Список валидных тестовых данных (вывод сообщения "Result is OK")
 ![](pic/CCNG.jpg)

**Тестирование производилось в следующем окружении:**
 notebook LG-book; 
 Windows 10;
 Java, Version 11.0.8; 
 Chrome, Version 84.0.4147.105
