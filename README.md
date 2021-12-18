# All js methods
## Методы строк
##### `str.charAt()` - Аналог обращения по индексу
```javascript
const str = 'Hello, world!';

console.log(str.charAt(0)); //* 'H';
console.log(str[0]); //* 'H'
console.log(str.charAt(1)); //* 'e'
```
##### `str.at()` - Возвращает символ под определенным индексом
```javascript
const str = 'Hello, world!';

console.log(str.at(0)); //* 'H'
console.log(str.at(4)); //* 'o';
console.log(str.at(-1)); //* '!'
```
##### `str.charCodeAt()` - Возвращает unicode номер
```javascript
const str = 'Hello, world!';

console.log(str.charCodeAt(0)); //* 72
console.log(str.charCodeAt()); //* 72; значение 0 по умолчанию
console.log(str.charCodeAt(1)); //* 101
console.log('e'.charCodeAt()); //* 101
```
##### `str.concat()` - Объединяет строки
```javascript
const str1 = 'Hello, ';
const str2 = 'World!';

console.log(str1.concat(str2)); //* 'Hello, World!'
console.log(str1.concat({})); //* 'Hello, [object Object]!'; преобразует объект к строке
console.log(str1.concat([])); //* 'Hello, '; преобразует массив к ''
```
##### `str.startsWith()/str.endsWith()`
```javascript
const str = 'Hello, world!';

console.log(str.startsWith('Hell')); //* true
console.log(str.startsWith('Hell', 2)); //* false; ищет совпадение со второго индекса
console.log(str.startsWith('hell')); //* false; метод чувствителен к регистру
console.log(str.endsWith('abame')); //* false
```
##### `str.includes()` - Проверка на подстроку в строке
```javascript
const str = 'Hello, world!'

console.log(str.includes('llo')); //* true; подстрока есть
console.log(str.includes('world', 3)); //* true; ищет совпадение с третьего индекса
console.log(str.includes('abame')); //* false; подстроки нет
```
##### `str.indexOf()/str.lastIndexOf()` - Возвращает индекс с которого начинается подстрока
```javascript
const str = 'Hello, world!'

console.log(str.indexOf('llo')); //* 2
console.log(str.indexOf('l', 4)); //* 10; будет искать совпадения с четвертого индекса
console.log(str.indexOf('AAA')); //* -1; выозвращает если мы передаем несуществующую подстроку
console.log(str.lastIndexOf('l')); //* 10; будет искать совпадения с конца
```
##### `str.slice()` - Возвращает обрезанную строку
```javascript
const str = 'Hello, world!'

console.log(str.slice(2, 8)); //* 'llo, wo'; обрезает строку от индекса 2 до 8 (не включая 8ой)
console.log(str.slice(7, -2)); //* 'worl'; обрезает строку от индекса 7 до 2го с конца т.е. 11
console.log(str.slice()); //* 'Hello, world!'; обрежет строку от начала и до конца
console.log(str.slice(2)); //* 'llo, world!'; обрежет строку от 2го индекса и до конца
```
##### `str.substr()` - Возвращает обрезанную строку
```javascript
const str = 'Hello, world!'

console.log(str.substr(2, 7)); //* 'llo, wo'; обрезает 7 символов со второго индекса
```
##### `str.split()` - Преобразует строку в массив по разделителю
```javascript
const str = 'Hello, world!'

console.log(str.split()); //* ['Hello, world!']
console.log(str.split('')); //* ['H', 'e', 'l', 'l', 'o', ',', ' ', 'w', 'o', 'r', 'l', 'd', '!']
console.log(str.split(' ')); //* ['Hello,', ' world!']
```
##### `str.toUpperCase()/str.toLowerCase()` - Преобразует строку в верхний/нижний регистр
```javascript
const str = 'Hello, world!'

console.log(str.toUpperCase()); //* 'HELLO, WORLD!'
console.log(str.toLowerCase()); //* 'hello, world!'
```
##### `str.trim()` - Удаляет пробелы с начала и конца
```javascript
const str = '   Hello, world!   '

console.log(str.trim()); //* 'Hello, world!'
console.log(str.trimStart()); //* 'Hello, world!   '; удаляет только в начале
console.log(str.trimEnd()); //* '   Hello, world!'; удаляет только в конце
```
## Методы массивов
##### `arr.push()/arr.pop()/arr.shift()/arr.unshift()` - МУТАБЕЛЬНЫЕ!
```javascript
let arr = ['one', 'two', 'three', 'four', 'five', 'six']

arr.push(100, 200); //* добавляет элемент(ы) в конец массива
console.log(arr); //* ['one', 'two', 'three', 'four', 'five', 'six', 100, 200]

console.log(arr.pop()); //* 200; удаляет последний элемент массива и возвращает его
console.log(arr); //* ['one', 'two', 'three', 'four', 'five', 'six', 100]

arr.unshift(10, 20); //* добавляет элемент(ы) в начало массива
console.log(arr); //* [10, 20, 'one', 'two', 'three', 'four', 'five', 'six', 100]

console.log(arr.shift()); //* 10; удаляет элемент с начала массива и возвращает его
console.log(arr); //* [ 20, 'one', 'two', 'three', 'four', 'five', 'six', 100]
```
##### `arr.concat()`- ИММУТАБЕЛЬНЫЙ! Объединяет массивы
```javascript
const arr1 = ['one', 'two', 'three'];
const arr2 = ['a', 'b', 'c'];

console.log(arr1.concat()); //* ['one', 'two', 'three']; возвращает новую копию массива
console.log(arr1.concat(arr2, [1, 2, 3])); //* ['one', 'two', 'three', 'a', 'b', 'c', 1, 2, 3]; возвращает новый массив
console.log(arr1); //* ['one', 'two', 'three']; массив не изменился
```
------------
## Методы перебора массивов
##### `arr.forEach()` - Вызывает функцию на каждый элемент массива
```javascript
let arr = ['one', 'two', 'three', 'four', 'five', 'six'];

arr.forEach((el, i, arr) => {
	console.log(`
		Элемент: ${i + 1}

		Элемент массива: ${el}
		Индекс элемента: ${i}
		Весь массив: ${arr}
