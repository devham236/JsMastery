# Lexikalische Struktur

- Bestimmt, wie eine Programmiersprache geschrieben werden muss.
- Wie Variablennamen auszusehen haben, welche Zeichen ein Kommentar einleiten oder wie man Programmanweisungen trennen sollte.

## Kommentare

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

## Literale

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

## Indentifier

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
