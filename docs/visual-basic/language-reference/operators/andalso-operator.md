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
ms.openlocfilehash: aff4621b8f415b9441ad1edf537b9b0736892bb8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874855"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso-Operator (Visual Basic)

Führt eine kurze, logische Konjunktion zweier Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`result`|Erforderlich. Beliebiger `Boolean` -Ausdruck. Das Ergebnis ist das `Boolean` Ergebnis des Vergleichs der beiden Ausdrücke.|  
|`expression1`|Erforderlich. Beliebiger `Boolean` -Ausdruck.|  
|`expression2`|Erforderlich. Beliebiger `Boolean` -Ausdruck.|  
  
## <a name="remarks"></a>Bemerkungen  

 Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann. Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.  
  
 Wenn beide Ausdrücke als ausgewertet `True` werden, `result` ist `True` . In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` gleich |Und `expression2` ist|Der Wert von `result` ist|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(nicht ausgewertet)|`False`|  
  
## <a name="data-types"></a>Datentypen  

 Der- `AndAlso` Operator ist nur für den [booleschen Datentyp](../data-types/boolean-data-type.md)definiert. Visual Basic konvertiert jeden Operanden nach Bedarf in, `Boolean` bevor der Ausdruck ausgewertet wird. Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass zu `False` `0` und `True` wird `-1` .
Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Überladen  

 Der [and-Operator](and-operator.md) und der [IsFalse-Operator](isfalse-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das überladen `And` der `IsFalse` Operatoren und wirkt sich auf das Verhalten des `AndAlso` Operators aus. Wenn Ihr Code `AndAlso` für eine Klasse oder Struktur verwendet, die und überlastet `And` `IsFalse` , sollten Sie sicher sein, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `AndAlso` Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der gesamte zusammengefügten Ausdruck true ist. Wenn der erste Ausdruck ist `False` , wird der zweite nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 Im vorherigen Beispiel werden die Ergebnisse von `True` , `False` `False` bzw. erzeugt. Bei der Berechnung von `secondCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste bereits vorhanden ist `False` . Der zweite Ausdruck wird jedoch in der Berechnung von ausgewertet `thirdCheck` .  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine `Function` Prozedur gezeigt, die unter den Elementen eines Arrays nach einem angegebenen Wert sucht. Wenn das Array leer ist oder die Array Länge überschritten wurde, `While` testet die Anweisung das Array Element nicht mit dem Suchwert.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Logische/bitweise Operatoren (Visual Basic)](logical-bitwise-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [And-Operator](and-operator.md)
- [IsFalse-Operator](isfalse-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
