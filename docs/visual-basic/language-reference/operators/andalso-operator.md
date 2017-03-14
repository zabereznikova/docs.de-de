---
title: "AndAlso Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AndAlso"
  - "AndAlso"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "short-circuiting"
  - "AndAlso operator"
  - "operators [Visual Basic], short-circuiting"
  - "operators [Visual Basic], conjunction"
  - "short-circuit evaluation"
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# AndAlso Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Führt eine logische Kurzschlusskonjunktion zweier Ausdrücke aus.  
  
## Syntax  
  
```  
  
result = expression1 AndAlso expression2  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`result`|Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck.  Das Ergebnis ist das `Boolean`\-Ergebnis des Vergleichs zwischen zwei Ausdrücken.|  
|`expression1`|Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck.|  
|`expression2`|Erforderlich.  Ein beliebiger `Boolean`\-Ausdruck.|  
  
## Hinweise  
 Eine logische Operation wird als *Kurzschlussoperation* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig von dem Ergebnis eines anderen Ausdrucks umgehen kann.  Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis der Operation bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da dieser das Endergebnis nicht ändern kann.  Kurzschlussoperationen können zu einer Leistungssteigerung führen, wenn der umgangene Ausdruck sehr komplex ist oder Prozeduraufrufe enthält.  
  
 Wenn beide Ausdrücke `True` ergeben, ist `result` ebenfalls `True`.  Die folgende Tabelle veranschaulicht, wie `result` bestimmt wird.  
  
||||  
|-|-|-|  
|Wert von `expression1`|Und `expression2` gleich|hat `result` den Wert|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|\(nicht ausgewertet\)|`False`|  
  
## Datentypen  
 Der Operator `AndAlso` wird nur für den [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) definiert.  Visual Basic konvertiert jeden Operanden je nach Bedarf in `Boolean`\-Werte und führt die Operation ganz als `Boolean` aus.  Wenn Sie das Ergebnis einem numerischen Typ zuweisen, konvertiert Visual Basic es vom `Boolean`\-Typ in diesen Typ.  Dies kann zu unerwartetem Verhalten führen.  Bei der Konvertierung in `Integer` ergibt `5 AndAlso 12` z. B. `–1`.  
  
## Überladen  
 Der [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) und der [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) können *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Das Überladen des Operators `And` und des Operators `IsFalse` beeinflusst das Verhalten des Operators `AndAlso`.  Wenn im Code `AndAlso` für eine Klasse oder Struktur verwendet wird, die `And` und `IsFalse` überlädt, müssen Sie das neu definierte Verhalten der Operatoren kennen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel wird mit dem Operator `AndAlso` eine logische Konjunktion zweier Ausdrücke ausgeführt.  Das Ergebnis ist ein `Boolean`\-Wert, der darstellt, ob der gesamte verbundene Ausdruck **True** ist.  Wenn der erste Ausdruck `False` ist, wird der zweite nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 Durch das vorangehende Beispiel werden die Ergebnisse `True`, `False` bzw. `False` erzeugt.  Bei der Berechnung von `secondCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste Ausdruck bereits `False` ist.  Der zweite Ausdruck wird jedoch bei der Berechnung von `thirdCheck` ausgewertet.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine `Function`\-Prozedur, die in den Elementen eines Arrays nach einem gegebenen Wert sucht.  Wenn das Array leer ist oder die zulässige Arraylänge überschritten wurde, wird das Arrayelement von der `While`\-Anweisung nicht auf den Suchwert überprüft.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## Siehe auch  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [And Operator](../../../visual-basic/language-reference/operators/and-operator.md)   
 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)