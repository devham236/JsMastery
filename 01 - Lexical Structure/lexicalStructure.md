# Lexikalische Struktur

- Bestimmt, wie eine Programmiersprache geschrieben werden muss.
- Wie Variablennamen auszusehen haben, welche Zeichen ein Kommentar einleiten oder wie man Programmanweisungen trennen sollte.

## Kommentare

- Ermöglichen es dir freie Bemerkungen/Tipps/Erklärungen usw. in deinen Code zu integrieren ohne diesen zu unterbrechen oder in irgendeine Art und Weise zu beeinflussen
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
