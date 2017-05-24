---
title: /-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
dev_langs:
- VB
helpviewer_keywords:
- division operator, floating point
- floating-point numbers, division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators, division
- division, by zero
- operators [Visual Basic], division
- division operator, syntax
- / operator [Visual Basic]
- math operators
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 71b4f64f6deeb334412c87131ccd9480620f284f
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

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
  
 Die [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten zurück, wobei der Rest entfällt.  
  
## <a name="remarks"></a>Hinweise  
 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab. Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Datentypen der Operanden|Datentyp|  
|------------------------|----------------------|  
|Beide Ausdrücke sind ganzzahlige Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lang](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Ein Ausdruck ist ein [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) Daten und das andere ist ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Ein Ausdruck ist eine [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) Daten und das andere ist eine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) oder eine [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Ein Ausdruck ist ein [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp|`Double`|  
  
 Vor der Division ist, werden alle ganzzahligen numerischen Ausdrücke zu erweitert `Double`. Wenn Sie das Ergebnis einem ganzzahligen Datentyp zuweisen, versucht Visual Basic, das Ergebnis von konvertieren `Double` auf diesen Typ. Dies kann eine Ausnahme auslösen, wenn das Ergebnis nicht in diesem Typ passt. Insbesondere finden Sie unter "Versuchte Division durch&0;" auf dieser Hilfeseite.  
  
 Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als&0; (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch&0; (null)  
 Wenn `expression2` NULL ist, ergibt die `/` -Operator verhält sich anders, für die Operanden unterschiedliche Datentypen. In der folgenden Tabelle sind die möglichen Verhaltensweisen.  
  
|Datentypen der Operanden|Verhalten Wenn `expression2`&0; (null)|  
|------------------------|---------------------------------------|  
|Gleitkomma (`Single` oder `Double`)|Gibt unendlich (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>), oder <xref:System.Double.NaN>(keine Zahl) Wenn `expression1` sind ebenfalls NULL</xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity>|  
|`Decimal`|Löst aus<xref:System.DivideByZeroException></xref:System.DivideByZeroException>|  
|Ganze Zahl (mit oder ohne Vorzeichen)|Konvertierung in den ganzzahligen Typ löst versucht <xref:System.OverflowException>da Ganzzahltypen akzeptieren können <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, oder <xref:System.Double.NaN></xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.OverflowException>|  
  
> [!NOTE]
>  Die `/` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist. Wenn Ihr Code auf eine solche Klasse oder Struktur dieser Operator verwendet wird, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `/` Operator, um Gleitkommadivisionen auszuführen. Das Ergebnis ist der Quotient der zwei Operanden.  
  
 [!code-vb[VbVbalrOperators Nr.&16;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 Die Ausdrücke im vorangehenden Beispiel geben die Werte 2,5 und 3,333333 zurück. Beachten Sie, dass das Ergebnis immer Gleitkomma (`Double`), obwohl beide Operanden ganzzahlige Konstanten sind.  
  
## <a name="see-also"></a>Siehe auch  
 [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [Datentypen von Operatorergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)   
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

