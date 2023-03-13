#Web-API игры Крестики-нолики

Endpoint: https://localhost:7075/xo
HTTP Methods: 
GET - Возвращает текущее состояние игры
POST - Принимает через json координаты ячейки в которую пытаются походить в формате {"x": (0-2), "y" (0-2)}, где x - это координата по горизонтали от 0 до 2, а y - это координата по вертикали от 0 до 2. Возвращает обработанные данные.
DELETE - Сбрасывет игру к начальным параметрам и возвращает данные.

Данные возвращаются в виде json строки:
{
  "field": [    
    "e",
    "e",
    "e",
    "e",
    "e",
    "e",
    "e",
    "e",
    "e"
  ],
  "player": "x",
  "status": 0,
  "codeWin": 0,
  "count": 9
}

Переменная field представляет из себя массив из 9 элементов, являющимся полем игры последовательно сложенными строками игровой сетки.
В элементах возможны 3 значения:
    e - Ячейка пуста
    x - В ячейке стоит крестик
    o - В ячейке стоит нолик
Переменная player возможно 2 значения:
    x - На этом ходу играет крестик
    o - На этом ходу играет нолик
Переменная status хранит код текущего состояния игры:
    0 - Всё нормально игра идет
    1 - Игра окончена в ничью
    2 - Игра окончена победой крестика
    3 - Игра окончена победой нолика
    4 - Была попытка походить в ячейку в которую уже ходили, данные игрового поля не меняются
Переменная codeWin хранит код победного ряда:
    0 - Игра не окончена либо ничья
    1 - Горизонтальный ряд 1 линия
    2 - Горизонтальный ряд 2 линия
    3 - Горизонтальный ряд 3 линия
    4 - Вертикальный ряд 1 колонка
    5 - Вертикальный ряд 2 колонка
    6 - Вертикальный ряд 3 колонка
    7 - Диагональный ряд \
    8 - Диагональный ряд /
Переменная count хранит число оставшихся пустых ячеек
