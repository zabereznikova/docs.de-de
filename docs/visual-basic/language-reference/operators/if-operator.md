---
title: "If Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.IfOperator"
  - "IfOperator"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ternary operators"
  - "conditional execution"
  - "If expressions [Visual Basic]"
  - "conditional operator [Visual Basic]"
  - "If Operator [Visual Basic]"
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# If Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Verwendet eine Kurzschlussauswertung, um einen von zwei Werten in Abhängigkeit von Bedingungen zurückzugeben.  Der Operator `If` kann mit drei oder zwei Argumenten aufgerufen werden.  
  
## Syntax  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## Aufruf des Operators 'If' mit drei Argumenten  
 Wenn `If` mit drei Argumenten aufgerufen wird, muss die Auswertung des ersten Arguments einen Wert ergeben, der in einen `Boolean` umgewandelt werden kann.  Dieser `Boolean`\-Wert legt fest, welches der anderen beiden Argumente ausgewertet und zurückgegeben wird.  Die folgende Liste gilt nur, wenn der Operator `If` mit drei Argumenten aufgerufen wird.  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`argument1`|Erforderlich.  `Boolean`.  Bestimmt, welches der anderen Argumente ausgewertet und zurückgegeben wird.|  
|`argument2`|Erforderlich.  `Object`.  Wird ausgewertet und zurückgegeben, wenn die Auswertung von `argument1` `True` ergibt.|  
|`argument3`|Erforderlich.  `Object`.  Ausgewertet und zurückgegeben, wenn auf `argument1``False` ausgewertet wird oder wenn `argument1` eine Variable [Auf NULL festlegbare](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` ist, die mit [Nichts](../../../visual-basic/language-reference/nothing.md)ergibt.|  
  
 Ein Operator `If`, der mit drei Argumenten aufgerufen wird, funktioniert wie eine `IIf`\-Funktion, mit dem Unterschied, dass die Kurzschlussauswertung verwendet wird.  Eine `IIf`\-Funktion wertet stets alle drei Argumente aus, während ein Operator `If` mit drei Argumenten nur zwei davon auswertet.  Das erste Argument von `If` wird ausgewertet, und das Ergebnis wird in einen `Boolean`\-Wert umgewandelt: `True` oder `False`.  Wenn der Wert `True` ist, wird `argument2` ausgewertet und der Wert zurückgegeben. `argument3` wird jedoch nicht ausgewertet.  Wenn der Wert des `Boolean`\-Ausdrucks `False` ist, wird `argument3` ausgewertet und der Wert zurückgegeben. In diesem Fall wird `argument2` nicht ausgewertet.  In den folgenden Beispielen wird die Verwendung von `If` mit drei Argumenten veranschaulicht:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/if-operator_1.vb)]  
  
 Im folgenden Beispiel wird die Bedeutung der Kurzschlussauswertung veranschaulicht.  Im Beispiel werden zwei Versuche dargestellt, die Variable `number` durch die Variable `divisor` zu teilen, es sei denn, `divisor` hat den Wert 0 \(null\).  In diesem Fall soll 0 zurückgegeben werden, und die Division soll nicht durchgeführt werden, da dies einen Laufzeitfehler zur Folge hätte.  Da der `If`\-Ausdruck die Kurzschlussauswertung verwendet, wertet er, je nach Wert des ersten Arguments, entweder das zweite oder das dritte Argument aus.  Wenn das Ergebnis des ersten Arguments True ist, ist der Divisor nicht null. Dann kann das zweite Argument ausgewertet und die Division ausgeführt werden.  Wenn das erste Argument False ergibt, wird nur das dritte Argument ausgewertet und 0 \(null\) zurückgegeben.  Wenn der Divisor 0 ist, wird daher nicht versucht, die Division durchzuführen, und es tritt kein Fehler auf.  Da `IIf` keine Kurzschlussauswertung verwendet, wird das zweite Argument auch dann ausgewertet, wenn das erste Argument den Wert False hat.  Dies verursacht einen Laufzeitfehler aufgrund einer Division durch 0.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/if-operator_2.vb)]  
  
## Aufruf des Operators 'If' mit zwei Argumenten  
 Das erste Argument von `If` kann auch weggelassen werden.  Damit kann der Operator auch mit zwei Argumenten aufgerufen werden.  Die folgende Liste gilt nur, wenn der Operator `If` mit zwei Argumenten aufgerufen wird.  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`argument2`|Erforderlich.  `Object`.  Muss ein Referenztyp oder ein Typ, der NULL\-Werte zulässt, sein.  Wird ausgewertet und zurückgegeben, wenn die Auswertung etwas anderes als `Nothing` ergibt.|  
|`argument3`|Erforderlich.  `Object`.  Wird ausgewertet und zurückgegeben, wenn die Auswertung von `argument2` `Nothing` ergibt.|  
  
 Wenn das `Boolean`\-Argument weggelassen wird, muss das erste Argument ein Referenztyp oder ein Typ, der NULL\-Werte zulässt, sein.  Wenn die Auswertung des ersten Arguments `Nothing` ergibt, wird der Wert des zweiten Arguments zurückgegeben.  In allen anderen Fällen wird der Wert des ersten Arguments zurückgegeben.  Das folgende Beispiel zeigt die Funktionsweise dieser Auswertung.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/if-operator_3.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)