---
title: C#-Operatoren
ms.date: 04/04/2018
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
ms.openlocfilehash: 30e4942934e5d65b214d24a0948f70169d625485
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507248"
---
# <a name="c-operators"></a>C#-Operatoren
C# bietet viele Operatoren, bei denen es sich um Symbole handelt, die angeben, welche Operationen (Mathematik, Indizierung, Funktionsaufruf usw.) in einem Ausdruck ausgeführt werden. Sie können viele Operatoren [überladen](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md), um ihre Bedeutung zu ändern, wenn sie auf einen benutzerdefinierten Typ angewendet werden.  
  
 Operationen mit Ganzzahltypen (wie `==`, `!=`, `<`, `>`, `&`, `|`) sind grundsätzlich auch für Aufzählungstypen (`enum`) zulässig.  
  
 Die folgenden Abschnitte listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge. Die Operatoren in jedem Abschnitt verwenden die gleiche Rangfolgenebene.  
 
## <a name="primary-operators"></a>Primäre Operatoren  
 Hierbei handelt es sich um die höchsten Rangfolgenoperatoren.
  
 [x.y](../../../csharp/language-reference/operators/member-access-operator.md) – Memberzugriff.  
  
 [x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) – nullbedingter Memberzugriff. Gibt `null` zurück, wenn der linke Operand `null` ist.  
 
 [x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) – nullbedingter Indexzugriff. Gibt `null` zurück, wenn der linke Operand `null` ist.
 
 [f(x)](../../../csharp/language-reference/operators/invocation-operator.md) – Funktionsaufruf.  
  
 [a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) – Aggregatobjektindizierung.  
   
 [x++](../../../csharp/language-reference/operators/increment-operator.md) – Postfixinkrement. Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).  
  
 [x--](../../../csharp/language-reference/operators/decrement-operator.md) – Postfixdekrement. Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins kleiner ist (für gewöhnlich wird die Ganzzahl 1 subtrahiert).  
  
 [new](../../../csharp/language-reference/keywords/new-operator.md) – Typinstanziierung.  
  
 [typeof](../../../csharp/language-reference/keywords/typeof.md): Gibt das den Operanden repräsentierende Objekt <xref:System.Type> zurück.  
  
 [checked](../../../csharp/language-reference/keywords/checked.md) – Aktiviert die Überlaufprüfung für Ganzzahloperationen.  
  
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) – Deaktiviert die Überlaufprüfung für Ganzzahloperationen. Dies ist das Standardverhalten für den Compiler.  
  
 [default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md): erzeugt den Standardwert des Typs T.  
  
 [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) – Deklariert eine Delegatinstanz und gibt sie zurück.  
  
 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) – Gibt die Größe des Typoperanden in Byte zurück.  
  
 [->](../../../csharp/language-reference/operators/dereference-operator.md) – Mit Memberzugriff kombinierte Zeigerdereferenzierung.  
  
## <a name="unary-operators"></a>Unäre Operatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [+x](../../../csharp/language-reference/operators/addition-operator.md) – Gibt den Wert von x zurück.  
  
 [-x](../../../csharp/language-reference/operators/subtraction-operator.md) – Numerische Negation.  
  
 [\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) – logische Negation.  
  
 [~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) – Bitweises Komplement.  
  
 [++x](../../../csharp/language-reference/operators/increment-operator.md) – Präfixinkrement. Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).  
  
 [--x](../../../csharp/language-reference/operators/decrement-operator.md) – Präfixdekrement. Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins kleiner ist (für gewöhnlich wird die ganze Zahl 1 subtrahiert).  
  
 [(T)x](../../../csharp/language-reference/operators/invocation-operator.md) – Typumwandlung.  
  
 [await](../../../csharp/language-reference/keywords/await.md) – Wartet auf `Task`.  
  
 [&x](../../../csharp/language-reference/operators/and-operator.md) – Adresse von.  
  
 [*x](../../../csharp/language-reference/operators/multiplication-operator.md) – Dereferenzierung.  
  
