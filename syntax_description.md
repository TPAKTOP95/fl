Описание языка спецификации конечных автоматов
==========================================

Файл с описанием состоит из пяти частей.
* Конечное множество состояний
* Входной алфавит
* Стартовое состояние из множества состояний
* Множество принимающих состояний -- подмножество множества состояний
* Множество правил

Пробельные символы вне скобок и кавычек игнорируется, поэтому пустая строка может быть записана как `""`.

Комментарии в языке не предусмотрены.

Символы операторов в состояниях и символах алфавита экранируются с помощью `\`

### Множество состояний
Представляет собой конструкцию ввида `STATES = {...}` внутри фигурных скобок на месте троеточия 
находятся состояния, разделённые оператором запятой `,`

### Входной алфавит
Аналогично предствляется в виде `ALPHABET = {...}`

### Стартовое состояние
Представляется в виде `INITIAL = {...}`, однако в скобках содержиться лишь одно состояние, при большем количестве состояний 
пользователю выёдет ошибка и выставиться первое ведённое состояние

### Множество принимающих состояний
Описывается как `FINITE = {...}`, если элемент в скобках не является состоянием описанным в разделе 
`STATES`, то пользователь видит сообщение об ошибке, а соответсвующий элемент игнорируется

### Множество правил
Каждой правило задаётся в виде `(..) ++ ".." -> (..)`, где в круглых скобках элементы из множества состояний, а в кавычках 
элементы алфавита, если в скобках находится не элемент соответствующего множества, то пользователь видит ошибку, а 
правило игнорируется.