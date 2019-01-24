---
title: GoTo-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 729ff2a9cbeacaefdf0452a6c5868c229a8d05b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582525"
---
# <a name="goto-statement"></a>GoTo-Anweisung
Brancht ohne Bedingungen in eine angegebene Zeile in einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Segment  
 `line`  
 Erforderlich. Alle zeilenbezeichnungen.  
  
## <a name="remarks"></a>Hinweise  
 Die `GoTo` -Anweisung kann nur für Zeilen in der Prozedur, die in der es auftritt verzweigen. Die Zeile benötigen eine Zeile, die Bezeichnung `GoTo` können zu verweisen. Weitere Informationen finden Sie unter [Vorgehensweise: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  `GoTo` -Anweisungen können, dass Code schwierig zu lesen und zu verwalten. Wann immer möglich, verwenden Sie stattdessen eine Steuerelement-Struktur. Weitere Informationen finden Sie unter [Ablaufsteuerung](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Sie können keine `GoTo` Anweisung außerhalb von einer `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, oder `Using`... `End Using` Erstellung zu einer Bezeichnung in.  
  
## <a name="branching-and-try-constructions"></a>Verzweigen und versuchen Sie es Konstruktionen  
 Innerhalb einer `Try`... `Catch`... `Finally` Konstruktion die folgenden Regeln gelten zur Verzweigung mit dem `GoTo` Anweisung.  
  
|Block oder eine region|Verzweigung von außerhalb|Verzweigen Sie von innerhalb|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` Block|Nur von einem `Catch` Block, der die gleiche Konstruktion <sup>1</sup>|Nur für außerhalb der gesamten Konstruktion|  
|`Catch` Block|Nicht zulässig.|Nur für außerhalb der gesamten Konstruktion oder auf die `Try` Block, der die gleiche Konstruktion <sup>1</sup>|  
|`Finally` Block|Nicht zulässig.|Nicht zulässig.|  
  
 <sup>1</sup> sofern `Try`... `Catch`... `Finally` -Konstruktion innerhalb einer anderen geschachtelt ist eine `Catch` -Block verzweigen kann, in der `Try` Block, eine eigene Schachtelungsebene, aber nicht in einen anderen `Try` Block. Eine geschachtelte `Try`... `Catch`... `Finally` Konstruktion muss vollständig im enthalten sein, eine `Try` oder `Catch` Block von der Konstruktion, in dem sie geschachtelt ist.  
  
 Die folgende Abbildung zeigt eine `Try` Konstruktion in einer anderen geschachtelt. Verschiedene getestete Branches zwischen die beiden Konstruktionen Datenblöcke werden als gültig oder ungültig angegeben.  
  
 ![Grafisches Diagramm zum Branchen in Try-Konstrukten](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Gültige und ungültige Branches in Try-Konstrukten  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `GoTo` Branch in Zeile Bezeichnungen in einer Prozedur-Anweisung.  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
