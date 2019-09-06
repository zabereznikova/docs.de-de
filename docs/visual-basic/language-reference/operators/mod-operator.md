---
title: Operator Mod(Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: dc1e866836bb7420ffe17210b5be7a5e1d4048d0
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374493"
---
# <a name="mod-operator-visual-basic"></a>Mod-Operator (Visual Basic)

Dividiert zwei Zahlen und gibt nur den Rest zurück.

## <a name="syntax"></a>Syntax

```vb
result = number1 Mod number2
```

## <a name="parts"></a>Teile

`result` \
Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.

`number1` \
Erforderlich. Ein beliebiger numerischer Ausdruck.

`number2` \
Erforderlich. Ein beliebiger numerischer Ausdruck.

## <a name="supported-types"></a>Unterstützte Typen

allen numerischen Typen Dies schließt die unsignierten-und Gleit Komma Typen `Decimal`und ein.

## <a name="result"></a>Ergebnis

Das Ergebnis ist der Rest, `number1` nachdem durch dividiert wurde. `number2` Beispielsweise wird der Ausdruck `14 Mod 4` zu 2 ausgewertet.

> [!NOTE]
> Es gibt einen Unterschied zwischen *Rest* und *Modulo* in der Mathematik mit unterschiedlichen Ergebnissen für negative Zahlen. Der `Mod` Operator in Visual Basic, der .NET Framework `op_Modulus` -Operator und die zugrunde liegende [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) Il-Anweisung führen einen Rest-Vorgang aus.

Das Ergebnis eines `Mod` -Vorgangs behält das Vorzeichen der `number1`Dividende bei, und es kann positiv oder negativ sein. Das Ergebnis liegt immer im Bereich (-`number2`, `number2`), exklusiv. Beispiel:

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>Hinweise

Wenn entweder `number1` oder `number2` ein Gleit Komma Wert ist, wird der Rest der Division zurückgegeben. Der Datentyp des Ergebnisses ist der kleinste Datentyp, der alle möglichen Werte enthalten kann, die sich aus der Division mit den Daten `number1` Typen `number2`und ergeben.

Wenn `number1` oder`number2` als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.

Verwandte Operatoren umfassen Folgendes:

- Der [Operator \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück. Der Ausdruck `14 \ 4` wird z. b. zu 3 ausgewertet.

- Der [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten, einschließlich des Restwerts, als Gleit Komma Zahl zurück. Der Ausdruck `14 / 4` wird z. b. zu 3,5 ausgewertet.

## <a name="attempted-division-by-zero"></a>Versuchte Division durch Null

Wenn `number2` der Wert 0 (null) ergibt, `Mod` hängt das Verhalten des-Operators vom Datentyp der Operanden ab:
- Eine ganzzahlige Division <xref:System.DivideByZeroException> löst eine `number2` -Ausnahme aus, wenn nicht in der Kompilierzeit bestimmt werden kann `BC30542 Division by zero occurred while evaluating this expression` , `number2` und generiert einen Kompilierzeitfehler, wenn zur Kompilierzeit NULL ergibt.
- Eine Gleit Komma Division gibt zurück <xref:System.Double.NaN?displayProperty=nameWithType>.

## <a name="equivalent-formula"></a>Äquivalente Formel

Der Ausdruck `a Mod b` entspricht einer der folgenden Formeln:

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>Ungenauigkeit von Gleit Komma Werten

Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Dezimal Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen von bestimmten Vorgängen führen, wie z. b. `Mod` Wert Vergleiche und Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="overloading"></a>Überladen

Der `Mod` Operator kann *überladen*werden, was bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann. Wenn Ihr Code auf `Mod` eine Instanz einer Klasse oder Struktur angewendet wird, die eine solche Überlastung einschließt, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der `Mod` -Operator verwendet, um zwei Zahlen aufzuteilen und nur den Rest zurückzugeben. Wenn eine der Zahlen eine Gleit Komma Zahl ist, ist das Ergebnis eine Gleit Komma Zahl, die den Restwert darstellt.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die mögliche Ungenauigkeit von Gleit Komma Operanden veranschaulicht. In der ersten Anweisung sind `Double`die Operanden, und 0,2 ist ein unendlich wiederholter binärer Bruchteil mit einem gespeicherten Wert von 0.20000000000000001. In der zweiten Anweisung erzwingt das Literaltypzeichen `D` beide Operanden zu `Decimal`, und 0,2 hat eine genaue Darstellung.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operator \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
