---
title: '* Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 4f6a8ea2c5f4e23791afdfe98d2a08bf67219048
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348365"
---
# <a name="-operator-visual-basic"></a>*-Operator (Visual Basic)
Multipliziert zwei Zahlen miteinander.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`number1`|Erforderlich Ein beliebiger numerischer Ausdruck.|  
|`number2`|Erforderlich Ein beliebiger numerischer Ausdruck.|  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist das Produkt von `number1` und `number2`.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der unsignierten und Gleit Komma Typen und `Decimal`.  
  
## <a name="remarks"></a>Hinweise  
 Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab. In der folgenden Tabelle wird gezeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Operanden Datentypen|Ergebnis Datentyp|  
|---|---|  
|Beide Ausdrücke sind [ganzzahlige](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), UInteger, [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ulong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)).|Ein numerischer Datentyp, der für die Datentypen von `number1` und `number2`geeignet ist. Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)|  
|Beide Ausdrücke sind [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) .|`Decimal`|  
|Beide Ausdrücke sind [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Jeder Ausdruck ist ein Gleit Komma Datentyp (`Single` oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)), aber nicht beide `Single` (Hinweis `Decimal` ist kein Gleit Komma Datentyp).|`Double`|  
  
 Wenn ein Ausdruck zu " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird er als 0 (null) behandelt.  
  
## <a name="overloading"></a>Überladen  
 Der `*`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet den `*`-Operator, um zwei Zahlen zu multiplizieren. Das Ergebnis ist das Produkt der beiden-Operanden.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
