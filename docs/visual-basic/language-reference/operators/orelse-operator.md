---
title: OrElse-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47239a1d2b5b20f2b8cacc9b9185a0f95f63dc84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="orelse-operator-visual-basic"></a>OrElse-Operator (Visual Basic)
Führt eine inklusiven logischen Disjunktion zweier Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Beliebiger `Boolean`-Ausdruck.  
  
 `expression1`  
 Erforderlich. Beliebiger `Boolean`-Ausdruck.  
  
 `expression2`  
 Erforderlich. Beliebiger `Boolean`-Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Eine logische Operation gilt als *verkürzte* Wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit, der zweite Ausdruck ausgewertet werden, da das Endergebnis nicht geändert werden kann. Verkürzte kann die Leistung verbessern, wenn der umgehen Ausdruck komplex ist oder sie Prozeduraufrufe umfasst.  
  
 Wenn eine oder beide Ausdrücke `True`, `result` ist `True`. Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(nicht ausgewertet)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Die `OrElse` Operator definiert ist, nur für die [booleschen Datentyp](./../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic konvertiert jeden Operanden nach Bedarf `Boolean` und führt den Vorgang, die vollständig in `Boolean`. Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ. Dies kann zu unerwartetem Verhalten führen. Beispielsweise `5 OrElse 12` führt `–1` bei der Konvertierung in `Integer`.  
  
## <a name="overloading"></a>Überladen  
 Die [oder-Operator](./../../visual-basic/language-reference/operators/or-operator.md) und [IsTrue-Operator](./../../visual-basic/language-reference/operators/istrue-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur ihr Verhalten definieren kann, wenn ein Operand den Typ dieser Klasse hat oder Struktur. Überladen der `Or` und `IsTrue` Operatoren wirkt sich auf das Verhalten der `OrElse` Operator. Wenn im Code verwendet `OrElse` auf eine Klasse oder Struktur, die Überladungen `Or` und `IsTrue`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](./../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `OrElse` Operator, um eine logische Disjunktion zweier Ausdrücke ausgeführt. Das Ergebnis ist ein `Boolean` Wert, der darstellt, ob eine der beiden Ausdrücke zutrifft. Wenn der erste Ausdruck ist `True`, die zweite wird nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 Das obige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False` bzw. Bei der Berechnung der `firstCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `True`. Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung der `secondCheck`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `If`... `Then` Anweisung, die zwei Prozeduraufrufe enthält. Wenn der erste Aufruf gibt `True`, im zweite Verfahren wird nicht aufgerufen. Dies kann zu unerwarteten Ergebnissen führen, wenn das zweite Verfahren wichtige Aufgaben, die immer ausgeführt werden soll ausführt, wenn dieser Abschnitt des Codes ausgeführt wird.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](./../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](./../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](./../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Or-Operator](./../../visual-basic/language-reference/operators/or-operator.md)  
 [IsTrue-Operator](./../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Logische und bitweise Operatoren in Visual Basic](./../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
