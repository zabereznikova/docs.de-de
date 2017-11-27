---
title: If...Then...Else-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else-Anweisung (Visual Basic)
Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
' Multiple-line syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  
  
## <a name="parts"></a>Teile  
 `condition`  
 Erforderlich. Ausdruck. Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.  
  
 Wenn der Ausdruck ist eine [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` Variable, der ergibt [nichts](../../../visual-basic/language-reference/nothing.md), die Bedingung wird behandelt, als ob der Ausdruck ist `True`, und die `Else` -Block ausgeführt.  
  
 `Then`  
 In der Syntax für einzeilige erforderlich; Dies ist optional in der Syntax mehrere Zeilen.  
  
 `statements`  
 Dies ist optional. Eine oder mehrere Anweisungen nach `If`... `Then` , die ausgeführt werden, wenn `condition` ergibt `True`.  
  
 `elseifcondition`  
 Erforderlich, wenn `ElseIf` vorhanden ist. Ausdruck. Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.  
  
 `elseifstatements`  
 Dies ist optional. Eine oder mehrere Anweisungen nach `ElseIf`... `Then` , die ausgeführt werden, wenn `elseifcondition` ergibt `True`.  
  
 `elsestatements`  
 Dies ist optional. Eine oder mehrere Anweisungen, die ausgeführt werden, wenn kein vorheriges `condition` oder `elseifcondition` Ausdruck wird zu `True`.  
  
 `End If`  
 Beendet die `If`... `Then`... `Else` Block.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="multiple-line-syntax"></a>Mehrzeilige Syntax  
 Wenn ein `If`... `Then`... `Else` Anweisung festgestellt wird, `condition` getestet wird. Wenn `condition` ist `True`, die nachfolgenden Anweisungen `Then` ausgeführt werden. Wenn `condition` ist `False`, die jeweils `ElseIf` Anweisung (sofern vorhanden) wird in der Reihenfolge ausgewertet. Wenn eine `True``elseifcondition` gefunden wird, werden die Anweisungen, die direkt nach der zugeordneten `ElseIf` ausgeführt werden. Wenn kein `elseifcondition` ergibt `True`, oder es sind keine `ElseIf` -Anweisungen, die nachfolgenden Anweisungen `Else` ausgeführt werden. Nach dem Ausführen der folgenden Anweisungen `Then`, `ElseIf`, oder `Else`, die Ausführung wird fortgeführt, mit der folgenden Anweisung `End If`.  
  
 Die `ElseIf` und `Else` Klauseln sind optional. Sie können beliebig viele `ElseIf` Klauseln, wie Sie möchten, dass in einer `If`... `Then`... `Else` -Anweisung, jedoch keine `ElseIf` -Klausel kann angezeigt werden, nachdem ein `Else` Klausel. `If`... `Then`... `Else` -Anweisungen können ineinander geschachtelt werden.  
  
 In der Syntax mehrere Zeilen der `If` Anweisung muss die einzige Anweisung in der ersten Zeile sein. Die `ElseIf`, `Else`, und `End If` Anweisungen können nur von einer zeilenbezeichnung vorangestellt werden. Die `If`... `Then`... `Else` Block mit Enden einer `End If` Anweisung.  
  
> [!TIP]
>  Die [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) kann nützlicher sein, wenn Sie einen einzelnen Ausdruck auswerten, die mehrere mögliche Werte hat.  
  
## <a name="single-line-syntax"></a>Einzeilige-Syntax  
 Sie können die einzeilige Syntax für kurze, einfache Tests verwenden. Allerdings wird die Syntax mehrere Zeilen Struktur und flexibler und ist in der Regel einfacher zu lesen, zu verwalten und zu debuggen.  
  
 Welche folgt die `Then` Schlüsselwort wird untersucht, um zu bestimmen, ob eine Anweisung eine einzeilige `If`. Wenn etwas anderes als ein Kommentar, nach dem angezeigt `Then` in der gleichen Zeile wird die Anweisung als eine einzeilige behandelt `If` Anweisung. Wenn `Then` nicht vorhanden ist, muss er den Anfang einer mehrzeiligen `If`... `Then`... `Else`.  
  
 In der Syntax einzeilige können mehrere Anweisungen, die als Ergebnis der Ausführung einer `If`... `Then` Entscheidung. Alle Anweisungen müssen in der gleichen Zeile und durch Doppelpunkte getrennt werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der Syntax mehrere Zeilen für die `If`... `Then`... `Else` Anweisung.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält geschachtelte `If`... `Then`... `Else` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der Syntax einzeilige.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Entscheidungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)