`)
})
```
##### `arr.customForEach()`
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

Array.prototype.customForEach = function (cb) {
	for (let i = 0; i < this.length; i++) {
		cb(this[i], i, this)
	}
};

arr.customForEach((el, i, array) => console.log(el, i, array));
```
##### `arr.map()` - Вызывает функцию на каждый элем массива и возвр новый массив
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

console.log(arr.map(el => {
	return el + '!'; //* map должен вернуть новый элемент
})); //* [ 'one!', 'two!', 'three!', 'four!', 'five!', 'six!' ]
console.log(arr); //* [ 'one', 'two', 'three', 'four', 'five', 'six' ]; основной массив не мутируется
```
##### `arr.customMap()`
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

Array.prototype.customMap = function (cb) {
	let newArr = [];
	for (let i = 0; i < this.length; i++) {
		newArr.push(cb(this[i], i, this))
	}
	return newArr;
};

console.log(arr.customMap((el) => {
	return el + '!'
}));
```
##### `arr.some()/arr.every()` - Проверка соответствует ли некоторые/все элем массива условию
```javascript
const arr = [10, 20, 30, 40, 50];

console.log(arr.some(el => el > 30)); //* true; true если хоть один элем соотв условию
console.log(arr.some(el => el === 5)); //* false

console.log(arr.every(el => el !== 5)); //* true; true если все элем соотв условию
console.log(arr.every(el => el < 30)); //* false
console.log(arr.every(el => typeof el === 'number')); //* true
console.log(arr.every(el => typeof el === 'string')); //* false
```
##### `arr.customSome()/arr.customEvery()`
```javascript
const arr = [10, 20, 30, 40, 50];

Array.prototype.customSome = function (cb) {
	for (let i = 0; i < this.length; i++) {
		if (cb(this[i], i, this)) return true
	}
	return false
};

