#Код стайл для языка Java
- - -
##1 Отступы (identation) и пропуски строк
- - -
- Отступ от начала предыдущей строки равняется четырём пробелам.
- Две пустых линии используются, чтобы разделять объявления классов и интерфейсов.
- Одна пустая линия должна разделять:
 - Методы
 - Локальные переменные в методе и первое выражение
 - Блок или отдельную строку комментариев
 - Логически разделенные части в методе, чтобы улучшить читабельнос

##2 Расстановка скобок

Скобка переносится на новую строку при определении пространств имен (namespaces) и классов (classes). В остальных случаях скобка остается на той же строке.
```javascript
class MyClass
	{
	int foo() {
		makeStuff();
		makeAnotherStuff();
        }
    }
```

##3 Форматирование строк, длина операторов/выражений
- Максимальная длина строки равна 120 символам. Если аргументы метода не помещаются на одной строке, их следует разбивать на несколько строк; новую строку следует начинать на одну позицию правее открывающей скобки списка аргументов.

```java
// Правильно
int lotsOfArgs(int anInteger, long aLong, short aShort,
               double aDouble, float aFloat, String aString);
// Неправильно
int lotsOfArgs(int anInteger, long aLong, short aShort, double aDouble, float aFloat, String aString);
```

- В сложных выражениях размещайте каждое условие на отдельной строке.

```java
// Правильно
if ((('0' <= inChar) && (inChar <= '9'))
 || (('а' <= inChar) && (inChar <= 'z'))
 || (('A' <= inСhar) && (inСhar <= 'Z'))) {
    /* .... */
}

// Неправильно
if ((('0' <= inChar) && (inChar <= '9')) || (( 'а' <= inChar) && (inChar <= 'z')) || (( 'A' <=  inСhar) && (inСhar <= 'Z'))) {
    /* .... */
}
```
- Всегда располагайте один оператор на строке.

```java
// Правильно
a = b + 1;
c++;

// Неправильно
a = b + 1; c++;
```
##3 Операторы if/else, do, while, for
- Тело операторов if, else if, do, while, for необходимо всегда выделять фигурными скобками, а перед каждым оператором ставить отступ – четыре пробела.

```java
// Правильно
if (x == y) {
    makeSomeStuff();
    makeSomeOtherStuff(); 
} else if (x > y) {
    singleLine();
} else {
    doThis();
    doThat();
}

for (int i = 0; i < 10; i++) {
    statements; 
}

// Неправильно
if (x == y) {
makeSomeStuff();
makeSomeOtherStuff(); 
} else if (x > y)
    singleLine();
else
{
    doThis();
    doThat();
}

for (int i = 0; i < 10; i++) statement;

```
- Слово while не переносится на новую строку

```java
do {
    doThis();
    doThat();
} while (condition);

```
- Форма тернарного оператора:

```java
alpha = (aLongBooleanExpression) ? beta : gamma;

alpha = (aLongBooleanExpression) ? beta
                                 : gamma;

alpha = (aLongBooleanExpression)
        ? beta
        : gamma;

```
##4 Условия множественного выбора switch

- Операторы case должны находиться в той же колонке, что и оператор switch.
- Каждый случай должен заканчиваться оператором break (или return) или комментарием, чтобы показать, что далее следует другой случай

```java
switch (myEnum) {
case Value1:
    doSomething();
    break;
case Value2:
case Value3:
    doSomethingElse();
    // fall through
default:
    defaultHandling();
    break;
}
```
##5 Обработка исключений
Выражение типа try-catch должно иметь следующий вид:

```java
try {
    statements;
} catch (ExceptionClass e) {
    statements;
} finally {
    doStuff();
}
```
##6 Операции

- Необходимо вставлять пробел между операциями присваивания, логическими и арифметическими операциями.

```java
// Правильно
if (i == 0) {
    /* ... */;
}
a += 3;
a = b + c;

// Неправильно
if (i = = 0) {
    /* ... */;
}
a+ =3;
a=b+c;
```

- Не следует оставлять пробел после унарной операции.

```java
if (!flag) {
    break;
}

```
##7 Выбор имен

