---
title: C#-Operatoren
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: a342c0aaf6a1b0c9959c9b79e3e3e92134693bf1
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250767"
---
# <a name="c-operators"></a>C#-Operatoren

C# bietet eine Reihe vordefinierter Operatoren, die von den integrierten Typen unterstützt werden. Beispielsweise führen [arithmetische Operatoren](arithmetic-operators.md) arithmetische Vorgänge mit Operanden von integrierten numerischen Typen durch, und [boolesche logische Operatoren](boolean-logical-operators.md) führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden aus.

Ein benutzerdefinierter Typ kann bestimmte Operatoren überladen, um das zugehörige Verhalten für die Operanden dieses Typs zu definieren. Weitere Informationen finden Sie im Artikel zum Schlüsselwort [operator](../keywords/operator.md).

Die folgenden Abschnitte listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge. Die Operatoren in jedem Abschnitt verwenden die gleiche Rangfolgenebene.

## <a name="primary-operators"></a>Primäre Operatoren

Hierbei handelt es sich um die höchsten Rangfolgenoperatoren.

[x.y](member-access-operators.md#member-access-operator-) – Memberzugriff.

[x?.y](member-access-operators.md#null-conditional-operators--and-) – nullbedingter Memberzugriff. Gibt `null` zurück, wenn der linke Operand `null` ist.

[x?[y]](member-access-operators.md#null-conditional-operators--and-) – nullbedingter Arrayelement- oder Typindexerzugriff. Gibt `null` zurück, wenn der linke Operand `null` ist.

[f(x)](member-access-operators.md#invocation-operator-) – Methodenaufruf oder Delegataufruf.

[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – Arrayelement- oder Typindexerzugriff.

[x++](arithmetic-operators.md#increment-operator-) – Postfixinkrement. Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).

[x--](arithmetic-operators.md#decrement-operator---) – Postfixdekrement. Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins kleiner ist (für gewöhnlich wird die Ganzzahl 1 subtrahiert).

[new](../keywords/new-operator.md) – Typinstanziierung.

[typeof](../keywords/typeof.md): Gibt das den Operanden repräsentierende Objekt <xref:System.Type> zurück.

[checked](../keywords/checked.md) – Aktiviert die Überlaufprüfung für Ganzzahloperationen.

[unchecked](../keywords/unchecked.md) – Deaktiviert die Überlaufprüfung für Ganzzahloperationen. Dies ist das Standardverhalten für den Compiler.

[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): erzeugt den Standardwert des Typs T.

[nameof](../keywords/nameof.md) – Ruft den einfachen (nicht qualifizierten) Namen einer Variablen, eines Typs oder eines Members als konstante Zeichenfolge ab.

[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – Deklariert eine Delegatinstanz und gibt sie zurück.

[sizeof](../keywords/sizeof.md) – Gibt die Größe des Typoperanden in Byte zurück.

[stackalloc](../keywords/stackalloc.md) – Belegt einen Speicherblock auf dem Stapel.

[->](pointer-related-operators.md#pointer-member-access-operator--) – Mit Memberzugriff kombinierte Zeigerdereferenzierung

## <a name="unary-operators"></a>Unäre Operatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[+x](addition-operator.md) – Gibt den Wert von x zurück.

[-x](subtraction-operator.md) – Numerische Negation.

[\!x](boolean-logical-operators.md#logical-negation-operator-) – logische Negation.

[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – Bitweises Komplement.

[++x](arithmetic-operators.md#increment-operator-) – Präfixinkrement. Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).

[--x](arithmetic-operators.md#decrement-operator---) – Präfixdekrement. Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins kleiner ist (für gewöhnlich wird die ganze Zahl 1 subtrahiert).

[(T)x](invocation-operator.md) – Typumwandlung.

[await](../keywords/await.md) – Wartet auf `Task`.

[&x](pointer-related-operators.md#address-of-operator-) – Adresse einer Variablen

[*x](pointer-related-operators.md#pointer-indirection-operator-) – Zeigerdereferenzierung

Der [true-Operator](../keywords/true-false-operators.md) gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „true“ hat.

Der [false-Operator](../keywords/true-false-operators.md) gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „false“ hat.

## <a name="multiplicative-operators"></a>Multiplikative Operatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x * y](arithmetic-operators.md#multiplication-operator-) – Multiplikation.

[x / y](arithmetic-operators.md#division-operator-) – Division. Wenn es sich bei den Operanden um Ganzzahlen handelt, ist das Ergebnis eine Ganzzahl, die in Richtung 0 abgeschnitten wird (beispielsweise `-7 / 2 is -3`).

[x % y](arithmetic-operators.md#remainder-operator-) – Restwert. Wenn es sich bei den Operanden um Ganzzahlen handelt, wird dadurch der Rest der Division x durch y zurückgegeben.  Wenn `q = x / y` und `r = x % y`, dann `x = q * y + r`.

## <a name="additive-operators"></a>Additive Operatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x + y](arithmetic-operators.md#addition-operator-) – Addition.

[x – y](arithmetic-operators.md#subtraction-operator--) – Subtraktion.

## <a name="shift-operators"></a>Schiebeoperatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – Verschiebt Bits nach links und füllt sie mit Null auf der rechten Seite auf.

[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – Verschiebt Bits nach rechts. Wenn der linke Operand `int` oder `long` ist, werden die linken Bits mit dem Vorzeichenbit gefüllt. Wenn der linke Operand `uint` oder `ulong` ist, werden die linken Bits mit Null gefüllt.

## <a name="relational-and-type-testing-operators"></a>Relationale und Typtestoperatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x \< y](comparison-operators.md#less-than-operator-) – Kleiner als (wahr, wenn x kleiner als y ist).

[x > y](comparison-operators.md#greater-than-operator-) – Größer als (wahr, wenn x größer als y ist).

[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – Ist kleiner oder gleich.

[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – Ist größer gleich.

[is](../keywords/is.md) – Typkompatibilität. Gibt TRUE zurück, wenn der ausgewertete linke Operand in den im rechten Operanden (ein statischer Typ) angegebenen Typ umgewandelt werden kann.

[as](../keywords/as.md) – Typkonvertierung. Gibt die Umwandlung des linken Operanden zum durch den rechten Operanden (ein statischer Typ) angegebenen Typ zurück, `as` gibt jedoch `null` zurück, wobei `(T)x` eine Auslösung ausgeben würde.

## <a name="equality-operators"></a>Gleichheitsoperatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x == y](equality-operators.md#equality-operator-) – Gleichheit. Standardmäßig wird für Verweistypen, die nicht `string` entsprechen, diese Verweisübereinstimmung (Identitätstest) zurückgeben Typen können `==` jedoch überladen. Wenn Sie also vorhaben, die Identität zu testen, sollten Sie möglichst die `ReferenceEquals`-Methode für `object` verwenden.

[x != y](equality-operators.md#inequality-operator-) – ungleich. Siehe hierzu den Kommentar für `==`. Wenn ein Typ `==` überlädt, muss er `!=` überladen.

## <a name="logical-and-operator"></a>Logischer AND-Operator

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

`x & y` –[logische AND](boolean-logical-operators.md#logical-and-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische AND](bitwise-and-shift-operators.md#logical-and-operator-)-Operationen für die Operanden von integralen Typen.

## <a name="logical-xor-operator"></a>Logischer XOR-Operator

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

`x ^ y` –[logische XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)-Operationen für die Operanden von integralen Typen.

## <a name="logical-or-operator"></a>Logischer OR-Operator (||)

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

`x | y` –[logische OR](boolean-logical-operators.md#logical-or-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische OR](bitwise-and-shift-operators.md#logical-or-operator-)-Operationen für die Operanden von integralen Typen.

## <a name="conditional-and-operator"></a>Bedingter AND-Operator

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logisches AND. Wenn der erste Operand FALSE ist, wertet C# den zweiten Operand nicht aus.

## <a name="conditional-or-operator"></a>Bedingter OR-Operator

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – Logisches OR. Wenn der erste Operand TRUE ist, wertet C# den zweiten Operand nicht aus.

## <a name="null-coalescing-operator"></a>Nullzusammensetzungsoperator

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x ?? y](null-coalescing-operator.md) – Gibt `x` zurück, sofern es Nicht-`null` ist; ansonsten wird `y` zurückgegeben.

## <a name="conditional-operator"></a>Bedingter Operator

Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[t ? x : y](conditional-operator.md): Wenn der Test `t` TRUE ist, wird `x` ausgewertet und zurückgegeben, ansonsten wird `y` ausgewertet und zurückgegeben.

## <a name="assignment-and-lambda-operators"></a>Zuweisungs- und Lambdaoperatoren

Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.

[x = y](assignment-operator.md) – Zuweisung.

[x += y](arithmetic-operators.md#compound-assignment) – Inkrement. Fügen Sie dem Wert `x` den Wert `y` hinzu. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück. Wenn `x` ein [Ereignis](../keywords/event.md) festlegt, muss `y` eine entsprechende Methode sein, die C# als Ereignishandler hinzufügt.

[x -= y](subtraction-assignment-operator.md) – Dekrement. Subtrahieren Sie vom Wert `x` den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück. Wenn `x` ein [Ereignis](../keywords/event.md) festlegt, muss `y` eine entsprechende Methode sein, die C# als Ereignishandler entfernt.

[x *= y](arithmetic-operators.md#compound-assignment) – Multiplikationszuweisung. Multiplizieren Sie den Wert `y` mit dem Wert `x`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[x /= y](arithmetic-operators.md#compound-assignment) – Divisionszuweisung. Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[x %= y](arithmetic-operators.md#compound-assignment) – Restwertzuweisung. Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie den Rest in `x`, und geben Sie den neuen Wert zurück.

[x &= y](boolean-logical-operators.md#compound-assignment) – AND-Zuweisung. Führen Sie eine AND-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR-Zuweisung. Führen Sie eine OR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR-Zuweisung. Führen Sie eine XOR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – Linksschiebezuweisung. Verschieben Sie den Wert von `x` nach links um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – Rechtsschiebezuweisung. Verschieben Sie den Wert von `x` nach rechts um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.

[=>](lambda-operator.md) – Lambdadeklaration.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#](../../index.md)
- [Überladbare Operatoren](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [C#-Schlüsselwörter](../keywords/index.md)
