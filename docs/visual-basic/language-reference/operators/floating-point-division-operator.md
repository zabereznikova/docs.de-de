---
title: /-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f221e863725b9aeb0b3fa3219b3a881541e2be0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 Das Ergebnis ist der vollständige Quotient aus `expression1` geteilt durch `expression2`, einschließlich des Rests.  
  
 Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den Quotienten ganze Zahl zurück, die im weiteren Verlauf gelöscht.  
  
## <a name="remarks"></a>Hinweise  
 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab. Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Datentypen der Operanden|Der Ergebnisdatentyp|  
|------------------------|----------------------|  
|Beide Ausdrücke sind ganzzahlige Datentypen (["SByte"](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), ["ushort"](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Ein Ausdruck ist eine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) -Datentyp und der andere wird keine [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Ein Ausdruck ist eine [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp und der andere wird keine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) oder ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Einer der Ausdrücke ist ein [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp|`Double`|  
  
 Bevor Division ausgeführt wird, werden alle ganzzahligen numerischen Ausdrücke auf Erweitert `Double`. Wenn Sie das Ergebnis in einen ganzzahligen Datentyp zuweisen, versucht Visual Basic konvertieren das Ergebnis von `Double` auf diesen Typ. Dies kann eine Ausnahme ausgelöst, wenn das Ergebnis nicht in diesem Typ passt. Insbesondere finden Sie unter "Division durch Null versucht" auf dieser Hilfeseite.  
  
 Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird dies als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Wenn `expression2` ergibt 0 (null), die `/` Operator weist unterschiedliches Verhaltensweisen für unterschiedliche Operandendatentypen. Die folgende Tabelle zeigt die möglichen Verhaltensweisen.  
  
|Datentypen der Operanden|Verhalten Wenn `expression2` 0 (null)|  
|------------------------|---------------------------------------|  
|Gleitkomma (`Single` oder `Double`)|Gibt unendlich (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>), oder <xref:System.Double.NaN> (keine Zahl) Wenn `expression1` ist auch 0 (null)|  
|`Decimal`|Löst aus<xref:System.DivideByZeroException>|  
|Ganzzahltypen (mit oder ohne Vorzeichen)|Wechsel zurück in den ganzzahligen Typ löst versucht <xref:System.OverflowException> da Ganzzahltypen nicht akzeptieren können <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, oder<xref:System.Double.NaN>|  
  
> [!NOTE]
>  Die `/` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `/` Operator Gleitkommadivision ausführen. Das Ergebnis ist der Quotient der beiden Operanden.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 Die Ausdrücke im vorangehenden Beispiel Rückgabewerte 2,5 und 3,333333 zurück. Beachten Sie, dass das Ergebnis immer Gleitkomma (`Double`), auch wenn beide Operanden ganzzahlige Konstanten sind.  
  
## <a name="see-also"></a>Siehe auch  
 [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [Datentypen von Operatorergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