console.log(arr.customSome(el => el > 30)); //* true; true если хоть один элем соотв условию
console.log(arr.customSome(el => el === 5)); //* false

Array.prototype.customEvery = function (cb) {
	for (let i = 0; i < this.length; i++) {
		if (!cb(this[i], i, this)) return false
	}
	return true
};

console.log(arr.customEvery(el => el !== 5)); //* true; true если все элем соотв условию
console.log(arr.customEvery(el => el < 30)); //* false
console.log(arr.customEvery(el => typeof el === 'number')); //* true
console.log(arr.customEvery(el => typeof el === 'string')); //* false
```
##### `arr.find()/arr.findIndex()` - Находит и возвр элемент/его индекс в массиве
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

console.log(arr.find((el, i, arr) => el === 'four')); //* 'four'; возвращает элемент
console.log(arr.find((el, i, arr) => i === 3)); //* 'four'

console.log(arr.findIndex((el, i, arr) => el === 'four')); //* 3; возврщает индекс элемента
console.log(arr.findIndex((el, i, arr) => i === 3)); //* 3
```
##### `arr.customFind()/arr.customFindIndex()`
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

Array.prototype.customFind = function (cb) {
	for (let i = 0; i < this.length; i++) {
		if (cb(this[i], i, this)) return this[i]
	}
	return null
};

console.log(arr.customFind((el, i, arr) => el === 'four')); //* 'four'
console.log(arr.customFind((el, i, arr) => i === 3)); //* 'four'

Array.prototype.customFindIndex = function (cb) {
	for (let i = 0; i < this.length; i++) {
		if (cb(this[i], i, this)) return i
	}
	return null
};

console.log(arr.customFindIndex((el, i, arr) => el === 'four')); //* 3
console.log(arr.customFindIndex((el, i, arr) => i === 3)); //* 3
```
##### `arr.filter()` - Возвращает новый массив с элементами удовлетворяющими условию
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

console.log(arr.filter(el => el.length === 3)); //* [ 'one', 'two', 'six' ]
```
##### `arr.customFilter()`
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

Array.prototype.customFilter = function (cb) {
	let result = [];
	for (let i = 0; i < this.length; i++) {
		if (cb(this[i], i, this)) result.push(this[i]);
	}
	return result
};

console.log(arr.customFilter(el => el.length === 3)); //* [ 'one', 'two', 'six' ]
```
##### `arr.reduce()` - Замыкает вызов каждого элемента
```javascript
const arr = [10, 20, 30, 40, 50];

console.log(arr.reduce((total, el, i) => {
	return { ...total, [`#${i}`]: el }
}, { you: 'pidor' })); //* { you: 'pidor', '#0': 10, '#1': 20, '#2': 30, '#3': 40, '#4': 50 }
```
##### `arr.customReduce()`
```javascript
const arr = [10, 20, 30, 40, 50];

Array.prototype.customReduce = function (cb, init) {
	let reducer = init;
	for (let i = 0; i < this.length; i++) {
		reducer = cb(reducer, this[i], i, this);
	}
	return reducer
};

console.log(arr.customReduce((total, el, i) => {
	return { ...total, [`#${i}`]: el }
}, { you: 'pidor' })); //* { you: 'pidor', '#0': 10, '#1': 20, '#2': 30, '#3': 40, '#4': 50 }
```
------------
##### `arr.at()` - Возвращает элем под определенным индексом
```javascript
let arr = ['one', 'two', 'three', 'four', 'five', 'six']

console.log(arr.at(1)); //* 'two'
console.log(arr.at(-1)); //* 'six'
```
##### `arr.indexOf()/arr.lastIndexOf()` - Возвращает индекс искомого элемента
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six', 'three', 'three', 'three'];

console.log(arr.indexOf('five', 2)); //* 4; второй арг указывает с какого индекса начать поиск
console.log(arr.lastIndexOf('three', 2)); //* 2; возвращает индекс последнего щначения, не считая 3 последних элем
```
##### `arr.slice()` - ИММУТАБЕЛЬНЫЙ! Возвращает обрезанный массив
```javascript
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

console.log(arr.slice(2, 5)); //* [ 3, 4, 5 ]
console.log(arr.slice(7)); //* [ 8, 9 ]; от 7 индекса и до конца
console.log(arr); //* [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
##### `arr.fill()` - МУТАБЕЛЬНЫЙ! Заменяет элементы массива на заданный в параметре
```javascript
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

