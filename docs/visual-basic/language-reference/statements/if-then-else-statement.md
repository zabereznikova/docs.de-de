---
title: If...Then...Else-Anweisung (Visual Basic)
ms.date: 04/16/2018
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
ms.openlocfilehash: aeffdc842730a1be8160cd8db8e4c2aa849e94cc
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201728"
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else-Anweisung (Visual Basic)
Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
' Multiline syntax:  
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

## <a name="quick-links-to-example-code"></a>Quicklinks zum Beispielcode

Dieser Artikel enthält mehrere Beispiele, wird von zeigen der `If`... `Then`... `Else` Anweisung:

* [Mehrzeilige Attributsyntax-Beispiel](#multi-line)
* [Geschachtelte Attributsyntax-Beispiel](#nested)
* [Einzeilige Attributsyntax-Beispiel](#single-line)

## <a name="parts"></a>Teile  
 `condition`  
 Erforderlich. -Ausdruck. Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.  
  
 Wenn der Ausdruck ist eine [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` Variable, die sich ergibt [nichts](../../../visual-basic/language-reference/nothing.md), die Bedingung wird behandelt, als ob der Ausdruck ist `False` und `Else` Block wird ausgeführt.  
  
 `Then`  
 In der Syntax einzeilige erforderlich. in der mehrzeiligen Syntax optional.  
  
 `statements`  
 Dies ist optional. Eine oder mehrere Anweisungen nach `If`... `Then` ausgeführt werden, wenn `condition` ergibt `True`.  
  
 `elseifcondition`  
 Erforderlich, wenn `ElseIf` vorhanden ist. -Ausdruck. Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.  
  
 `elseifstatements`  
 Dies ist optional. Eine oder mehrere Anweisungen nach `ElseIf`... `Then` ausgeführt werden, wenn `elseifcondition` ergibt `True`.  
  
 `elsestatements`  
 Dies ist optional. Eine oder mehrere Anweisungen, die ausgeführt werden, wenn kein vorheriges `condition` oder `elseifcondition` Ausdruck wird zu `True`.  
  
 `End If`  
 Beendet die mehrzeilige Version des `If`... `Then`... `Else` Block.  
  
## <a name="remarks"></a>Hinweise  
  
### <a name="multiline-syntax"></a>Multiline-syntax  
 Wenn ein `If`... `Then`... `Else` -Anweisung gefunden, `condition` getestet wird. Wenn `condition` ist `True`, die nachfolgenden Anweisungen `Then` ausgeführt werden. Wenn `condition` ist `False`, die jeweils `ElseIf` Anweisung (sofern vorhanden) wird in der Reihenfolge ausgewertet. Wenn eine `True` `elseifcondition` gefunden wird, wird die Anweisungen, die direkt nach der zugeordneten `ElseIf` ausgeführt werden. Wenn kein `elseifcondition` ergibt `True`, oder es sind keine `ElseIf` Anweisungen, die nachfolgenden Anweisungen `Else` ausgeführt werden. Nach dem Ausführen der folgenden Anweisungen `Then`, `ElseIf`, oder `Else`, Ausführung wird fortgeführt, mit der Anweisung nach `End If`.  
  
 Die `ElseIf` und `Else` Klauseln sind optional. Sie haben so viele `ElseIf` Klauseln, wie Sie möchten in einer `If`... `Then`... `Else` -Anweisung, jedoch keine `ElseIf` -Klausel kann nach dem erscheinen einer `Else` Klausel. `If`... `Then`... `Else` -Anweisungen können ineinander geschachtelt werden.  
  
 In der mehrzeiligen Syntax der `If` Anweisung muss die einzige Anweisung in der ersten Zeile sein. Die `ElseIf`, `Else`, und `End If` Anweisungen können nur von der Bezeichnung einer Zeile stehen. Die `If`... `Then`... `Else` Block mit Enden einer `End If` Anweisung.  
  
> [!TIP]
>  Die [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) kann mehr hilfreich sein, wenn Sie einen einzelnen Ausdruck auswerten, die mehrere mögliche Werte hat.  
  
### <a name="single-line-syntax"></a>Einzeilige syntax  
 Sie können die Syntax für einzeilige für eine einzelne Bedingung mit Code ausgeführt werden, wenn es "true" ist. Allerdings wird die Syntax mehrere Zeilen Struktur und Flexibilität bietet und ist einfacher zu lesen, verwalten und Debuggen.  
  
 Nachfolgend die `Then` Schlüsselwort wird untersucht, um zu bestimmen, ob eine Anweisung mit einem einzeiligen ist `If`. Wenn etwas anderes als ein Kommentar angezeigt, nach dem wird `Then` in der gleichen Zeile wird die Anweisung als einem einzeiligen behandelt `If` Anweisung. Wenn `Then` nicht vorhanden ist, muss er den Anfang einer Zeile `If`... `Then`... `Else`.  
  
 In der Syntax einzeilige haben Sie mehrere Anweisungen, die als Ergebnis der Ausführung einer `If`... `Then` Entscheidung. Alle Anweisungen in der gleichen Zeile befinden müssen, und durch Doppelpunkte getrennt werden.  

## <a name="multiline-syntax-example"></a>Mehrzeilige Attributsyntax-Beispiel

<a name="multi-line"></a>
 
 Das folgende Beispiel veranschaulicht die Verwendung der Syntax für den mehrzeiligen der `If`... `Then`... `Else` Anweisung.  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Geschachtelte Attributsyntax-Beispiel

<a name="nested"></a>

 Das folgende Beispiel enthält geschachtelte `If`... `Then`... `Else` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Einzeilige Attributsyntax-Beispiel
  
<a name="single-line"></a> Das folgende Beispiel veranschaulicht die Verwendung der Syntax einzeilige.  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Entscheidungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)
