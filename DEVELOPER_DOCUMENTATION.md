# Документация разработчика

## Текст программы

### Наименование программы

**ImageInfoReader** — веб-приложение на основе HTML, CSS и JavaScript для чтения и отображения информации о графических файлах.

### Область применения

Программа предназначена для анализа графических файлов, извлечения их основных характеристик (размер, разрешение, глубина цвета, сжатие) и отображения этих данных в виде таблицы. Может использоваться в учебных целях, для демонстрации работы с файлами в браузере, а также как инструмент для анализа изображений.

### Назначение программы

- Чтение информации о графических файлах, включая:
  - Имя файла.
  - Размер изображения (в пикселях).
  - Разрешение (dpi).
  - Глубину цвета.
  - Тип сжатия.
- Предоставление удобного интерфейса для загрузки файлов и отображения их характеристик.
- Возможность сортировки данных по различным параметрам.
- Удаление элементов из таблицы.

### Функциональные возможности

- Загрузка графических файлов с устройства.
- Загрузка всех файлов из выбранной папки.
- Отображение информации о файлах в таблице.
- Возможность сортировки данных по имени, размеру, разрешению, глубине цвета и типу сжатия.
- Удаление последнего добавленного элемента из таблицы.

---

## Описание программы

### Структура программы

Программа состоит из трех основных частей:

1. **HTML**:
   - Структура страницы включает заголовок, панель управления (кнопки для загрузки файлов и удаления элементов) и таблицу для отображения информации.
   - Таблица содержит пять столбцов: имя файла, размер, разрешение, глубина цвета и тип сжатия.

2. **CSS**:
   - Стили для оформления страницы, таблицы и кнопок.
   - Таблица скрыта по умолчанию и отображается только после загрузки данных.

3. **JavaScript**:
   - Основная логика работы приложения:
     - Загрузка файлов и извлечение их характеристик.
     - Отображение данных в таблице.
     - Сортировка данных.
     - Удаление элементов из таблицы.

### Используемые технологии

- **HTML5**: для создания структуры веб-страницы.
- **CSS3**: для стилизации интерфейса.
- **JavaScript**: для обработки событий, работы с файлами и взаимодействия с DOM.

---

### Логика работы программы

#### Функциональные модули

1. **Загрузка файлов**:
   - При нажатии кнопки "Add files" создается элемент `<input type="file">`, который позволяет выбрать один или несколько графических файлов.
   - Для каждого файла создается объект `FileReader`, который считывает содержимое файла.
   - С помощью объекта `Image` анализируются размеры изображения (ширина и высота).

2. **Загрузка папки**:
   - При нажатии кнопки "Add from folder" создается элемент `<input type="file" webkitdirectory>`, который позволяет выбрать папку.
   - Все файлы из папки обрабатываются аналогично загрузке отдельных файлов.

3. **Отображение данных**:
   - Информация о каждом файле добавляется в массив `fileData`.
   - Данные выводятся в таблицу с помощью функции `renderTable`.

4. **Удаление данных**:
   - При нажатии кнопки "Remove item" удаляется последний элемент из массива `fileData`, и таблица обновляется.

5. **Сортировка данных**:
   - При клике на заголовок столбца данные сортируются по соответствующему параметру.
   - Сортировка может быть выполнена по возрастанию или убыванию.

---

### Взаимодействие с пользователем

1. Пользователь нажимает кнопку "Add files" или "Add from folder" для загрузки файлов.
2. После загрузки файлов информация о них отображается в таблице.
3. Пользователь может кликнуть на заголовок любого столбца для сортировки данных.
4. Для удаления последнего элемента из таблицы пользователь нажимает кнопку "Remove item".

---

## Инструкция по установке и запуску

### Требования

- Любой современный веб-браузер (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).
- Подключение к сети Интернет не требуется (программа работает локально).

### Установка

1. Сохраните HTML-код программы в файл с расширением `.html`, например, `image_info_reader.html`.

2. Откройте файл в браузере двойным кликом или через контекстное меню ("Открыть с помощью").

---

### Запуск программы

1. Откройте файл `image_info_reader.html` в браузере.
2. Интерфейс приложения загрузится, и вы увидите кнопки управления и пустую таблицу.

---

## Инструкция пользователя

1. **Загрузка файлов**:
   - Нажмите кнопку "Add files".
   - Выберите один или несколько графических файлов в открывшемся диалоговом окне.
   - Нажмите "Открыть". Информация о файлах появится в таблице.

2. **Загрузка папки**:
   - Нажмите кнопку "Add from folder".
   - Выберите папку с графическими файлами.
   - Информация о файлах из папки появится в таблице.

3. **Сортировка данных**:
   - Кликните на заголовок столбца, чтобы отсортировать данные по соответствующему параметру.
   - Повторный клик изменит направление сортировки (по возрастанию/убыванию).

4. **Удаление данных**:
   - Нажмите кнопку "Remove item", чтобы удалить последний добавленный файл из таблицы.

---

## Требования к техническим характеристикам

- **Браузер**: поддержка HTML5, CSS3 и JavaScript (современные версии).
- **Операционная система**: любая, поддерживающая браузеры (Windows, macOS, Linux, Android, iOS).
- **Оперативная память**: не менее 256 МБ.

---

## Обработка ошибок

- Если пользователь загружает файл, который не является изображением, он не будет добавлен в таблицу.
- Если массив файлов пуст, кнопка "Remove item" не вызывает ошибок, но таблица остается пустой.

---

## Дополнительные сведения

### Структура данных

- **Массив `fileData`**:
  - Хранит объекты с информацией о каждом загруженном файле.
  - Поля объекта:
    - `name` — имя файла.
    - `size` — размер изображения (ширина и высота в пикселях).
    - `resolution` — разрешение (по умолчанию 72 dpi).
    - `colorDepth` — глубина цвета (по умолчанию 24 бита).
    - `compression` — тип сжатия (определяется по MIME-типу файла).

### Масштабируемость

- Программа может быть расширена для обработки других типов данных (например, метаданных EXIF) или добавления новых параметров сортировки.

---

## Сопровождение и развитие

- Код программы написан с учетом модульности и читаемости, что упрощает его сопровождение.
- Для добавления новых функций необходимо обновить функции `handleFiles`, `renderTable` и соответствующие элементы интерфейса.

---

## Заключение

Программа **ImageInfoReader** предоставляет удобный инструмент для анализа графических файлов в браузере. Она проста в использовании, не требует установки и может быть легко расширена для поддержки дополнительных функций.