- Все названия должны быть на английском языке.
- Названия пакетов должны быть написаны строчными буквами
```java
mypackage, com.company.application.ui
```
- Названия классов должны быть существительными и написаны в PascalCase (название переменной пишется слитно, каждое новое слово начинается с заглавной буквы).
```java
class Raster;
class ImageSprite;
```
- Названия интерфейсов должны быть в PascalCase.
```java
interface RasterDelegate;
interface Storing;
```
- Названия методов должны начинаться с глагола и быть написаны в camelCase (название пишется слитно и начинается со строчной буквы, каждое новое слово начинается с заглавной буквы).
```java
initialize();
cookApplePie();
```
- Имена переменных должны быть в camelCase. Старайтесь избегать однобуквенных имен, за исключением временных «ненужных» переменных (например для счётчиков удобно использовать название i).
```java
float myWidth;
int i;
```
- Имена констант должны быть написаны заглавными буквами, слова разделяются ни
жним подчеркиванием.
```java
int MIN_WIDTH = 4;
int MAX_WIDTH = 999;
int GET_THE_CPU = 1;
```
- Элементы перечисляемого типа должны быть написаны заглавными буквами, слова разделяются нижним подчеркиванием.
```java
enum Season {
    WINTER, SPRING, SUMMER, AUTUMN
}
```
- Следует избегать аббревиатур, кроме случаев, где аббревиатура более известна, чем полное название. Аббревиатуры должны быть в camelCase.
```java
exportHtmlSource();
```
- В названиях переменных и методах типа boolean следует использовать префикс is или has.
```java
isSet, isVisible, isFinished(), isOpen(); hasThis, hasThat
```
- Следует использовать compute в методах, где подсчитывается какое-то значение, find – в методах, где что-то ищется.
```java
valueSet.computeAverage();
matrix.computeInverse()
vertex.findNearestVertex();
matrix.findSmallestElement();
```
- Используйте множественное число для коллекций объектов.
```java
Collection<Point> points;
int[] values;
```
- Избегайте отрицательных префиксов для переменных и методов типа `boolean`.
```java
// Правильно
bool isError;
bool isFound;
// Неправильно
bool isNoError;
bool isNotFound;
```

##7 Объявление классов и интерфейсов

- Все поля должны объявляться в начале класса.
- Классы и интерфейсы должны объявляться следующим образом:
	- Статические переменные класса в порядке `public, protected, package-private, private`
	- Остальные переменные класса в порядке `public, protected, package-private, private`
	- Конструкторы
	- Методы
- Объявляйте класс как `final` если необходимо исключить наследование данного класса.
```java
final class MyFinalClass {
    /* body */
}
```

##8 Объявление методов
- Модификаторы метода должны идти в следующем порядке:

	`<access> static abstract synchronized transient final native.`
```java
// Правильно
public static double square(double a);
// Неправильно
static public double square(double a);
```
- Объявляйте метод, переменную или аргумент метода как `final`, если он(-а) не должен(-на) подвергаться изменениям.
```java
public final int doStuff(final int i) {
    final int myFinalVar = i * 10;
    /* body */
}
```

##9 Объявление полей

- Приведение типов следует писать в явном виде.

```java
// Правильно
floatValue = (int) intValue;
// Неправильно
floatValue = intValue;
```

- Массивы следует объявлять скобками рядом с типом.
```java
// Правильно
double[] coeffs;
int[] points;
// Неправильно
double coeffs[];
int points[];
```

##10 Комментирование
- Все комментарии пишутся на английском языке.
- Комментарии описывают, что делает код, а не как.
- Не стоит писать комментарии ради комментариев.
- Блоки и отдельные строки комментариев должны быть сдвинуты так же, как и - окружающий их код.
-Можно использовать различные формы записи комментариев.
```java
// single-line comment
/*
 * multi-line
 * comment
 */
/*
 * another
 * multi-line comment */
```
- Используйте комментарии TODO для кода, который является временным, краткосрочным, или хорошим, но не идеальным. Также следует вставлять конкретную дату, к которой проблема должна быть решена, или же конкретное событие.
`// TODO: Change this to use flag instead of constant by Dec 31`
`// TODO: Delete this method after v1.2 release`

##11 JavaDoc
- Каждый класс и public метод должен содержать Javadoc, по крайней мере, с одной фразой, описывающей, что он делает. Фраза должна начинаться с описательного глагола 3-го лица.
```java
/** Returns the correctly rounded positive square root of a double value. */
static double sqrt(double a) {
}
```
```java
/**
 * Constructs a new String by converting the specified array of 
 * bytes using the platform's default character encoding.
 */
public String(byte[] bytes) {
}
```
- Вам не нужно описывать Javadoc для тривиальных `get` и `set` методов, таких как `setFoo()`, если ваш Javadoc говорит только `/* Sets Foo */`.
- Если при использовании метода необходимо выполнять какие-либо ограничения, или если действие метода имеет важный эффект в другом месте программы, обязательно опишите это в документации.

##12 Дополнительно
- Не пишите слишком длинных методов.
- Метод должен делать ровно то, что написано в его названии. Если метод делает - что-либо еще, разделите его на несколько методов.
- Локальные переменные: ограничивайте область видимости.
- Следует избегать использования «магических» чисел в коде, любые числа кроме 0 и 1 должны быть записаны в константы.
```java
// Правильно
private static final int TEAM_SIZE = 11;
```
`...`
```java
Player[] players = new Player[TEAM_SIZE];
// Неправильно
Player[] players = new Player[11];
Следует использовать аннотацию @Override, если метод переопределен.
@Override
public void overrideMe() {
   doSomething();
}
```
