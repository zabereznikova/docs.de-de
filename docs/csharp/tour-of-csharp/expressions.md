---
title: C#-Ausdrücke – Überblick über C#
description: Ausdrücke, Operanden und Operatoren sind Bausteine der Sprache C#.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 682f98d51bf4eb3c1641297972afb86956e06d3e
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212091"
---
# <a name="expressions"></a>Ausdrücke

*Ausdrücke* bestehen aus *Operanden* und *Operatoren*. Die Operatoren eines Ausdrucks geben an, welche Operationen auf die Operanden angewendet werden. Beispiele für Operatoren sind `+`, `-`, `*`, `/` und `new`. Beispiele für Operanden sind Literale, Felder, lokale Variablen und Ausdrücke.

Wenn ein Ausdruck mehrere Operatoren enthält, bestimmt die *Rangfolge* der Operatoren die Reihenfolge, in der die einzelnen Operatoren ausgewertet werden. Der Ausdruck `x + y * z` wird z.B. als `x + (y * z)` ausgewertet, da der `*`-Operator Vorrang vor dem `+`-Operator hat.

Tritt ein Operand zwischen zwei Operatoren mit gleicher Rangfolge auf, steuert die *Assoziativität* der Operatoren die Reihenfolge, in der die Vorgänge ausgeführt werden:

*   Mit Ausnahme der Zuweisungsoperatoren sind alle binären Operatoren *linksassoziativ*, was bedeutet, dass Vorgänge von links nach rechts ausgeführt werden. `x + y + z` wird beispielsweise als `(x + y) + z` ausgewertet.
*   Die Zuweisungsoperatoren und der bedingte Operator (`?:`) sind *rechtsassoziativ*, d.h., die Operationen werden von rechts nach links ausgeführt. `x = y = z` wird beispielsweise als `x = (y = z)` ausgewertet.

Rangfolge und Assoziativität können mit Klammern gesteuert werden. In `x + y * z` wird beispielsweise zuerst `y` mit `z` multipliziert und dann das Ergebnis zu `x` addiert, aber in `(x + y) * z` werden zunächst `x` und `y` addiert, und dann wird das Ergebnis mit `z` multipliziert.

Die meisten Operatoren können *überladen* werden. Das Überladen von Operatoren ermöglicht die Angabe benutzerdefinierter Operatorimplementierungen für Vorgänge, in denen einer der Operanden oder beide einer benutzerdefinierten Klasse oder einem benutzerdefinierten Strukturtyp angehören.

In der folgenden Übersicht der C#-Operatoren werden die Operatorkategorien gemäß der Rangfolge von oben nach unten aufgelistet. Operatoren der gleichen Kategorie haben den gleichen Rang. Jede Kategorie enthält eine Liste von Ausdrücken mit der Beschreibung des jeweiligen Ausdruckstyps.

* Primär
    - `x.m`: Memberzugriff
    - `x(...)`: Methoden- und Delegataufruf
    - `x[...]`: Array- und Indexerzugriff
    - `x++`: Postinkrement
    - `x--`: Postdekrement
    - `new T(...)`: Objekt- und Delegaterstellung
    - `new T(...){...}`: Objekterstellung mit Initialisierer
    - `new {...}`:  Anonymer Objektinitialisierer
    - `new T[...]`: Arrayerstellung
    - `typeof(T)`: Abrufen von <xref:System.Type>-Objekt für `T`
    - `checked(x)`: Auswerten von Ausdrücken in geprüftem Kontext
    - `unchecked(x)`: Auswerten von Ausdrücken in nicht geprüftem Kontext
    - `default(T)`: Abrufen des Standardwerts vom Typ `T`
    - `delegate {...}`: Anonyme Funktion (anonyme Methode)
* Unär
    - `+x`: Identität
    - `-x`: Negation
    - `!x`: Logische Negation
    - `~x`: Bitweise Negation
    - `++x`: Präinkrement
    - `--x`: Prädekrement
    - `(T)x`: Explizites Konvertieren von `x` in den Typ `T`
    - `await x`: Asynchrones Warten auf den Abschluss von `x`
* Multiplikativ
    - `x * y`: Multiplikation
    - `x / y`: Division
    - `x % y`: Rest
* Additiv
    - `x + y`: Addition, Zeichenfolgenverkettung, Delegatkombination
    - `x – y`: Subtraktion, Delegatentfernung
* Shift
    - `x << y`: Linksverschiebung
    - `x >> y`: Rechtsverschiebung
* Relational und Typtest
    - `x < y`: Kleiner als 
    - `x > y`: Größer als
    - `x <= y`: Kleiner oder gleich 
    - `x >= y`: Größer oder gleich
    - `x is T`: `true` zurückgeben, wenn `x` ein `T` ist, andernfalls `false`
    - `x as T`: `x` als `T` typisiert zurückgeben, oder `null`, wenn `x` kein `T` ist
* Gleichheit
    - `x == y`: Gleich
    - `x != y`: Ungleich
* Logisches AND
    - `x & y`: Ganzzahliges bitweises AND, boolesches logisches AND
* Logisches XOR
    - `x ^ y`: Ganzzahliges bitweises XOR, boolesches logisches XOR
* Logisches OR
    - `x | y`: Ganzzahliges bitweises OR, boolesches logisches OR
* Bedingtes AND
    - `x && y`: Wertet `y` nur aus, wenn `x` nicht `false` ist
* Bedingtes OR
    - `x || y`: Wertet `y` nur aus, wenn `x` nicht `true` ist
* NULL-Sammeloperator
    - `x ?? y`: Wird zu `y` ausgewertet, wenn `x` NULL ist, andernfalls zu `x`
* Bedingt
    - `x ? y : z`: Wertet `y` aus, wenn `x` `true` ist, `z`, wenn `x` `false` ist
* Zuweisung oder anonyme Funktion
    - `x = y`: Zuweisung
    - `x op= y`: Zusammengesetzte Zuweisung; unterstützte Operatoren sind
        - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
    - `(T x) => y`: Anonyme Funktion (Lambda-Ausdruck)

> [!div class="step-by-step"]
> [Zurück](types-and-variables.md)
> [Weiter](statements.md)