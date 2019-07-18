---
title: OrElse-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860144"
---
# <a name="orelse-operator-visual-basic"></a>OrElse-Operator (Visual Basic)
Führt eine verkürzte einschließende logischen Disjunktion zweier Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
 `expression1`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
 `expression2`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Eine logische Operation gilt *kurzschließen* Wenn der kompilierte Code die Auswertung eines Ausdrucks je nach Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit zum Auswerten des zweiten Ausdrucks, da das endgültige Ergebnis nicht mehr ändern können. Das kurzschließen kann die Leistung verbessern, wenn der Ausdruck Umgangene komplex ist oder Prozeduraufrufe enthält.  
  
 Wenn eine oder beide Ausdrücke `True`, `result` ist `True`. In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(nicht ausgewertet)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Die `OrElse` Operator ist definiert, nur für die [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic konvertiert alle Operanden nach Bedarf `Boolean` vor der Auswertung des Ausdrucks. Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ, `False` wird `0` und `True` wird `-1`.
Weitere Informationen finden Sie unter [booleschen Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions)
  
## <a name="overloading"></a>Überladen  
 Die [oder-Operator](../../../visual-basic/language-reference/operators/or-operator.md) und [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur des Verhaltens neu definiert, wenn ein Operand den Typ dieser Klasse hat oder Struktur. Das Überladen der `Or` und `IsTrue` Operatoren beeinflusst das Verhalten von der `OrElse` Operator. Wenn Ihr Code verwendet `OrElse` für eine Klasse oder Struktur, die Überladungen `Or` und `IsTrue`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `OrElse` Operator, um die logische Disjunktion zweier Ausdrücke ausgeführt. Das Ergebnis ist eine `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke "true". Wenn der erste Ausdruck `True`, das zweite wird nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 Im vorherige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False` bzw. Bei der Berechnung des `firstCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `True`. Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung des `secondCheck`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `If`... `Then` Anweisung, die zwei Prozeduraufrufe enthält. Wenn der erste Aufruf gibt `True`, im zweite Verfahren wird nicht aufgerufen. Dies kann zu unerwarteten Ergebnissen führen, wenn das zweite Verfahren wichtige Aufgaben, die immer ausgeführt werden soll ausführt, wenn in diesem Abschnitt des Codes ausgeführt wird.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Or-Operator](../../../visual-basic/language-reference/operators/or-operator.md)
- [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
