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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581815"
---
# <a name="goto-statement"></a>GoTo-Anweisung
Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Segment  
 `line`  
 Erforderlich. Eine beliebige Zeilen Bezeichnung.  
  
## <a name="remarks"></a>Hinweise  
 Die `GoTo`-Anweisung kann nur bis Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird. Die Linie muss über eine Zeilen Bezeichnung verfügen, auf die `GoTo` verweisen kann. Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> mit `GoTo`-Anweisungen kann der Code schwierig zu lesen und zu warten. Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur. Weitere Informationen finden Sie unter [Ablauf Steuerung](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Eine `GoTo`-Anweisung kann nicht verwendet werden, um außerhalb eines `For` zu verzweigen... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 oder 2... 3 Konstruktion in eine Bezeichnung in.  
  
## <a name="branching-and-try-constructions"></a>Verzweigungen und Versuchs Konstruktionen  
 Innerhalb einer `Try`... `Catch`... `Finally` Konstruktion gelten die folgenden Regeln für die Verzweigung mit der `GoTo`-Anweisung.  
  
|Block oder Region|Verzweigungen von außerhalb|Verzweigungen aus innerhalb|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`-Block|Nur aus einem `Catch` Block desselben Baus <sup>1</sup>|Nur für die gesamte Konstruktion|  
|`Catch`-Block|Nie zulässig|Nur für die gesamte Konstruktion oder den `Try` Block desselben Aufbaus <sup>1</sup>|  
|`Finally`-Block|Nie zulässig|Nie zulässig|  
  
 <sup>1</sup> , wenn ein `Try`... `Catch`... `Finally` Konstruktion in einer anderen geschachtelt ist, kann ein `Catch` Block in den `Try` Block auf der eigenen Schachtelungs Ebene, aber nicht in einen anderen `Try` Block verzweigen. Ein-`Try`... `Catch`... `Finally` Konstruktion muss vollständig in einem `Try` oder `Catch` Block der Konstruktion enthalten sein, in der Sie geschachtelt ist.  
  
 Die folgende Abbildung zeigt eine `Try` in einer anderen geschachtelte Konstruktion. Verschiedene Verzweigungen zwischen den Blöcken der beiden Konstruktionen werden als gültig oder ungültig angegeben.  
  
 ![Grafisches Diagramm der Verzweigung in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `GoTo`-Anweisung verwendet, um Zeilen Bezeichnungen in einer-Prozedur zu verzweigen.  
  
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
