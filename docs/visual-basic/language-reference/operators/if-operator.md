---
title: If-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c553da5abf5453ba881671806b976125355c1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="if-operator-visual-basic"></a>If-Operator (Visual Basic)
Verwendet kurzschlussauswertung bedingt einen von zwei Werten zurück. Die `If` Operator kann mit drei Argumenten oder mit zwei Argumenten aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Wenn-Operator mit drei Argumenten aufgerufen.  
 Wenn `If` heißt mithilfe von drei Argumenten muss das erste Argument ausgewertet werden, ein Wert, der umgewandelt werden kann eine `Boolean`. Dass `Boolean` Wert wird bestimmt, welche der beiden anderen Argumente ausgewertet und zurückgegeben wird. Die folgende Liste gilt nur, wenn die `If` -Operator mit drei Argumenten aufgerufen wird.  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`argument1`|Erforderlich. `Boolean`. Bestimmt, welche Argumente um auszuwerten und zurückzugeben.|  
|`argument2`|Erforderlich. `Object`. Ausgewertet und zurückgegeben, wenn `argument1` ergibt `True`.|  
|`argument3`|Erforderlich. `Object`. Ausgewertet und zurückgegeben, wenn `argument1` ergibt `False` oder, wenn `argument1` ist ein [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` Variable, der ergibt [nichts](../../../visual-basic/language-reference/nothing.md).|  
  
 Ein `If` Operator, der mit drei Argumenten aufgerufen wird, funktioniert wie ein `IIf` Funktion identisch, verwendet jedoch kurzschlussauswertung. Ein `IIf` Funktion wertet immer alle drei Argumente, während ein `If` Operator, der drei Argumente ausgewertet werden nur zwei davon. Das erste `If` Argument ausgewertet wird und das Ergebnis wird umgewandelt in ein `Boolean` Wert `True` oder `False`. Wenn der Wert `True`, `argument2` wird ausgewertet, und sein Wert wird zurückgegeben, aber `argument3` wird nicht ausgewertet. Wenn der Wert von der `Boolean` Ausdruck ist `False`, `argument3` wird ausgewertet, und sein Wert wird zurückgegeben, aber `argument2` wird nicht ausgewertet. Die folgenden Beispiele veranschaulichen die Verwendung von `If` drei Argumente werden verwendet, wenn:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 Das folgende Beispiel veranschaulicht den Wert des kurzschlussauswertung. Das Beispiel zeigt zwei Versuche zum Unterteilen der Variable `number` Variable `divisor` außer bei `divisor` 0 (null). In diesem Fall wird 0 zurückgegeben werden soll, und nicht versucht sollte die Division ausgeführt, da ein Fehler zur Laufzeit führen würde. Da die `If` ausdrucksverwendungen kurzschlussauswertung ist, wird er der zweite oder das dritte Argument, abhängig vom Wert des ersten Arguments ausgewertet. Wenn das erste Argument auf "true" festgelegt ist, der Divisor ist nicht 0 (null) und ist das zweite Argument ausgewertet, und führen die Division sicher. Wenn das erste Argument auf "false" festgelegt ist, wird nur das dritte Argument wird ausgewertet, und eine 0 zurückgegeben. Wenn der Divisor 0 ist, ist daher kein Versuch unternommen, Durchführung der Division und tritt kein Fehler. Aber da `IIf` verwendet keine kurzschlussauswertung, das zweite Argument ausgewertet wird, selbst wenn das erste Argument auf "false" festgelegt ist. Dies bewirkt, dass ein Laufzeitfehler aufgrund einer Division durch Null.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Wenn der Operator mit zwei Argumenten aufgerufen.  
 Das erste Argument für `If` kann ausgelassen werden. Dadurch wird den Operator mit zwei Argumenten aufgerufen werden sollen. Die folgende Liste gilt nur, wenn die `If` Operator mit zwei Argumenten aufgerufen wird.  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`argument2`|Erforderlich. `Object`. Ein Verweis oder die nullable-Typ muss sein. Ausgewertet und zurückgegeben, wenn alles andere als ergibt die Auswertung `Nothing`.|  
|`argument3`|Erforderlich. `Object`. Ausgewertet und zurückgegeben, wenn `argument2` ergibt `Nothing`.|  
  
 Wenn die `Boolean` Argument ausgelassen wird, wird das erste Argument muss ein Verweis oder die nullable-Typ sein. Wenn das erste Argument ergibt `Nothing`, der Wert des zweiten Arguments zurückgegeben wird. In allen anderen Fällen wird der Wert des ersten Arguments zurückgegeben. Das folgende Beispiel veranschaulicht die Funktionsweise dieser Auswertung.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
