# Читы! HESOYAM

Оглавление:
* [Типы данных](#типы-данных)
* [Операции](#операции)
* * [Вывод в консоль](#вывод-в-консоль)
* * [Сложение](#сложение)
* * [Условия](#условия)
* * [Циклы](#циклы)
* * * [-> Читай: крутые циклы](https://github.com/powerdot/cheats/blob/master/cool_for.md)
* * [Четное & нечетное](#четное--нечетное)
* [Примеры кода](#примеры-кода)
* [Готовые программки](#готовые-программки)
* * [Поиск среднего арифметического](#поиск-среднего-арифметического)
* * [Поиск минимального и максимального числа](#поиск-минимального-и-максимального-числа)
* * [Умное отображение лайков](#умное-отображение-лайков)
* * [Поиск квартир](#поиск-квартир)

```js
// вот так ставить комментарий в одну строку
/*
    если комментарий нужен на кучу строк,
    то вот так.
    В комментариях код не работает, его просто не видит программа
*/
```

## Типы данных
### Строки (звать String)
```js
var a = "привет";
var a1 = 'глеб, ' + "привет"; // -> глеб, привет
```

### Целые числа (звать Integer)
```js
var b = 5;
var b1 = -11;
```

### Числа с плавающей (floating) точкой (звать Float или Decimal)
```js
var c = 0.3423;
var c1 = 1/2;
```

### Объект (звать Object)
```js
var human_ivan = {
    name: "Иван",
    lastname: "Иванов"
}
// Объект очень полезен, чтобы хранить информацию "в пакете"
// Не будем же мы разбрасывать информацию о человеке в миллионах переменных.
// Информацию хранят в таких пакетах. Структурировано.

// Её можно достать так:
console.log( human_ivan.name ) // -> "Иван"
```

### Массив (звать Array)
```js
// В них можно хранить любую дичь: 
// числа, текст, объекты и даже массивы, и даже массивы с объектами, в нутри которых есть массивы!
var array = [1,2,3,4];
var array1 = ["глеб", 'никита', 'демур', 'женя'];
var array2 = [6, 3, "привет", 2.75, 6/2]; // -> [6, 3, "привет", 2.75, 3];
var array3 = [
    {name: "иван", lastname: "иванов", friends: ["илья", "глеб"]},
    {name: "петр", lastname: "петрович", friends: ["максим", "славик"]}
];
var array4 = [
    [4, 5, 6, 7],
    [8, 9, 1, 2]
];
```

## Операции

### Вывод в консоль
```js
console.log("лол"); // -> лол
console.log("лол ", ' кек'); // -> лол   кек (заметь, 3 пробела, потому что запятая добавляет разделитель в виде пробела)
console.log("привет, " + "глеб!"); // -> привет, глеб!
console.log("привет," , "глеб!"); // -> привет, глеб!
    
var name = "глеб";
console.log("привет, " + name + "!"); // -> привет, глеб!
```

### Сложение
```js
var a = 1;
a++; // -> 2
a+=1; // -> 3
a=a+1; // -> 4
a-=-1; // -> 5
a-=1; // -> 4

a = "привет"; // "a" теперь носит "привет", а не 4
a += ", глеб"; // -> привет, глеб
a = a+"!"; // -> привет, глеб!
```

### Условия
```js
var a = 5;
var b = 6;

// просто условие
if(a > b){
    console.log("a больше b"); // -> a больше b
}

// условие с "иначе"
if(a == b){
    console.log("a равно b");
}else{
    console.log("a НЕ равно b"); // -> a НЕ равно b
}

if(a == 4){
    console.log("a равно 4");
}else if(a==5){
    console.log("a равно 5"); // -> a равно 5 
}else if(a == 6){
    console.log("a равно 6");
}

// супер-пупер короткие условия
// строение: УСЛОВИЕ ? TRUE : FALSE

var res = a==b ? "a равно b" : "a НЕ равно b";
console.log( res ); // -> a НЕ равно b

// точно так же, но без переменной res:
console.log( a!=b ? "a НЕ равно b" : "a равно b" ); // -> a НЕ равно b
```

### Циклы
```js
// for от 0 до 4 (0,1,2,3,4)
for(var i=0; i<5; i++){ ... }
for(var i=0; i==4; i++){ ... }
for(var i=0; i>=4; i++){ ... }

// while (тот же for, только больше), мы его обычно не используем
var i = 0;
while(i<5){
    ...
    i++;
}
```
[-> Читай: крутые циклы](https://github.com/powerdot/cheats/blob/master/cool_for.md)

### Четное & нечетное
```js
// (число)%2 - выдает 0 - если четное, и 1 - нечетное

var number = 8;
var res = number%2; // -> 0 - четное

number = 11;
res = number%2; // -> 1 - нечетное

console.log( 63%2 ); // -> 1 - нечетное
```

## Примеры кода

### Вывод количества элементов и 0-го элемента
```js
var x = ["привет", 'как дела', 'что делаешь'];
console.log(x.length, x[0]); // -> 3, "привет"
```

### Существует ли элемент в массиве?
```js
var array = ["привет", 'как дела', 'что делаешь'];
var search = "как дела";
if( array.includes(search) ){ // <- ищем через .includes
    console.log("массив содержит:", search); // -> "массив содержит: как дела"
}else{
    console.log("массив x НЕ содержит", search);
}
```

### Добавляем элемент в массив
```js
var array = ["привет", 'как дела', 'что делаешь'];
array.push('кек');
console.log(array); // -> ["привет", "как дела", "что делаешь", "kek"]
```

## Готовые программки
### Поиск среднего арифметического
```js
var array = [3,4,5,6,7,8];
var sum = 0;

for(var i=0; i<array.length; i++){
    sum += array[i];
}

console.log("ср. арифм:", sum/array.length);
```

### Поиск минимального и максимального числа
```js
var array = [3,678,3,24,6,7,3,2,3,4023,3,-45,-3,43,23,-454,312,34,3454];
var min = array[0];
var max = array[0];

for(var i = 0 ; i < array.length; i++){
	if(array[i] < min){
		min = array[i];
	}
	if(array[i] > max){
		max = array[i];
	}
}

console.log('my min:', min, 'my max:', max);
```

### Умное отображение лайков
```js
var names = ["илья"];
var res = "еще никто не лайкнул твой пост =(";

if(names.length == 1) res = names[0]+ ' лайкнул твой пост';
if(names.length == 2) res = names[0]+ ' и ' + names[1]+ ' лайкнули твой пост';
if(names.length == 3) res = names[0]+ ', ' + names[1]+ ' и ' + names[2] + ' лайкнули твой пост';
if(names.length > 3) res = names[0]+ ' и еще ' + (names.length - 1) + ' человека лайкнули твой пост';

console.log(res);
```

### Поиск квартир
```js
var array = [
  {street: 'ул. Боярская', house: '22к3', room: '202', size: 60, price: 8000000},
  {street: 'ул. Тысячичертеская', house: '15', room: '56', size: 45, price: 5000000},
  {street: 'ул. Эполпарковская', house: '1c4', room: '11', size: 75, price: 15000000},
  {street: 'ул. Глебовская', house: '6', room: '2', size: 70, price: 20000000},
  {street: 'ул. Илюшинская', house: '34', room: '7', size: 69, price: 18000000},
  {street: 'ул. Алексовская', house: '31', room: '53', size: 53, price:6000000},
  {street: 'ул. Мемасная', house: '14', room: '88', size: 23, price: 3000000},
  {street: 'ул. Навальновская', house: '3с2', room: '24', size: 94, price: 12000000},
  {street: 'ул. Собянинская', house: '6с3', room: '64', size: 68, price: 4900000},
  {street: 'ул. Спбшная', house: '5', room: '55', size: 85, price: 25000000},
  {street: 'ул. Кальянная', house: '7к4', room: '44', size: 66, price: 9000000},
  {street: 'ул. Гейпарадная', house: '3', room: '23', size: 25, price: 2000000},
  {street: 'ул. Первонаховская', house: '11с1', room: '3', size: 77, price: 50000000},
];
var search_size = 60;

var found_rooms = array.filter(x=> x.size>=search_size); // ищу хаты с нужным метражом

var price_sum = 0;

for(var room of found_rooms){
	price_sum += room.price;
}

var mid_price = price_sum / found_rooms.length; // нахожу среднюю стоимость

console.log( "Всего квартир размером больше или равно " + search_size + " км.м: " + found_rooms.length );
console.log( "Средняя стоимость этих квартир " + mid_price + " руб." );
```
