---
title: /-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: af2316f92e2904eee1e8c046b34b8147e40cb513
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778481"
---
# <a name="-operator-visual-basic"></a>/-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt ein Gleitkommaergebnis zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>Teile  
 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der volle Quotient von `expression1` geteilt durch `expression2`, einschließlich des Rests.  
  
 Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den Quotienten ganze Zahl, die im weiteren Verlauf gelöscht.  
  
## <a name="remarks"></a>Hinweise  
 Der Datentyp des Ergebnisses, hängt von den Typen der Operanden ab. Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Datentypen der Operanden|Der Ergebnisdatentyp|  
|------------------------|----------------------|  
|Beide Ausdrücke sind ganzzahlige Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Ein Ausdruck ist eine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) -Datentyp und die andere ist keiner [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Ein Ausdruck ist eine [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp und die andere ist keiner [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) oder ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Einer der Ausdrücke ist eine [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp|`Double`|  
  
 Vor der Division, werden alle ganzzahligen numerischen Ausdrücke zu erweitert `Double`. Wenn Sie das Ergebnis in einen ganzzahligen Datentyp zuweisen, versucht Visual Basic, das Ergebnis von konvertieren `Double` auf diesen Typ. Dies kann eine Ausnahme auslösen, wenn das Ergebnis nicht in diesem Typ passt. Insbesondere finden Sie unter "Division durch Null versucht" auf dieser Hilfeseite.  
  
 Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Wenn `expression2` ergibt 0 (null), die `/` Operators verhält sich anders, für die Datentypen der andere Operand. Die folgende Tabelle zeigt die möglichen Verhaltensweisen.  
  
|Datentypen der Operanden|Verhalten Wenn `expression2` ist 0 (null)|  
|------------------------|---------------------------------------|  
|Gleitkomma (`Single` oder `Double`)|Gibt Unendlich zurück (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>), oder <xref:System.Double.NaN> (keine Zahl) Wenn `expression1` ist auch 0 (null)|  
|`Decimal`|Löst aus <xref:System.DivideByZeroException>|  
|Integral (mit oder ohne Vorzeichen)|Wechsel zurück in den ganzzahligen Typ löst versucht <xref:System.OverflowException> da ganzzahlige Typen nicht akzeptieren können <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, oder <xref:System.Double.NaN>|  
  
> [!NOTE]
>  Die `/` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `/` -Operator Gleitkommadivision ausgeführt. Das Ergebnis ist der Quotient der beiden Operanden.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Die Ausdrücke im vorangehenden Beispiel Rückgabewerte 2,5 und 3,333333 zurück. Beachten Sie, dass das Ergebnis immer Gleitkomma (`Double`), auch wenn beide Operanden ganzzahlige Konstanten sind.  
  
## <a name="see-also"></a>Siehe auch

- [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Datentypen von Operatorergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