console.log(arr.fill(0)); //* [0,0,0,0,0,0,0,0,0]
console.log(arr); //* [0,0,0,0,0,0,0,0,0]
console.log(arr.fill(1, 3, 7)); //* [0,0,0,1,1,1,1,0,0]; заменяет элементы массива от 3 индекса до 7
```
##### `arr.join()` - Преобразует массив в строку по разделителю
```javascript
const arr = ['one', 'two', 'three'];

console.log(arr.join(' ')); //* 'one two three'
console.log(arr.join('*')); //* 'one*two*three'
console.log(arr.join('')); //* 'onetwothree'
```
##### `arr.reverse()` - МУТАБЕЛЬНЫЙ!
```javascript
const arr = ['one', 'two', 'three'];

console.log(arr.reverse()); //* ['three', 'two', 'one']
console.log(arr); //* ['three', 'two', 'one']
```
##### `arr.sort()` - МУТАБЕЛЬНЫЙ!
```javascript
const arr = ['e', 555, 'd', 44, 'c', 3, 'b', 22, 'a', 111]

console.log(arr.sort()); //* [111, 22, 3, 44, 555, 'a', 'b', 'c', 'd', 'e']; сортировка по алфавиту
console.log(arr.sort((a, b) => a - b)); //* [3, 22, 44, 111, 555, 'a', 'b', 'c', 'd', 'e']; по возрастанию
console.log(arr.sort((a, b) => b - a)); //* [555, 111, 44, 22, 3, 'a', 'b', 'c', 'd', 'e']; по убыванию
console.log(arr); //* [555, 111, 44, 22, 3, 'a', 'b', 'c', 'd', 'e']
```
##### `arr.splice()` - МУТАБЕЛЬНЫЙ! Вырезает элементы из массива и заменяет их новыми
```javascript
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

console.log(
	arr.splice(4, 3, 'a', 'b')
); //* [ 5, 6, 7 ]; возвращ массив вырезанных элементов: 1арг - индекс с которого начать вырезать элементы, 2арг - кол-во элемнтов, 3арг - на что заменить вырезанные элементы
console.log(arr); //* [1, 2, 3, 4, 'a', 'b', 8, 9]; мутирует массив
```
##### `arr.includes()` - Возвращает true если найдено совпадение
```javascript
const arr = ['one', 'two', 'three', 'four', 'five', 'six'];

console.log(arr.includes('four')); //* true
console.log(arr.includes('four', 4)); //* false; 2 парам - индекс с которого начинается поиск
```
##### `arr.flat()` - Разворачивает массив массивов, параметр указывает уровень вложенности до которого нужно разворачивать массив
```javascript
const arr = [['a', 11], ['b', 22], [['c', 33], ['d', 44], [['e', 55], ['f', 66]]]];

console.log(arr.flat()); //* [ 'a', 11, 'b', 22, 'c', 33, 'd', 44, [ 'e', 55 ], [ 'f', 66 ] ]
console.log(arr.flat(2)); //* [ 'a', 11, 'b', 22, 'c', 33, 'd', 44, [ 'e', 55 ], [ 'f', 66 ] ]
console.log(arr.flat(Infinity)); //* [ 'a', 11, 'b', 22, 'c', 33, 'd', 44, 'e', 55, 'f', 66 ]
```
## Методы объектов
##### `Object.assign()` - Объединяет объекты
```javascript
const obj1 = { name: 'abame', age: 69, color: 'black' };
const obj2 = { job: 'ебаный козел', color: 'черножепый' };
const sumObj = {};

