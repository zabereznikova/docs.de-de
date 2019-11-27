---
title: Operator /
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
ms.openlocfilehash: 537d8b0c703b59743f1a7c531448118058707645
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331055"
---
# <a name="-operator-visual-basic"></a>/-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt ein Gleit Komma Ergebnis zurück.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a>-Komponenten  
 `expression1`  
 Erforderlich Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der unsignierten und Gleit Komma Typen und `Decimal`.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der vollständige Quotienten von `expression1` dividiert durch `expression2`, einschließlich Rest.  
  
 Der [Operator \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten zurück, der den Rest löscht.  
  
## <a name="remarks"></a>Hinweise  
 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab. In der folgenden Tabelle wird gezeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Operanden Datentypen|Ergebnis Datentyp|  
|------------------------|----------------------|  
|Beide Ausdrücke sind [ganzzahlige](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), UInteger, [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ulong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)).|`Double`|  
|Ein Ausdruck ist ein [einzelner](../../../visual-basic/language-reference/data-types/single-data-type.md) Datentyp, und der andere ist kein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) .|`Single`|  
|Ein Ausdruck ist ein [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp, der andere kein [einzelner](../../../visual-basic/language-reference/data-types/single-data-type.md) oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -Wert.|`Decimal`|  
|Jeder Ausdruck ist ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp.|`Double`|  
  
 Bevor die Division durchgeführt wird, werden alle ganzzahligen numerischen Ausdrücke auf `Double`erweitert. Wenn Sie das Ergebnis einem ganzzahligen Datentyp zuweisen, versucht Visual Basic, das Ergebnis von `Double` in diesen Typ zu konvertieren. Dadurch kann eine Ausnahme ausgelöst werden, wenn das Ergebnis nicht in diesen Typ passt. Weitere Informationen finden Sie auf dieser Hilfeseite unter "versuchte Division durch Null".  
  
 Wenn `expression1` oder `expression2` als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch Null  
 Wenn `expression2` den Wert 0 (null) ergibt, verhält sich der `/` Operator bei verschiedenen Operanden-Datentypen unterschiedlich. In der folgenden Tabelle sind die möglichen Verhalten aufgeführt.  
  
|Operanden Datentypen|Verhalten, wenn `expression2` NULL ist|  
|------------------------|---------------------------------------|  
|Gleit Komma (`Single` oder `Double`)|Gibt unendlich (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>) oder <xref:System.Double.NaN> (keine Zahl) zurück, wenn `expression1` ebenfalls 0 (null) ist.|  
|`Decimal`|Löst <xref:System.DivideByZeroException>|  
|Ganzzahl (signiert oder unsigniert)|Bei der Konvertierung in einen ganzzahligen Typ wird <xref:System.OverflowException> ausgelöst, da ganzzahlige Typen <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>oder <xref:System.Double.NaN> nicht akzeptieren können.|  
  
> [!NOTE]
> Der `/`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der `/`-Operator verwendet, um eine Gleit Komma Division auszuführen. Das Ergebnis ist der Quotienten der beiden Operanden.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Die Ausdrücke im vorherigen Beispiel geben die Werte 2,5 und 3,333333 zurück. Beachten Sie, dass das Ergebnis immer Gleit Komma (`Double`) ist, obwohl beide Operanden ganzzahlige Konstanten sind.  
  
## <a name="see-also"></a>Siehe auch

- [Operator/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Operator \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Datentypen von Operatorergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
