# Отчет о проверке Credit Card Number Validator.
**Проведено:**
 - тестирование установки IntelliJ IDEA на Windows 10, его запуск и совместимость с Java 11, работает ли приложение согласно руководству пользования.
 - функциональное тестирование приложения "Credit Card Number Validator"

**Дата начала** - 09.09.2020

**Дата окончания** - 09.09.2020

**На тестирование затрачено** - 0,5 часа 

**В процессе тестирования использовались следующие артефакты:**
1. Руководство по установке IntelliJ IDEA
2. Код от предыдущего программиста
public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "5351719427810741";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
}

**В результате тестирования выявлены следующие дефекты:**
Программа считает валидными только 16-ти значные номера банковских карт

## Описание процесса тестирования
1. Установить IntelliJ IDEA согласно [Руководство по установке IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)
2. В IntelliJ IDEA открыть созданный проект
3. В панеле проекта (Alt + 1) раскрыть структуру каталогов и на каталоге src правой кнопкой мыши выбрать "New" -> "Java Class"
4. В открывшемся окне ввести Main и нажать клавишу "Enter"
5. В файл Main.java вставить код оставленный предыдущим программистом.
6. Проверить работу кода запуская программу с разными тестовыми данными.

**В качестве тестовых данных использовались данные с сервиса [freeformatter.com](https://www.freeformatter.com/credit-card-number-generator-validator.html)**
Сервис генерирует валидные номера карт.

## Ожидаемый результат:
 *Тестовые данные валидные
 *Сообщение "Result is OK"

## Фактический результат:
Программа считает валидными номера карт с длинной 16 цифр. Сообщение "Result is OK"
Номера карт с длинной 14, 15, 19 цифр программа считает невалидными. Сообщение "Result is FAIL"


**Тестирование производилось в следующем окружении:**
 notebook LG-book; 
 Windows 10;
 Java, Version 11.0.8; 
 Chrome, Version 84.0.4147.105