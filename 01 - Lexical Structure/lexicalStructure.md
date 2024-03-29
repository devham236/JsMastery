# Lexical Structure

1. **Comments**
2. **Literals**
3. **Identifier**
4. **Reserved Words/Keywords**
5. **Unicode**
6. **Optional Semicolon**

- Die lexikalische Struktur bestimmt, wie eine Programmiersprache geschrieben werden muss.
- Wie Variablennamen auszusehen haben, welche Zeichen ein Kommentar einleiten oder wie man Programmanweisungen trennen sollte.

## 1. Comments

- Ermöglichen es dir freie Bemerkungen/Tipps/Erklärungen usw. in deinen Code zu integrieren ohne diesen zu unterbrechen oder in irgendeiner Art und Weise zu beeinflussen
- JavaScript interpretiert folgende Zeilen als Kommentar und ignoriert diese:

```js
// Single line comment

/* Also single line comment */

/*
 *
 * Multi line comment
 *
 */

/* Also a comment */ // and another

/* Nesting /*doesn't work*/ */
```

- Kommentare können beliebig lang sein, können aber nicht "genested" werden.

## 2. Literals

- Ein Literal ist ein alleinstehender Wert
- Zum Beispiel:

```js
12; // Die number zwölf
1.2; // Oder die number Eins komma zwei
("hello"); // Ein Text string
true; // Ein boolean Wert
null; // Oder die Abwesenheit eines objects
```

- Also einfach alle Datentypen, ohne Zuweisung einer Variable, sind Literale

## 3. Indentifier

- Sind Namen von variables, functions, methods, events, properties, objects, classes usw.
- Ein Identifier muss mit einem underscore **(\_)**, einem dollar sign **($)** oder mit einem Buchstaben beginnen.
- Darf nicht mit einer Zahl beginnen, damit JavaScript numbers und identifiers unterscheiden kann.
- Folgende Identifier sind in Ordnung:

```js
i
my_variable_name
v13
_dummy
$str
3variable       //Gibt einen Syntax error wieder
```

## 4. Reserved Words/Keywords

- Manche Identifier oder Namen sind von JavaScript reserviert
- Diese kannst du also nicht als deine Identifier benutzen
- Folgende sind einige von JavaScript reservierten Keywords, die einen Sytax error wiedergeben wenn man diese als Identifier benutzt:

```js
async   else
await   if
break   import
case    null
class   new
```

- Es gibt noch viel mehr solcher reservierter Keywords, und sogar einige die man unter bestimmten Umständen benutzen darf.
- In der Regel sollte man aber trotzdem verhindern diese als Identifier zu benutzen.

## 5. Unicode

- Unicode ist ein extrem breiter und vielfältiger Charaktersatz der fast alle Zeichen und Symbole von sehr vielen Sprachen enthält.
- JavaScript benutzt Unicode um mit Texten umzugehen.
- Du kannst Umlaute, Buchstaben und andere Sprachenspezifische Charaktere als Identifier verwenden

```js
const äöü = "deutsche Umlaute";
const âéç = "französische Akzente";
```

- Beide Variablen oben, können jetzt beliebig in allen JavaScript Programmen verwendet werden.

## 5.1 Unicode Escape Sequences

- Manche Software oder Hardware kann nicht mit dem gesamten Unicode Charaktersatz umgehen
- Dafür definiert JavaScript "Escape Sequences" mit denen du Unicode character (z.b deutsche Umlaute) mithilfe von ASCII character schreiben kannst.
- ASCII (American Standard Code for Information Interchange) character sind standardisierte "codes" für die Englische Sprache.
- Das bedeutet alle Buchstaben von a-z (lowercase und uppercase), alle Zahlen von 0-9 und alle Zeichen die man so auf fast allen Tastaturen findet (?, !, %...)
- Diese "Escape Sequences" beginnen mit "/u", gefolgt von vier Hexcodes (also entweder zahlen von 0-9 oder buchstaben von a-z) oder gefolgt von 1-6 hexcodes innerhalb eines geschweiften klammerpaars {}.
- Beispiele:

```js
let café = 1
caf/u00e9   // Unicode escape für é
caf/u{E9}   // andere Form von Unicode escape
```

- Vor der Version ES6, konnte man nur die Form mit den 4 Hexcodes für Unicode Escape Sequences verwenden
- Mit ES6 konnte man dann geschweifte Klammern verwenden, dadurch wurde das erstellen von Unicode Escape Sequences für Emojis deutlich vereinfacht.

## 5.2 Unicode Normalization

- Unicode kann zum Beispiel "é", auf zwei verschiedene Art und Weisen codieren (encoding).
- Entweder mit den Hexcode wie oben zu sehen oder in dem aus "é" ein normales "e" gemacht wird und dann ein ein weiterer Zahlencode (ein acute accent combining mark) hinten rangehängt wird
- zum Beispiel:

```js
const café = 1; // Wird so codiert "caf/u{e9}"
const café = 2; // Dieses wird so codiert "cafe/u{301}"
```

- JavaScript sieht diese beiden Variablen als zwei unterschiedliche Variablen an, was zu großer Verwirrung in einem Programm führen kann.
- Deswegen musst du dafür sorgen das dein Editor eine gewisse "Unicode Normalization" durchführt, sodass ein identischer Unicode Charakter nicht auf zwei unterschiedlichen Weisen codiert wird.
- JavaScript geht nämlich davon aus das dein Code, den er liest/interpretiert, schon einer "Normalization" untergangen ist!

## 6. Optional Semicolons

- Ein Semikolon ";" wird verwendet um Statements voneinander zu trennen
- Semikolon werden nicht gebraucht wenn zwei Statements auf zwei verschiedenen Zeilen liegen oder wenn ein closing bracket vorliegt
- Hier sind einige Beispiele um zu verstehen wann Semikolon benötigt werden:

```bash
a = 3;
a = 4;
```

- Hier wird das Semikolon nach dem ersten Statement nicht benötigt.
- Schreibt man die Statements aber nebeneinander, braucht das erste Statement ein Semikolon.

```bash
let a
a
=
3
console.log(a)
```

- JavaScript würde den Code wie folgt interpretieren:

```bash
let a; a = 3; console.log(a);
```

- Hier könnte es zu großer Verwirrung führen wenn die Intention und die Interpretation nicht übereinstimmen:

```bash
let y = x + f
(a+b).toString()
```

- JavaScript denkt das "f" eine function ist der die Parameter "a+b" bekommt und interpretiert wie folgt:

```bash
let y = x + f(a+b).toString()
```
