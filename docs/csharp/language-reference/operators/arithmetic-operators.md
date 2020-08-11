---
title: 'Arithmetische Operatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Operatoren, die Multiplikations-, Divisions-, Rest-, Additions- und Subtraktionsoperationen mit numerischen Typen ausführen.
ms.date: 05/11/2020
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
- '%=_CSharpKeyword'
- '*=_CSharpKeyword'
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: f5da9c4433ffcf3e6a110bbb1543343289240778
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916955"
---
# <a name="arithmetic-operators-c-reference"></a>Arithmetische Operatoren (C#-Referenz)

Die folgenden Operatoren führen arithmetische Operationen mit Operanden des numerischen Typs aus:

- Unäre Operatoren: [`++` (inkrementell)](#increment-operator-), [`--` (dekrementell)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators) und [`-` (minus)](#unary-plus-and-minus-operators)
- Binäre Operatoren: [`*` (Multiplikation)](#multiplication-operator-), [`/` (Division)](#division-operator-), [`%` (Rest)](#remainder-operator-), [`+` (Addition)](#addition-operator-) und [`-` (Subtraktion)](#subtraction-operator--)

Diese Operatoren werden alle von numerischen [Ganzzahl](../builtin-types/integral-numeric-types.md)- und [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) unterstützt.

Bei integralen Typen werden diese Operatoren (außer den Operatoren `++` und `--`) für die Typen `int`, `uint`, `long` und `ulong` definiert. Wenn Operanden andere integrale Typen aufweisen (`sbyte`, `byte`, `short`, `ushort` oder `char`), werden ihre Werte in den Typ `int` konvertiert. Hierbei handelt es sich auch um den Ergebnistyp einer Operation. Wenn Operanden abweichende integrale Typen oder Gleitkommatypen aufweisen, werden ihre Werte in den am besten geeigneten enthaltenden Typ konvertiert, falls solch ein Typ vorhanden ist. Weitere Informationen finden Sie im Abschnitt [Numerische Heraufstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md). Die `++`- und `--`-Operatoren werden für alle numerischen integralen und Gleitkommatypen sowie den [char](../builtin-types/char.md)-Typ definiert.

## <a name="increment-operator-"></a>Inkrementoperator ++

Der unäre Inkrementoperator (`++`) erhöht seinen Operanden um 1. Der Operand muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexerzugriff](../../programming-guide/indexers/index.md) sein.

Der Inkrementoperator wird in zwei Formen unterstützt: als Postfix-Inkrementoperator `x++` und als Präfix-Inkrementoperator `++x`.

### <a name="postfix-increment-operator"></a>Postfix-Operator für Inkrement

Das Ergebnis von `x++` ist der Wert von `x` *vor* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[postfix increment](snippets/shared/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a>Präfixinkrement-Operator

Das Ergebnis von `++x` ist der Wert von `x` *nach* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[prefix increment](snippets/shared/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a>Dekrementoperator --

Der unäre Dekrementoperator `--` verringert seinen Operanden um 1. Der Operand muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexerzugriff](../../programming-guide/indexers/index.md) sein.

Der Dekrementoperator wird in zwei Formen unterstützt: als Postfix-Dekrementoperator `x--` und als Präfix-Dekrementoperator `--x`.

### <a name="postfix-decrement-operator"></a>Postfix-Operator für Dekrement

Das Ergebnis von `x--` ist der Wert von `x` *vor* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[postfix decrement](snippets/shared/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a>Präfix-Dekrementoperator

Das Ergebnis von `--x` ist der Wert von `x` *nach* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[prefix decrement](snippets/shared/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a>Unäre Plus- und Minusoperatoren

Der unäre `+`-Operator gibt den Wert seines Operanden zurück. Der unäre `-`-Operator berechnet die numerische Negation des Operanden.

[!code-csharp-interactive[unary plus and minus](snippets/shared/ArithmeticOperators.cs#UnaryPlusAndMinus)]

Der [ulong](../builtin-types/integral-numeric-types.md)-Typ unterstützt den unären `-`-Operator nicht.

## <a name="multiplication-operator-"></a>Multiplikationsoperator *

Der Multiplikationsoperator `*` berechnet das Produkt seiner Operanden:

[!code-csharp-interactive[multiplication operator](snippets/shared/ArithmeticOperators.cs#Multiplication)]

Der unäre `*`-Operator ist der [Zeigerdereferenzierungsoperator](pointer-related-operators.md#pointer-indirection-operator-).

## <a name="division-operator-"></a>Divisionsoperator /

Der Divisionsoperator `/` dividiert den linken Operanden durch den rechten Operanden.

### <a name="integer-division"></a>Ganzzahldivision

Für die Operanden von Ganzzahltypen weist das Ergebnis des `/`-Operators einen Ganzzahltyp auf und ist gleich dem Quotienten der beiden Operanden, gerundet auf Null:

[!code-csharp-interactive[integer division](snippets/shared/ArithmeticOperators.cs#IntegerDivision)]

Um den Quotienten der beiden Operanden als Gleitkommazahl abzurufen, verwenden Sie den Typ `float`, `double` oder `decimal`:

[!code-csharp-interactive[integer as floating-point division](snippets/shared/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a>Gleitkommadivision

Für die Typen `float`, `double` oder `decimal` ist das Ergebnis des `/`-Operators der Quotient der beiden Operanden:

[!code-csharp-interactive[floating-point division](snippets/shared/ArithmeticOperators.cs#FloatingPointDivision)]

Wenn einer der Operanden `decimal` lautet, kann ein anderer Operand weder `float` noch `double` sein, weil weder `float` noch `double` implizit zu `decimal` konvertiert werden können. Sie müssen den Operanden `float` oder `double` explizit zum Typ `decimal` konvertieren. Weitere Informationen zu Konvertierungen zwischen numerischen Typen finden Sie unter [Built-in numeric conversions](../builtin-types/numeric-conversions.md) (Integrierte numerischer Konvertierungen).

## <a name="remainder-operator-"></a>Restoperator %

Der Restoperator `%` berechnet den Rest nach der Division seines linken Operanden durch den rechten Operanden.

### <a name="integer-remainder"></a>Ganzzahliger Rest

Für Operanden von Ganzzahltypen entspricht das Ergebnis von `a % b` dem von `a - (a / b) * b` erzeugten Wert. Das Vorzeichen des Rests, der ungleich 0 (null) ist, ist wie im folgenden Beispiel gezeigt identisch mit dem des linken Operanden:

[!code-csharp-interactive[integer remainder](snippets/shared/ArithmeticOperators.cs#IntegerRemainder)]

Verwenden Sie die <xref:System.Math.DivRem%2A?displayProperty=nameWithType>-Methode, wenn Sie sowohl Ganzzahldivision als auch Restergebnisse berechnen möchten.

### <a name="floating-point-remainder"></a>Gleitkommarest

Für die Operanden `float` und `double` entspricht das Ergebnis von `x % y` für die endlichen Werte `x` und `y` dem Wert `z`, sodass:

- das Vorzeichen von `z` dem Vorzeichen von `x` entspricht, sofern der Wert nicht 0 (null) ist.
- der absolute Wert von `z` dem von `|x| - n * |y|` erzeugten Wert entspricht, wobei `n` der größtmöglichen Ganzzahl entspricht, die kleiner oder gleich `|x| / |y|` ist. Hierbei sind `|x|` und `|y|` jeweils die absoluten Werte von `x` und `y`.

> [!NOTE]
> Diese Methode zum Berechnen des Rests ist analog zu der Methode, die für ganzzahlige Operanden verwendet wird, unterscheidet sich jedoch von der IEEE 754-Spezifikation. Wenn Sie den Restvorgang benötigen, der der IEEE 754-Spezifikation entspricht, verwenden Sie die Methode <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

Weitere Informationen zum Verhalten des `%`-Operators bei nicht begrenzten Operanden finden Sie im Abschnitt [Restoperator](~/_csharplang/spec/expressions.md#remainder-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Der Restoperator `%` entspricht für die `decimal`-Operanden dem [Restoperator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) vom Typ <xref:System.Decimal?displayProperty=nameWithType>.

Im folgenden Beispiel wird das Verhalten des Restoperators mit Gleitkommaoperanden veranschaulicht:

[!code-csharp-interactive[floating-point remainder](snippets/shared/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a>Additionsoperator +

Der Additionsoperator `+` berechnet die Summe der Operanden:

[!code-csharp-interactive[addition operator](snippets/shared/ArithmeticOperators.cs#Addition)]

Der `+`-Operator kann auch für die Zeichenfolgenverkettung und Delegatkombination verwendet werden. Weitere Informationen finden Sie im [Artikel zu den Operatoren `+` und `+=`](addition-operator.md).

## <a name="subtraction-operator--"></a>Subtraktionsoperator -

Der Subtraktionsoperator `-` subtrahiert den rechten Operanden vom linken:

[!code-csharp-interactive[subtraction operator](snippets/shared/ArithmeticOperators.cs#Subtraction)]

Der `-`-Operator kann auch für die Delegatentfernung verwendet werden. Weitere Informationen finden Sie im [Artikel zu den Operatoren `-` und `-=`](subtraction-operator.md).

## <a name="compound-assignment"></a>Verbundzuweisung

Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form

```csharp
x op= y
```

für die folgende Syntax:

```csharp
x = x op y
```

außer dass `x` nur einmal überprüft wird.

Im folgenden Beispiel wird die Verwendung von Verbundzuweisungen mit arithmetischen Operatoren veranschaulicht:

[!code-csharp-interactive[compound assignment](snippets/shared/ArithmeticOperators.cs#CompoundAssignment)]

Aufgrund von [numerischen Höherstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) kann das Ergebnis der Operation `op` ggf. nicht implizit in den Typ `T` von `x` konvertiert werden. In diesem Fall gilt Folgendes: Wenn `op` ein vordefinierter Operator ist und das Ergebnis der Operation explizit in den Typ `T` von `x` konvertiert werden kann, entspricht ein Verbundzuweisungsausdruck der Form `x op= y` dem Ausdruck `x = (T)(x op y)`. Der einzige Unterschied ist, dass `x` nur einmal ausgewertet wird. Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp-interactive[compound assignment with cast](snippets/shared/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

Die Operatoren `+=` und `-=` können auch zum Abonnieren von Ereignissen und zum Kündigen eines [Ereignisabonnements](../keywords/event.md) verwendet werden. Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-precedence-and-associativity"></a>Operatorrangfolge und Assoziativität

In der folgenden Liste sind die arithmetischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:

- Postfixinkrementoperator `x++` und Postfixdekrementoperator `x--`
- Präfixinkrementoperator `++x` und Präfixdekrementoperator `--x` sowie unäre `+`- und `-`-Operatoren
- Multiplikative Operatoren `*`, `/` und `%`
- Additive Operatoren `+` und `-`

Binäre arithmetische Operatoren sind linksassoziativ. Das bedeutet, dass Operatoren mit der gleichen Rangfolgenebene von links nach rechts ausgewertet werden.

Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge und Assoziativität festgelegt wird.

[!code-csharp-interactive[precedence and associativity](snippets/shared/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).

## <a name="arithmetic-overflow-and-division-by-zero"></a>Arithmetischer Überlauf und Division durch 0 (null)

Liegt das Ergebnis einer arithmetischen Operation außerhalb des Bereichs möglicher endlicher Werte des betreffenden numerischen Typs, hängt das Verhalten eines arithmetischen Operators vom Typ der Operanden ab.

### <a name="integer-arithmetic-overflow"></a>Arithmetischer Überlauf bei ganzen Zahlen

Division ganzer Zahlen durch Null löst immer eine <xref:System.DivideByZeroException> aus.

Im Fall eines arithmetischen Überlaufs bei ganzen Zahlen steuert ein Kontext für Überlaufprüfungen, der [aktiviert oder deaktiviert (Checked oder Unchecked)](../keywords/checked-and-unchecked.md) sein kann, das resultierende Verhalten:

- In einem aktivierten Kontext tritt bei einem Überlauf in einem konstanten Ausdruck ein Kompilierzeitfehler auf. Andernfalls wird, wenn die Operation zur Laufzeit ausgeführt wird, eine <xref:System.OverflowException>-Ausnahme ausgelöst.
- In einem deaktivierten Kontext wird das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.

Neben den Anweisungen [Checked und Unchecked](../keywords/checked-and-unchecked.md) können Sie mithilfe der `checked`- und `unchecked`-Operatoren den Kontext für Überlaufprüfungen steuern, in dem ein Ausdruck ausgewertet wird:

[!code-csharp-interactive[checked and unchecked](snippets/shared/ArithmeticOperators.cs#CheckedUnchecked)]

Standardmäßig erscheinen arithmetische Operationen in einem *unchecked*-Kontext.

### <a name="floating-point-arithmetic-overflow"></a>Arithmetischer Überlauf bei Gleitkommatypen

Bei arithmetischen Operationen mit den Typen `float` und `double` wird nie eine Ausnahme ausgelöst. Das Ergebnis von arithmetischen Operationen mit diesen Typen können spezielle Werte sein, die unendliche und nicht numerische Zahlen darstellen:

[!code-csharp-interactive[double non-finite values](snippets/shared/ArithmeticOperators.cs#FloatingPointOverflow)]

Für Operanden vom Typ `decimal` löst ein arithmetischer Überlauf immer eine <xref:System.OverflowException>-Ausnahme und die Division durch 0 (null) immer eine <xref:System.DivideByZeroException>-Ausnahme aus.

## <a name="round-off-errors"></a>Rundungsfehler

Aufgrund allgemeiner Einschränkungen der Gleitkommadarstellung von reellen Zahlen und arithmetischer Gleitkommaoperatoren können in Berechnungen mit Gleitkommatypen Rundungsfehler auftreten. Das bedeutet, dass das generierte Ergebnis eines Ausdrucks vom erwarteten mathematischen Ergebnis abweichen kann. Im folgenden Beispiel werden einige solcher Fälle dargestellt:

[!code-csharp-interactive[round-off errors](snippets/shared/ArithmeticOperators.cs#RoundOffErrors)]

Weitere Informationen finden Sie in den Hinweisen auf den Referenzseiten zu [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) oder [System.Decimal](/dotnet/api/system.decimal#remarks).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann die unären (`++`, `--`, `+` und `-`) und binären (`*`, `/`, `%`, `+` und `-`) arithmetischen Operatoren [überladen](operator-overloading.md). Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen. Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Postfix-Inkrementoperator und Postfix-Dekrementoperator](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [Präfix-Inkrementoperator und Präfix-Dekrementoperator](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [Unärer Minusoperator](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [Multiplikationsoperator](~/_csharplang/spec/expressions.md#multiplication-operator)
- [Divisionsoperator](~/_csharplang/spec/expressions.md#division-operator)
- [Restoperator](~/_csharplang/spec/expressions.md#remainder-operator)
- [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator)
- [Subtraktionsoperator](~/_csharplang/spec/expressions.md#subtraction-operator)
- [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment)
- [The checked and unchecked operators (Checked- und Unchecked-Operatoren)](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [Numerische Heraufstufungen](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [Numerische Ausdrücke in .NET](../../../standard/numerics.md)
