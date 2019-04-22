---
title: '\-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 1753199e2ecf3f156b90d8c0a5cacd672397260d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828702"
---
# <a name="-operator-visual-basic"></a>\-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt ein ganzzahliges Ergebnis.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Teile  
 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der ganzzahlige Quotient aus `expression1` geteilt durch `expression2`, der Rest wird verworfen, und nur den ganzzahlige Teil beibehalten. Dies bezeichnet man als *Abschneiden*.  
  
 Der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt zurück, der volle Quotient, der den Rest in der Bruchteil den Teil enthält.  
  
## <a name="remarks"></a>Hinweise  
 Ausführen der Division Visual Basic-Versuche vor dem Konvertieren Sie einen numerischen Gleitkommaausdruck, `Long`. Wenn `Option Strict` ist `On`, tritt ein Compilerfehler auf. Wenn `Option Strict` ist `Off`, <xref:System.OverflowException> ist möglich, wenn der Wert außerhalb des Bereichs von ist das [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md). Die Konvertierung in `Long` kann auch *Banker rounding*. Weitere Informationen finden Sie unter "Nachkommastellen" in [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Wenn `expression2` ergibt 0 (null), die `\` löst der Operator ein <xref:System.DivideByZeroException> Ausnahme. Dies gilt auch für alle numerischen Datentypen der Operanden.  
  
> [!NOTE]
>  Die `\` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `\` Operator, um eine Ganzzahldivision ausgeführt. Das Ergebnis ist eine ganze Zahl, die den Quotienten ganze Zahl, der zwei Operanden, mit der Rest verworfen darstellt.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Die Ausdrücke im vorhergehenden Beispiel geben die Werte von 2, 3, 33 und-22, bzw. zurück.  
  
## <a name="see-also"></a>Siehe auch

- [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
