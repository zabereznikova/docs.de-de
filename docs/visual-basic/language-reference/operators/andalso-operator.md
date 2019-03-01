---
title: AndAlso-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 5ba8be5051d0723fd2654b9733933cd434ac3ac5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965188"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso-Operator (Visual Basic)
Führt eine verkürzte logischen Konjunktion zweier Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`result`|Erforderlich. Beliebiger `Boolean` -Ausdruck. Das Ergebnis ist die `Boolean` Ergebnis des Vergleichs zwischen zwei Ausdrücken.|  
|`expression1`|Erforderlich. Beliebiger `Boolean` -Ausdruck.|  
|`expression2`|Erforderlich. Beliebiger `Boolean` -Ausdruck.|  
  
## <a name="remarks"></a>Hinweise  
 Eine logische Operation gilt *kurzschließen* Wenn der kompilierte Code die Auswertung eines Ausdrucks je nach Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit zum Auswerten des zweiten Ausdrucks, da das endgültige Ergebnis nicht mehr ändern können. Das kurzschließen kann die Leistung verbessern, wenn der Ausdruck Umgangene komplex ist oder Prozeduraufrufe enthält.  
  
 Wenn beide Ausdrücke `True`, `result` ist `True`. In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(nicht ausgewertet)|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Die `AndAlso` Operator ist definiert, nur für die [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic konvertiert alle Operanden nach Bedarf `Boolean` und führt den Vorgang, die vollständig in `Boolean`. Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ. Dies kann zu unerwartetem Verhalten führen. Z. B. `5 AndAlso 12` führt `–1` bei der Konvertierung in `Integer`.  
  
## <a name="overloading"></a>Überladen  
 Die [und Operator](../../../visual-basic/language-reference/operators/and-operator.md) und [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur des Verhaltens neu definiert, wenn ein Operand den Typ des, hat Klasse oder Struktur. Das Überladen der `And` und `IsFalse` Operatoren beeinflusst das Verhalten von der `AndAlso` Operator. Wenn Ihr Code verwendet `AndAlso` für eine Klasse oder Struktur, die Überladungen `And` und `IsFalse`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AndAlso` Operator, um eine logische Konjunktion zweier Ausdrücke ausgeführt. Das Ergebnis ist eine `Boolean` Wert, der angibt, ob die gesamte verbundene Ausdruck true ist "true". Wenn der erste Ausdruck `False`, das zweite wird nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 Im vorherige Beispiel erzeugt die Ergebnisse der `True`, `False`, und `False`bzw. Bei der Berechnung des `secondCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `False`. Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung des `thirdCheck`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `Function` Prozedur, die für einen bestimmten Wert zwischen den Elementen eines Arrays sucht. Wenn das Array leer ist oder wenn die Länge des Arrays überschritten wurde, die `While` -Anweisung ist nicht das Array-Element für den zu suchenden Wert testen.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Siehe auch
- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And-Operator](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
