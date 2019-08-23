---
title: GOTO-Anweisung (Visual Basic)
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
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912446"
---
# <a name="goto-statement"></a>GoTo-Anweisung
Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Segment  
 `line`  
 Erforderlich. Eine beliebige Zeilen Bezeichnung.  
  
## <a name="remarks"></a>Hinweise  
 Die `GoTo` -Anweisung kann nur an Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird. Die Linie muss über eine Zeilen Bezeichnung verfügen `GoTo` , auf die verwiesen werden kann. Weitere Informationen finden Sie unter [Vorgehensweise: Bezeichnungs](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)Anweisungen.  
  
> [!NOTE]
> `GoTo`-Anweisungen können das Lesen und Verwalten des Codes erschweren. Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur. Weitere Informationen finden Sie unter [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Sie können keine- `GoTo` Anweisung verwenden, um eine Verzweigung außerhalb eines `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, oder`Using`... `End Using` Konstruktion in eine Bezeichnung in.  
  
## <a name="branching-and-try-constructions"></a>Verzweigungen und Versuchs Konstruktionen  
 In einer `Try`... `Catch`... die folgenden Regeln gelten für die Verzweigung mit der `GoTo` -Anweisung. `Finally`  
  
|Block oder Region|Verzweigungen von außerhalb|Verzweigungen aus innerhalb|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`Baustein|Nur aus einem `Catch` Block desselben Baus <sup>1</sup>|Nur für die gesamte Konstruktion|  
|`Catch`Baustein|Nie zulässig|Nur für die gesamte Konstruktion oder den `Try` Block der gleichen Konstruktion <sup>1</sup>|  
|`Finally`Baustein|Nie zulässig|Nie zulässig|  
  
 <sup>1..</sup> `Try`. `Catch`... die Konstruktion ist in einer anderen geschachtelt, ein `Catch` Block kann `Try` in den Block auf der eigenen Schachtelungs Ebene, aber `Try` nicht in einen anderen Block verzweigen. `Finally` `Try`Ein... `Catch`... die Konstruktion muss vollständig in einem `Try` - `Catch` oder-Block der Konstruktion enthalten sein, in der Sie geschachtelt ist. `Finally`  
  
 Die folgende Abbildung zeigt eine `Try` in einer anderen geschachtelte Konstruktion. Verschiedene Verzweigungen zwischen den Blöcken der beiden Konstruktionen werden als gültig oder ungültig angegeben.  
  
 ![Grafisches Diagramm zum Branchen in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `GoTo` -Anweisung verwendet, um Zeilen Bezeichnungen in einer-Prozedur zu verzweigen.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch

- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
