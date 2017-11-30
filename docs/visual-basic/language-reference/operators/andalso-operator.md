---
title: AndAlso-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f92f4ed226c2923c3d95a7b80db3872b7ac33dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`result`|Erforderlich. Beliebiger `Boolean`-Ausdruck. Das Ergebnis ist die `Boolean` Ergebnis des Vergleichs von zwei Ausdrücken.|  
|`expression1`|Erforderlich. Beliebiger `Boolean`-Ausdruck.|  
|`expression2`|Erforderlich. Beliebiger `Boolean`-Ausdruck.|  
  
## <a name="remarks"></a>Hinweise  
 Eine logische Operation gilt als *verkürzte* Wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit, der zweite Ausdruck ausgewertet werden, da das Endergebnis nicht geändert werden kann. Verkürzte kann die Leistung verbessern, wenn der umgehen Ausdruck komplex ist oder sie Prozeduraufrufe umfasst.  
  
 Wenn beide Ausdrücke `True`, `result` ist `True`. Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(nicht ausgewertet)|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Die `AndAlso` Operator definiert ist, nur für die [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic konvertiert jeden Operanden nach Bedarf `Boolean` und führt den Vorgang, die vollständig in `Boolean`. Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ. Dies kann zu unerwartetem Verhalten führen. Beispielsweise `5 AndAlso 12` führt `–1` bei der Konvertierung in `Integer`.  
  
## <a name="overloading"></a>Überladen  
 Die [And-Operators](../../../visual-basic/language-reference/operators/and-operator.md) und die [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur ihr Verhalten definieren kann, wenn ein Operand den Typ dieses hat Klasse oder Struktur. Überladen der `And` und `IsFalse` Operatoren wirkt sich auf das Verhalten der `AndAlso` Operator. Wenn im Code verwendet `AndAlso` auf eine Klasse oder Struktur, die Überladungen `And` und `IsFalse`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AndAlso` Operator, um eine logische Konjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der gesamte verbundene Ausdruck true ist "true". Wenn der erste Ausdruck ist `False`, die zweite wird nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 Das obige Beispiel erzeugt die Ergebnisse der `True`, `False`, und `False`zugeordnet. Bei der Berechnung der `secondCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `False`. Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung der `thirdCheck`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `Function` Prozedur, die für einen bestimmten Wert zwischen den Elementen eines Arrays sucht. Wenn das Array leer ist oder wenn die Länge des Arrays überschritten wurde, die `While` testet Anweisung keine Arrayelements mit dem Suchwert.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [And-Operator](../../../visual-basic/language-reference/operators/and-operator.md)  
 [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
