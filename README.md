# Bus-Manager
Реализована система хранения автобусных маршрутов. Обрабатывает следующие запросы:

NEW_BUS bus stop_count stop1 stop2 ... — добавить маршрут автобуса с названием bus и stop_count остановками с названиями stop1, stop2, ...

BUSES_FOR_STOP stop — вывести названия всех маршрутов автобуса, проходящих через остановку stop.

STOPS_FOR_BUS bus — вывести названия всех остановок маршрута bus со списком автобусов, на которые можно пересесть на каждой из остановок.

ALL_BUSES — вывести список всех маршрутов с остановками.

Формат ввода

В первой строке ввода содержится количество запросов Q, затем в Q строках следуют описания запросов.

Гарантируется, что все названия маршрутов и остановок состоят лишь из латинских букв, цифр и знаков подчёркивания.

Так же выполнена декомпозиция программы:

  1.query.h, в него кладём:

enum class QueryType
struct Query
объявление istream& operator >> (istream& is, Query& q)

  2. query.cpp, в него кладём

определение istream& operator >> (istream& is, Query& q);

  3. responses.h:

struct BusesForStopResponse
ostream& operator << (ostream& os, const BusesForStopResponse& r)
struct StopsForBusResponse
ostream& operator << (ostream& os, const StopsForBusResponse& r)
struct AllBusesResponse
ostream& operator << (ostream& os, const AllBusesResponse& r)

  4. responses.cpp: определения всего, что объявлено в responses.h

  5. bus_manager.h: объявление класса BusManager

  6. bus_manager.cpp: определения методов класса BusManager

  7. main.cpp: функция main
