---
title: OrElse-Operator
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
ms.openlocfilehash: 3095a11523eeb8ec531c7f312fca74d2a070c92f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401406"
---
# <a name="orelse-operator-visual-basic"></a>OrElse-Operator (Visual Basic)
Führt eine kurze, inklusive logische Disjunktion für zwei Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Bestandteile  
 `result`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
 `expression1`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
 `expression2`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann. Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.  
  
 Wenn mindestens einer der Ausdrücke als ausgewertet wird `True` , `result` ist `True` . In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` gleich |Und `expression2` ist|Der Wert von `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(nicht ausgewertet)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Der- `OrElse` Operator ist nur für den [booleschen Datentyp](../data-types/boolean-data-type.md)definiert. Visual Basic konvertiert jeden Operanden nach Bedarf in, `Boolean` bevor der Ausdruck ausgewertet wird. Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass zu `False` `0` und `True` wird `-1` .
Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Überladen  
 Der [OR-Operator](or-operator.md) und der [IsTrue-Operator](istrue-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das überladen `Or` der `IsTrue` Operatoren und wirkt sich auf das Verhalten des `OrElse` Operators aus. Wenn Ihr Code `OrElse` für eine Klasse oder Struktur verwendet, die und überlastet `Or` `IsTrue` , sollten Sie sicher sein, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der- `OrElse` Operator verwendet, um eine logische Disjunktion für zwei Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob einer der beiden Ausdrücke True ist. Wenn der erste Ausdruck ist `True` , wird der zweite nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 Das vorangehende Beispiel erzeugt die Ergebnisse von `True` , `True` `False` bzw. Bei der Berechnung von `firstCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste bereits vorhanden ist `True` . Der zweite Ausdruck wird jedoch in der Berechnung von ausgewertet `secondCheck` .  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `If` ...-Anweisung, die `Then` zwei Prozedur Aufrufe enthält. Wenn der erste Aufruf zurückgegeben wird `True` , wird die zweite Prozedur nicht aufgerufen. Dies kann zu unerwarteten Ergebnissen führen, wenn die zweite Prozedur wichtige Aufgaben durchführt, die immer ausgeführt werden sollten, wenn dieser Code Abschnitt ausgeführt wird.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Logische/bitweise Operatoren (Visual Basic)](logical-bitwise-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Or-Operator](or-operator.md)
- [IsTrue-Operator](istrue-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
