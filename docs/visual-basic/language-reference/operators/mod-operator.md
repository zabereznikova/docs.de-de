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
ms.openlocfilehash: f1334ff7aa07f49139bfe684746ae9cc3cf8087c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663171"
---
# <a name="mod-operator-visual-basic"></a>MOD-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt nur den Restwert zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>Teile  
 `number1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `number2`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 allen numerischen Typen Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="result"></a>Ergebnis

Das Ergebnis ist der Rest nach der `number1` wird geteilt durch `number2`. Beispiel: der Ausdruck `14 Mod 4` 2 ergibt.  

> [!NOTE]
> Es gibt einen Unterschied zwischen *Rest* und *Modulo* in der Mathematik mit unterschiedlichen Ergebnissen für negative Zahlen. Die `Mod` -Operator in Visual Basic .NET Framework `op_Modulus` Operator und den zugrunde liegenden [Rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL-Anweisung, die alle einen Remainder-Vorgang ausführen.

Das Ergebnis einer `Mod` Vorgang behält die Vorzeichen des Divisors, `number1`, und daher positiv oder negativ sein. Das Ergebnis ist immer im Bereich (-`number2`, `number2`), exklusive. Zum Beispiel:

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
 Wenn entweder `number1` oder `number2` ist ein Gleitkommawert, der Gleitkommarest von der Abteilung zurückgegeben wird. Der Datentyp des Ergebnisses ist den kleinsten Datentyp, die alle möglichen Werte enthalten kann, die aus der Division mit den Datentypen der führen `number1` und `number2`.  
  
 Wenn `number1` oder `number2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.  
  
 Die folgenden: zugehörige Operatoren  
  
- Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück. Beispiel: der Ausdruck `14 \ 4` 3 ergibt.  
  
- Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt zurück, der volle Quotient, einschließlich den Rest als Gleitkommazahl. Beispiel: der Ausdruck `14 / 4` 3.5 ergibt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Wenn `number2` ergibt NULL, das Verhalten der `Mod` Operator hängt von den Datentyp des Operanden. Ganzzahldivision wird eine <xref:System.DivideByZeroException> Ausnahme. Gibt eine Gleitkommadivision <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Gleichwertigen Formel  
 Der Ausdruck `a Mod b` ist gleichbedeutend mit einer der folgenden Formeln:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>Gleitkomma Ungenauigkeit  
 Beim Arbeiten mit Gleitkommazahlen, denken Sie daran, dass sie nicht immer eine genaue dezimale Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. den Wertvergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Überladen  
 Die `Mod` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann. Wenn Ihr Code gilt `Mod` mit einer Instanz einer Klasse oder Struktur, die solche eine Überladung umfasst, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Mod` Operator, um zwei Zahlen dividiert, und nur den Rest zurückzugeben. Wenn entweder Anzahl eine Gleitkommazahl ist, ist das Ergebnis eine Gleitkommazahl, die den Rest darstellt.  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden. In der ersten Anweisung, die Operanden sind `Double`, 0,2 ist ein unendlich Binärbruch mit dem gespeicherten Wert 0,20000000000000001. In der zweiten Anweisung, das Literal-Typzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 verfügt über eine genaue Darstellung.  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