## <a name="multiplicative-operators"></a>Multiplikative Operatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x * y](../../../csharp/language-reference/operators/multiplication-operator.md) – Multiplikation.  
  
 [x / y](../../../csharp/language-reference/operators/division-operator.md) – Division. Wenn es sich bei den Operanden um Ganzzahlen handelt, ist das Ergebnis eine Ganzzahl, die in Richtung 0 abgeschnitten wird (beispielsweise `-7 / 2 is -3`).  
  
 [x % y](../../../csharp/language-reference/operators/remainder-operator.md) – Restwert. Wenn es sich bei den Operanden um Ganzzahlen handelt, wird dadurch der Rest der Division x durch y zurückgegeben.  Wenn `q = x / y` und `r = x % y`, dann `x = q * y + r`.  
  
## <a name="additive-operators"></a>Additive Operatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x + y](../../../csharp/language-reference/operators/addition-operator.md) – Addition.  
  
 [x – y](../../../csharp/language-reference/operators/subtraction-operator.md) – Subtraktion.  
  
## <a name="shift-operators"></a>Schiebeoperatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md) – Verschiebt Bits nach links und füllt sie mit Null auf der rechten Seite auf.  
  
 [x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) – Verschiebt Bits nach rechts. Wenn der linke Operand `int` oder `long` ist, werden die linken Bits mit dem Vorzeichenbit gefüllt. Wenn der linke Operand `uint` oder `ulong` ist, werden die linken Bits mit Null gefüllt.  
  
## <a name="relational-and-type-testing-operators"></a>Relationale und Typtestoperatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x \< y](../../../csharp/language-reference/operators/less-than-operator.md) – Kleiner als (wahr, wenn x kleiner als y ist).  
  
 [x > y](../../../csharp/language-reference/operators/greater-than-operator.md) – Größer als (wahr, wenn x größer als y ist).  
  
 [x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – Ist kleiner oder gleich.  
  
 [x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – Ist größer gleich.  
  
 [is](../../../csharp/language-reference/keywords/is.md) – Typkompatibilität. Gibt TRUE zurück, wenn der ausgewertete linke Operand in den im rechten Operanden (ein statischer Typ) angegebenen Typ umgewandelt werden kann.  
  
 [as](../../../csharp/language-reference/keywords/as.md) – Typkonvertierung. Gibt die Umwandlung des linken Operanden zum durch den rechten Operanden (ein statischer Typ) angegebenen Typ zurück, `as` gibt jedoch `null` zurück, wobei `(T)x` eine Auslösung ausgeben würde.  
  
## <a name="equality-operators"></a>Gleichheitsoperatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) – Gleichheit. Standardmäßig wird für Verweistypen, die nicht `string` entsprechen, diese Verweisübereinstimmung (Identitätstest) zurückgeben Typen können `==` jedoch überladen. Wenn Sie also vorhaben, die Identität zu testen, sollten Sie möglichst die `ReferenceEquals`-Methode für `object` verwenden.  
  
 [x != y](../../../csharp/language-reference/operators/not-equal-operator.md) – ungleich. Siehe hierzu den Kommentar für `==`. Wenn ein Typ `==` überlädt, muss er `!=` überladen.  
  
## <a name="logical-and-operator"></a>Logischer AND-Operator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x & y](../../../csharp/language-reference/operators/and-operator.md) – logisches oder bitweises AND. Sie können dies im Allgemeinen mit Ganzzahltypen und `enum`-Typen verwenden.  
  
## <a name="logical-xor-operator"></a>Logischer XOR-Operator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x ^ y](../../../csharp/language-reference/operators/xor-operator.md) – logisches oder bitweises XOR. Sie können dies im Allgemeinen mit Ganzzahltypen und `enum`-Typen verwenden.  
  
## <a name="logical-or-operator"></a>Logischer OR-Operator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – logisches oder bitweises OR. Sie können dies im Allgemeinen mit Ganzzahltypen und `enum`-Typen verwenden.  
  
## <a name="conditional-and-operator"></a>Bedingter AND-Operator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) – logisches AND. Wenn der erste Operand FALSE ist, wertet C# den zweiten Operand nicht aus.  
  
## <a name="conditional-or-operator"></a>Bedingter OR-Operator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) – Logisches OR. Wenn der erste Operand TRUE ist, wertet C# den zweiten Operand nicht aus.  
  
## <a name="null-coalescing-operator"></a>Nullzusammensetzungsoperator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x ?? y](../../../csharp/language-reference/operators/null-coalescing-operator.md) – Gibt `x` zurück, sofern es Nicht-`null` ist; ansonsten wird `y` zurückgegeben.  
  
## <a name="conditional-operator"></a>Bedingter Operator  
 Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md): Wenn der Test `t` TRUE ist, wird `x` ausgewertet und zurückgegeben, ansonsten wird `y` ausgewertet und zurückgegeben.  
  
## <a name="assignment-and-lambda-operators"></a>Zuweisung- und Lambdaoperatoren  
 Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.  
  
 [x = y](../../../csharp/language-reference/operators/assignment-operator.md) – Zuweisung.  
  
 [x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) – Inkrement. Fügen Sie dem Wert `x` den Wert `y` hinzu. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück. Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler hinzufügt.  
  
 [x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) – Dekrement. Subtrahieren Sie vom Wert `x` den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück. Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler entfernt.  
  
 [x *= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) – Multiplikationszuweisung. Multiplizieren Sie den Wert `y` mit dem Wert `x`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) – Divisionszuweisung. Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [x %= y](../../../csharp/language-reference/operators/remainder-assignment-operator.md) – Restwertzuweisung. Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie den Rest in `x`, und geben Sie den neuen Wert zurück.  
  
 [x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) – AND-Zuweisung. Führen Sie eine AND-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) – OR-Zuweisung. Führen Sie eine OR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) – XOR-Zuweisung. Führen Sie eine XOR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) – Linksschiebezuweisung. Verschieben Sie den Wert von `x` nach links um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) – Rechtsschiebezuweisung. Verschieben Sie den Wert von `x` nach rechts um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.  
  
 [=>](../../../csharp/language-reference/operators/lambda-operator.md) – Lambdadeklaration.  
  
