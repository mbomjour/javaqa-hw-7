# Github Actions и покрытие кода с JaCoCo
Перед вами код сервисного класса:
```java
package ru.netology.statistic;

public class StatisticsService 
    public long findMax(long[] incomes) {
        long currentMax = incomes[0];
        for (long income : incomes) {
            if (currentMax < income) {
                currentMax = income;
            }
        }
        return currentMax;
    }
}
```
И код тест-класса, который его тестирует:
```java
package ru.netology.statistic;

import org.junit.jupiter.api.Test;

import org.junit.jupiter.api.Assertions;

public class StatisticsServiceTest {

  @Test
  void findMax() {
    StatisticsService service = new StatisticsService();

    long[] incomesInBillions = {12, 5, 8, 4, 5, 3, 8, 6, 11, 11, 12};
    long expected = 12;

    long actual = service.findMax(incomesInBillions);

    Assertions.assertEquals(expected, actual);
  }
}
```
Ваша задача состоит в том, чтобы:
1. Создать Maven-проект и поместить в него эти два класса;
2. Запустить `mvn clean test` и убедиться, что тесты проходят;
3. Создать публичный репозиторий и запушить в него проект;
4. Настроить CI на основе Github Actions;
5. Добавить в проект JaCoCo и настроить его в режиме обрушения сборки по недостаточному покрытию, а именно 100% покрытие по счётчику `BRANCH`;
6. Запустить `mvn clean verify` и убедиться, что сборка упадёт из-за недостаточного покрытия;
7. Проанализировать сгенерированный отчёт по покрытию, дописать недостающие тесты (сам же сервисный класс трогать нельзя!) для полного покрытия;
8. Сделать коммит и пуш, убедиться что сборка на гитхабе проходит.