console.log(
	Object.assign(sumObj, obj1, obj2)
); //* { name: 'abame', age: 69, job: 'ебаный козел', color: 'черножепый' }; возвращает новый и изменяет суммарный объект (sumObj)
console.log(sumObj); //* { name: 'abame', age: 69, job: 'ебаный козел', color: 'черножопый' }; sumObj - суммарный объект
```
##### `Object.entries()` - Превращает объект в массив с парами `[['key', 'value']]`
```javascript
const president = { name: 'abame', age: 69, color: 'black' };

console.log(Object.entries(president)); //* [ [ 'name', 'abame' ], [ 'age', 69 ], [ 'color', 'black' ] ]
```
##### `Object.fromEntries()` - Превращает массив с парами в объект
```javascript
const arr = [['name', 'abame'], ['age', 69], ['color', 'black']];

console.log(Object.fromEntries(arr)); //* { name: 'abame', age: 69, color: 'black' }
```
##### `Object.is()` - Еще один способ сравнения (похоже только для NaN)
```javascript
console.log(Object.is(NaN === NaN)); //* false; при строгом равенстве NaN не равет NaN
console.log(Object.is(NaN, NaN)); //* true; при Object.is() NaN равен NaN
```
##### `Object.keys()/Object.values()` - Превращает ключи/значения объекста в массив ключей\значений
```javascript
const president = { name: 'abame', age: 69, color: 'black' };

console.log(Object.keys(president)); //* [ 'name', 'age', 'color' ]
console.log(Object.values(president)); //* [ 'abame', 69, 'black' ]
```
------------
##### `func.bind()/func.call()/func.apply()` - Позволяют изменить контекст вызова (this)
```javascript
const president1 = {
	name: 'abame',
	age: 69,
	color: 'black',
	getName(greetWord) {
		console.log(`${greetWord} i'm ${this.name}`);
	}
};

const president2 = {
	name: 'puten',
	age: 420,
	color: 'yellow',
};

president1.getName.call(president2, 'hello'); //* 'hello i'm puten'
president1.getName.apply(president2, ['greetings']); //* 'greetings i'm puten'
president1.getName.bind(president2)('hi'); //* 'hi i'm puten'
```
------------
##### `Number.isInteger()/Number.isFinite()/isFinite()` - Числовые проверки
```javascript
console.log(Number.isInteger(69)); //* true; проверка на целое число
console.log(Number.isInteger(4.20)); //* false

console.log(Number.isFinite(123)); //* true; проверка на число
console.log(Number.isFinite('123')); //* false; не преобразует переданное значение
console.log(isFinite('123')); //* true; менее надежный вариант с преобразованием
```
##### `parseInt()/parseFloar()`
```javascript
console.log(parseInt('420abc')); //* 123; преобраует значение в число, удаляет все символы справа
console.log(parseInt('4.20abc')); //* 4; преобразует только ЦЕЛОЕ число

console.log(parseFloat('4.20abc')); //* 4.20; преобразует число с плавоющей точкой
```
##### `num.toFixed()` - Округляет число
```javascript
// console.log(69.toFixed()); //*! Ошибка!; нежно добавить точку, либо взять число в скобки

console.log(69..toFixed()); //* 69;
console.log((69).toFixed()); //* 69
console.log((69.69).toFixed()); //* 70
console.log((69.6969).toFixed(2)); //* 69.70; округляет две цифры после запятой
```
------------
##### `Math` - Методы объекта
```javascript
console.log(Math.ceil(69.1)); //* 70; округляет дробное число к большему
console.log(Math.floor(69.9)); //* 69; округляет дробное число к меньшему
console.log(Math.round(69.5)); //* 70; округляет дробное число к ближайшему целому числу
console.log(Math.trunc(69.69)); //* 69; удаляет дробную часть

console.log(Math.min(1, 2, 3, 4, 5)); //* 1; возвращает наименьшее число
console.log(Math.max(1, 2, 3, 4, 5)); //* 5; возвращает наибольшее число

console.log(Math.random()); //* 0-1; возвращает случайное число от 0 до 1
```