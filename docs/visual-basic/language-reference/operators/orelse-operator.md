---
title: "OrElse Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "OrElse"
  - "vb.OrElse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "short-circuiting"
  - "operators [Visual Basic], short-circuiting"
  - "operators [Visual Basic], disjunction"
  - "short-circuit evaluation"
  - "OrElse operator [Visual Basic]"
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# OrElse Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Führt eine inklusive logische Kurzschlussdisjunktion an zwei Ausdrücken aus.  
  
## Syntax  
  
```  
  
result = expression1 OrElse expression2  
```  
  
## Teile  
 `result`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck.  
  
 `expression1`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck.  
  
 `expression2`  
 Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck.  
  
## Hinweise  
 Eine logische Operation wird als *Kurzschlussoperation* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig von dem Ergebnis eines anderen Ausdrucks umgehen kann.  Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis der Operation bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da dieser das Endergebnis nicht ändern kann.  Kurzschlussoperationen können zu einer Leistungssteigerung führen, wenn der umgangene Ausdruck sehr komplex ist oder Prozeduraufrufe enthält.  
  
 Wenn einer der beiden oder beide Ausdrücke `True` ergeben, hat `result` den Wert `True`.  Die folgende Tabelle veranschaulicht, wie `result` bestimmt wird.  
  
|Wert von `expression1`|Und `expression2` gleich|hat `result` den Wert|  
|----------------------------|------------------------------|---------------------------|  
|`True`|\(nicht ausgewertet\)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## Datentypen  
 Der Operator `OrElse` wird nur für den [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) definiert.  Visual Basic konvertiert jeden Operanden je nach Bedarf in `Boolean`\-Werte und führt die Operation ganz als `Boolean` aus.  Wenn Sie das Ergebnis einem numerischen Typ zuweisen, konvertiert Visual Basic es vom `Boolean`\-Typ in diesen Typ.  Dies kann zu unerwartetem Verhalten führen.  Bei der Konvertierung in `Integer` ergibt `5 OrElse 12` z. B. `–1`.  
  
## Überladen  
 Der [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) und der [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) können *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Das Überladen des Operators `Or` und des Operators `IsTrue` beeinflusst das Verhalten des Operators `OrElse`.  Wenn im Code `OrElse` für eine Klasse oder Struktur verwendet wird, die `Or` und `IsTrue` überlädt, müssen Sie das neu definierte Verhalten der Operatoren kennen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird mit dem Operator `OrElse` an zwei Ausdrücken eine logische Disjunktion ausgeführt.  Das Ergebnis ist ein `Boolean`\-Wert, der darstellt, ob einer der beiden Ausdrücke **True** ist.  Wenn der erste Ausdruck `True` ist, wird der zweite nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 Durch das vorangehende Beispiel werden die Ergebnisse `True`, `True` bzw. `False` erzeugt.  Bei der Berechnung von `firstCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste Ausdruck bereits `True` ist.  Der zweite Ausdruck wird jedoch bei der Berechnung von `secondCheck` ausgewertet.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `If`...`Then`\-Anweisung mit zwei Prozeduraufrufen dargestellt.  Wenn der erste Aufruf `True` zurückgibt, wird die zweite Prozedur nicht aufgerufen.  Dies kann zu unerwarteten Ergebnissen führen, wenn die zweite Prozedur wichtige Aufgaben ausführt, die bei Ausführung dieses Codeabschnitts stets ausgeführt werden müssen.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## Siehe auch  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md)   
 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)