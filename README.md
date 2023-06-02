## SimpleVector<br>
контейнер, упрощенная версия std::vector, написана обертка указателя. Используется идиома RAII.
____
:point_up: Используемый стек:
`STL` `ООП` `move - семантика` `rvalue-ссылки`

:point_up: Системные требования:
` C++17 и выше`

:point_right: Использование:
 Загрузить файлы проекта в среду разработки для сборки (VisualStudio). 
 Пример использования расположен в main.cpp (показано в тестах). 

### Описание<br>
Реализованы конструкторы:
- [X] По умолчанию. Создаёт пустой вектор с нулевой вместимостью. Не выделяет динамическую память и не выбрасывает исключений.
- [X] Параметризованный конструктор, создающий вектор заданного размера. Элементы вектора инициализированы значением по умолчанию для типа Type. Вектор имеет одинаковые размер и вместимость.
- [X] Конструктор из std::initializer_list. Элементы вектора содержат копию элементов initializer_list. Имеет размер и вместимость, совпадающую с размерами и вместимостью переданного initializer_list.
- [X] Конструктор копирования. Копия вектора имеет вместимость, достаточную для хранения копии элементов исходного вектора.
- [X] Реализован конструктор по rvalue ссылке.

Реализованы методы:
- [X] GetSize для получения количества элементов в векторе (не выбрасывает исключений).
- [X] GetCapacity для получения вместимости вектора (не выбрасывает исключений).
- [X] IsEmpty, сообщающий, пуст ли вектор (не выбрасывает исключений).
- [X] At для доступа к элементу вектора по его индексу, аналог метода at класса vector. В случае выхода индекса за пределы массива выбрасывает исключение std::out_of_range.
- [X] Clear для очистки массива без изменения его вместимости (не выбрасывает исключений).
- [X] Resize для изменения количества элементов в массиве. Метод предоставляет строгую гарантию безопасности исключений.
- [X] begin, end, cbegin и cend, возвращающие итераторы на начало и конец массива (не выбрасывают исключений). В качестве итераторов используются указатели.
- [X] PushBack, добавляющий элемент в конец вектора. Обеспечивает строгую гарантию безопасности исключений.
- [X] PopBack, удаляющий последний элемент вектора (не выбрасывает исключений).
- [X] Insert, вставляющий элемент в произвольное место контейнера. Обеспечивает базовую гарантию безопасности исключений.
- [X] Erase, удаляющий элемент в произвольной позиции вектора. Обеспечивает базовую гарантию безопасности исключений.
- [X] swap, обменивающий содержимое вектора с другим вектором (не выбрасывает исключений). Имеет время выполнения O(1).
- [X] Reserve задает ёмкость вектора.
- [X] оператор [] для доступа к элементу вектора по его индексу (не выбрасывает исключений). Имеет две версии — константную и неконстантную. Для корректной работы оператора индекс элемента массива не должен выходить за пределы массива.
- [X] оператор присваивания. Обеспечивает строгую гарантию безопасности исключений.
- [X] операторы == и !=, <, >, <=, >=, необходимые для булевых операций, а также реализована возможность перемещения.
При разрушении вектора освобождается память, занимаемая его элементами.
