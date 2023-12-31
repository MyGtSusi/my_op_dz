# Отчет
## Вариант 23
Лепендин Дмитрий Алексеевич, студент группы БПИ-218

### Условие задачи
```
Задача об инвентаризации по книгам. После нового года в
библиотеке университета обнаружилась пропажа каталога. После
поиска и наказания, виноватых ректор дал указание восстановить
каталог силами студентов. Фонд библиотека представляет собой
прямоугольное помещение, в котором находится M рядов по N шкафов по K книг в каждом шкафу. Требуется создать приложение, составляющее каталог. При решении задачи в качестве
отдельного процесса задается внесение в каталог записи об отдельной книге, которая сразу ставится на место в соответствии с выбранным методом упорядочения каталога. Примечание. Каталог —
это список книг, упорядоченный по их инвентарному номеру или
по алфавиту (на выбор разработчика). Каждая строка каталога содержит идентифицирующее значение (номер или название),
номер ряда, номер шкафа, номер книги в шкафу.
```

### Схема решаемой задачи
- В программе будут взаимодействовать клиент(студент) и сервер(библиотекарь).
- Клиент читает данные из файла. 
- После этого клинт отправляет отправляет данные о каждоый книге на сервер по UDP. 
- При этом, книга считается отправленной тогда, когда с сервера пришел ответ о том, что книга получена.
- Сервер принимает сообщение по udp и обрабатывает их, затем отчитывается о получении ответным сообщением

Клиент принимает данные в виде списка:

[номер ряда] [номер полки] [номер книги] [id книги]


пример:
```
1 1 1 122
1 1 2 123
1 2 1 212
1 2 2 213
```

### Компиляция программы

```
gcc student.c -o client && gcc server.c -o librarian
```

### Запуск программы

Клиент принимает аргументами при запуске имя файла с данными, порт и адрес сервера, или настройки по умолчанию в зависимости от кол-ва аргументов

Сервер принимает адрес и порт, или использует настройки по умолчанию 
