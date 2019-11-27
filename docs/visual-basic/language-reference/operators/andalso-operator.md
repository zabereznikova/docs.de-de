---
title: AndAlso-Operator
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
ms.openlocfilehash: b3801c7e05142e1bc793e3c9d49a6f6991756f9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350235"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso-Operator (Visual Basic)
Führt eine kurze, logische Konjunktion zweier Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`result`|Erforderlich Beliebiger `Boolean` -Ausdruck. Das Ergebnis ist das `Boolean` Ergebnis des Vergleichs der beiden Ausdrücke.|  
|`expression1`|Erforderlich Beliebiger `Boolean` -Ausdruck.|  
|`expression2`|Erforderlich Beliebiger `Boolean` -Ausdruck.|  
  
## <a name="remarks"></a>Hinweise  
 Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann. Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.  
  
 Wenn beide Ausdrücke als `True`ausgewertet werden, wird `result` `True`. In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert von `result` ist|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(nicht ausgewertet)|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Der `AndAlso`-Operator ist nur für den [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)definiert. Visual Basic konvertiert jeden Operanden nach Bedarf in `Boolean`, bevor der Ausdruck ausgewertet wird. Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass `False` `0` werden und `True` `-1`wird.
Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Überladen  
 Der [and-Operator](../../../visual-basic/language-reference/operators/and-operator.md) und der [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen der Operatoren `And` und `IsFalse` wirkt sich auf das Verhalten des `AndAlso` Operators aus. Wenn Ihr Code `AndAlso` für eine Klasse oder Struktur verwendet, die `And` und `IsFalse`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `AndAlso`-Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der gesamte zusammengefügten Ausdruck true ist. Wenn der erste Ausdruck `False`ist, wird der zweite nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 Das vorangehende Beispiel erzeugt die Ergebnisse der `True`, `False`und `False`. Bei der Berechnung der `secondCheck`wird der zweite Ausdruck nicht ausgewertet, da der erste bereits `False`ist. Der zweite Ausdruck wird jedoch in der Berechnung der `thirdCheck`ausgewertet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Function` Prozedur gezeigt, die in den Elementen eines Arrays nach einem angegebenen Wert sucht. Wenn das Array leer ist oder die Array Länge überschritten wurde, testet die `While`-Anweisung das Array Element nicht mit dem Suchwert.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And-Operator](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