## <a name="arithmetic-overflow"></a>Arithmetischer Überlauf  
 Die arithmetischen Operatoren ([+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md)) können Ergebnisse erzeugen, die sich außerhalb des zulässigen Wertebereichs für den betreffenden numerischen Typ befinden. Einzelheiten zu bestimmten Operatoren finden Sie im entsprechenden Abschnitt, grundsätzlich gilt aber:  
  
- Arithmetischer Überlauf bei ganzen Zahlen löst entweder eine <xref:System.OverflowException> aus oder verwirft die höchstwertigen Bits des Ergebnisses. Division ganzer Zahlen durch Null löst immer eine <xref:System.DivideByZeroException> aus.  

   Wenn ein Überlauf bei ganzen Zahlen auftritt, hängen die Auswirkungen vom Ausführungskontext ab, bei dem es sich um [checked oder unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) handeln kann. In einem "checked"-Kontext wird eine <xref:System.OverflowException> ausgelöst. In einem "unchecked"-Kontext werden die höchstwertigen Bits verworfen, und die Ausführung wird fortgesetzt. Bei C# haben Sie die Wahl, einen Überlauf zu verarbeiten oder zu ignorieren. Standardmäßig erscheinen arithmetische Operationen in einem *unchecked*-Kontext. 

   Neben arithmetischen Operationen können auch Konvertierungen zwischen ganzzahligen Typen (z.B. die Umwandlung von [long](../../../csharp/language-reference/keywords/long.md) nach [int](../../../csharp/language-reference/keywords/int.md)) einen Überlauf verursachen. Sie sind von der Ausführung „checked“ oder „unchecked“ abhängig. Bitweise Operatoren und Schiebeoperatoren verursachen allerdings nie einen Überlauf.  
   
-   Arithmetischer Überlauf oder Division durch 0 (null) löst bei Gleitkommazahlen nie eine Ausnahme aus, weil die Gleitkommatypen auf IEEE 754 basieren und daher Vorkehrungen für die Darstellung von Unendlich und NaN (Not a Number/Keine Zahl) aufweisen.  
  
-   Arithmetischer Überlauf bei [Decimal](../../../csharp/language-reference/keywords/decimal.md) löst immer eine <xref:System.OverflowException> aus. Dezimale Division durch Null löst immer eine <xref:System.DivideByZeroException> aus.  

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#](../../../csharp/index.md)
- [Überladbare Operatoren](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
