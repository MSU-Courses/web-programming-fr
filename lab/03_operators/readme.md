# Лабораторная работа 2. Использование операторов. Условные конструкции.

## Цель

Познакомиться с оператором `if`, тернарным оператором и оператором `switch`. Научиться анализировать работу условных конструкций и применять функции для обработки даты.

## Условие

1. Главный файл лабораторной работы должен называться `index.php`.
2. Используйте современные IDE, такие как **PhpStorm** или **Visual Studio Code**.
3. Запустите веб-сервер одним из следующих способов:
   - **OpenServer**: сохраните файлы в директории `www/domains/localhost`.
   - **Встроенный сервер PHP**:
     ```bash
     php -S localhost:8000
     ```
     Выполните команду в терминале в директории, где находится файл `index.php`.
4. Для проверки работы скриптов откройте браузер:
   - Для **OpenServer**: `http://localhost/название_папки/`.
   - Для встроенного сервера PHP: `http://localhost:8000/`.

## Ход работы

### Задание 1

1. Создайте файл `index.php` со следующим кодом:

   ```php
   <?php
   $lastName = 'Ivanov';
   $firstName = 'Nikolai';
   echo 'Client\'s last name is '.$lastName.', and their first name is '.$firstName.'.';

   $age = 30;
   print '<br>Client\'s age is '.$age.'.';
   ```

2. Сохраните файл и запустите веб-сервер.
3. Проанализируйте скрипт, объяснив:
   - Что делают переменные `$lastName`, `$firstName` и `$age`?
   - Как выполняется вывод данных?

### Задание 2

1. В файл `index.php` добавьте следующий код:

   ```php
   <?php
   $currentDay = date("D");

   if ($currentDay === "Fri") {
       echo "<br>Have a great weekend!";
   } else {
       echo "<br>Have a productive workday!";
   }
   ```

2. Замените `if...else` на тернарный оператор:
   ```php
   echo ($currentDay === "Fri") ? "<br>Have a great weekend!" : "<br>Have a productive workday!";
   ```
3. Верните `if...else` и добавьте ветку `elseif`:
   ```php
   elseif ($currentDay === "Sun") {
       echo "<br>Tomorrow starts a new work week!";
   }
   ```
4. Измените условие, используя числовое обозначение дня недели (`w`) вместо буквенного (`D`), и обновите вывод.

### Задание 3

1. Создайте файл `operator.php` со следующим кодом:

   ```php
   <?php
   // Example using if
   $age = 22;

   if ($age > 12 && $age < 20) {
       $message = "you are a teenager!";
   } elseif ($age > 40) {
       $message = "you are an adult!";
   } else {
       $message = "you are in your prime... get to work!";
   }

   // Example using a ternary operator
   $name = "Anna";
   echo $name ? $name.', '.$message : 'Anonymous, '.$message;
   ```

2. Проанализируйте скрипт:
   - Что реализуют условные конструкции `if` и тернарный оператор?
   - Какое значение принимает `$message`?

### Задание 4

1. Используя `switch` и функцию `date()`, проверьте текущий день недели и выведите сообщение в формате:
   ```
   Today is [weekday], [dd.mm.yyyy]
   ```
2. Пример кода:

   ```php
   <?php

   $day = date("w");

   switch ($day) {
       case 0:
           echo "Today is Sunday, ".date("d.m.Y");
           break;
       case 1:
           echo "Today is Monday, ".date("d.m.Y");
           break;
       case 2:
           echo "Today is Tuesday, ".date("d.m.Y");
           break;
       default:
           echo "Unknown day";
           break;
   }
   ```

### Задание 5

1. Используя функцию `date()`, создайте таблицу с содержимым, отображающим расписание на основе текущего дня недели.

**Формат таблицы**:

| №   | Фамилия Имя | График работы |
| --- | ----------- | ------------- |
| 1   | John Styles | xx - xx       |
| 2   | Jane Doe    | yy - yy       |

- **Для John Styles (xx - xx):**

  - Если текущий день недели — понедельник, среда или пятница, выведите график работы `8:00-12:00`.
  - В остальные дни недели выведите текст: `Нерабочий день`.

- **Для Jane Doe (yy - yy):**
  - Если текущий день недели — вторник, четверг или суббота, выведите график работы `12:00-16:00`.
  - В остальные дни недели выведите текст: `Нерабочий день`.

## Отчет

1. Отчет по лабораторной работе должен соответствовать [Гиду по написанию отчетов по лабораторным работам](../lab_guidelines.md).
