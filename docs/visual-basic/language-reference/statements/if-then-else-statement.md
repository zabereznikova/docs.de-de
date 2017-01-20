---
title: "If...Then...Else Statement (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ElseIf"
  - "vb.Then"
  - "vb.If"
  - "vb.EndIf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ElseIf statement, If...Then...Else"
  - "Then statement, If...Then...Else"
  - "control flow, branching"
  - "execution, conditional"
  - "TypeOf...Is expression, and If...Then...Else statements"
  - "If...Then...Else statements"
  - "If statement, If...Then...Else"
  - "If statement"
  - "Is operator [Visual Basic], in If...Then...Else statements"
  - "If Operator [Visual Basic]"
  - "branching, conditional"
  - "IIf function, and If...Then...Else statements"
  - "Else statement [Visual Basic]"
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# If...Then...Else Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.  
  
## Syntax  
  
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
  
## Teile  
 `condition`  
 Erforderlich.  Ausdruck.  Muss `True` oder `False` sein oder einen Datentyp ergeben, der implizit in `Boolean` konvertiert werden kann.  
  
 Wenn der Ausdruck eine Variable [Auf NULL festgelegt werden](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` ist, die an [Nichts](../../../visual-basic/language-reference/nothing.md) ergibt, wird die Bedingung behandelt, als ob der Ausdruck nicht `True` ist, und der `Else`\-Block wird ausgeführt.  
  
 `Then`  
 Bei einzeiliger Syntax erforderlich, bei mehrzeiliger Syntax optional.  
  
 `statements`  
 Dies ist optional.  Eine oder mehrere Anweisungen nach `If`...`Then`, die ausgeführt werden, wenn `condition` `True` ist.  
  
 `elseifcondition`  
 Erforderlich, wenn `ElseIf` vorhanden ist.  Ausdruck.  Muss `True` oder `False` sein oder einen Datentyp ergeben, der implizit in `Boolean` konvertiert werden kann.  
  
 `elseifstatements`  
 Dies ist optional.  Eine oder mehrere Anweisungen nach `ElseIf`...`Then`, die ausgeführt werden, wenn `elseifcondition` `True` ist.  
  
 `elsestatements`  
 Dies ist optional.  Eine oder mehrere Anweisungen, die ausgeführt werden, wenn kein vorheriger `condition`\-Ausdruck oder `elseifcondition`\-Ausdruck `True` ist.  
  
 `End If`  
 Beendet den `If`...`Then`...`Else`\-Block.  
  
## Hinweise  
  
## Mehrzeilige Syntax  
 Wenn eine `If`...`Then`...`Else`\-Anweisung auftritt, wird `condition` getestet.  Wenn `condition` `True` ist, werden die Anweisungen nach `Then` ausgeführt.  Wenn `condition` `False` ist, werden alle `ElseIf`\-Anweisungen \(sofern vorhanden\) nacheinander ausgewertet.  Sobald ein Wert für `elseifcondition` `True` ergibt, werden die Anweisungen ausgeführt, die unmittelbar auf das zugehörige `ElseIf` folgen.  Wenn keine `elseifcondition` `True` ist oder wenn keine `ElseIf`\-Anweisungen vorhanden sind, werden die Anweisungen nach `Else` ausgeführt.  Nach der Ausführung der Anweisungen nach `Then`, `ElseIf` oder `Else` wird die Anweisung nach `End If` ausgeführt.  
  
 Die `ElseIf`\-Klausel und die `Else`\-Klausel sind optional.  Sie können so viele `ElseIf`\-Klauseln, wie Sie möchten, in einer `If`...`Then`...`Else`\-Anweisung haben, aber keine `ElseIf`\-Klausel darf nach einer `Else`\-Klausel erscheinen.  `If`...`Then`...`Else`\-Anweisungen können ineinander geschachtelt werden.  
  
 Bei mehrzeiliger Syntax muss die `If`\-Anweisung die einzige Anweisung in der ersten Zeile sein.  Von den Anweisungen `ElseIf`, `Else`und `End If` kann nur eine Zeilenmarke stehen.  Der `If`...`Then`...`Else`\-Block muss mit einer `End If`\-Anweisung enden.  
  
> [!TIP]
>  Die [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) kann besonders in Situationen sinnvoll sein, in denen ein einzelner Ausdruck mit verschiedenen möglichen Werten ausgewertet wird.  
  
## Einzeilige Syntax  
 Die einzeilige Syntax bietet sich bei einfachen, kurzen Tests an.  Die mehrzeilige Syntax ist dagegen strukturierter und flexibler und kann in der Regel leichter gelesen, gepflegt und debuggt werden.  
  
 Was auf das `Then`\-Schlüsselwort folgt, wird überprüft, um festzustellen, ob eine Anweisung ein einzeiliges `If` ist.  Wenn in derselben Zeile auf `Then` etwas anderes als ein Kommentar folgt, wird die Anweisung als einzeilige `If`\-Anweisung behandelt.  Wenn `Then` nicht vorhanden ist, muss es sich um den Anfang einer mehrzeiligen `If`...`Then`...`Else`\-Anweisung handeln.  
  
 In der einzeiligen Syntax können mehrere Anweisungen als Ergebnis einer `If`...`Then`\-Entscheidung ausgeführt werden.  Alle Anweisungen müssen sich in derselben Zeile befinden und durch Doppelpunkt getrennt werden.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der mehrzeiligen Syntax der `If`...`Then`...`Else`\-Anweisung.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## Beispiel  
 Das folgende Beispiel enthält geschachtelte `If`...`Then`...`Else`\-Anweisungen.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der einzeiligen Syntax.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>   
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Decision Structures](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [If Operator](../../../visual-basic/language-reference/operators/if-operator.md)