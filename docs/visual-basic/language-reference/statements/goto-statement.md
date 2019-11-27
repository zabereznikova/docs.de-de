---
title: GoTo-Anweisung
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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351087"
---
# <a name="goto-statement"></a>GoTo-Anweisung
Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>-Komponente  
 `line`  
 Erforderlich Eine beliebige Zeilen Bezeichnung.  
  
## <a name="remarks"></a>Hinweise  
 Die `GoTo`-Anweisung kann nur bis Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird. Die Linie muss über eine Zeilen Bezeichnung verfügen, auf die `GoTo` verweisen kann. Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> mit `GoTo`-Anweisungen kann der Code schwierig zu lesen und zu warten. Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur. Weitere Informationen finden Sie unter [Ablauf Steuerung](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Eine `GoTo`-Anweisung kann nicht verwendet werden, um von außerhalb eines `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`oder `Using`...`End Using` Erstellung zu einer Bezeichnung in zu verzweigen.  
  
## <a name="branching-and-try-constructions"></a>Verzweigungen und Versuchs Konstruktionen  
 Innerhalb einer `Try`...`Catch`...`Finally` Konstruktion werden die folgenden Regeln für die Verzweigung mit der `GoTo`-Anweisung angewendet.  
  
|Block oder Region|Verzweigungen von außerhalb|Verzweigungen aus innerhalb|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`-Block|Nur aus einem `Catch` Block desselben Baus <sup>1</sup>|Nur für die gesamte Konstruktion|  
|`Catch`-Block|Nie zulässig|Nur für die gesamte Konstruktion oder den `Try` Block desselben Aufbaus <sup>1</sup>|  
|`Finally`-Block|Nie zulässig|Nie zulässig|  
  
 <sup>1</sup> wenn eine `Try`...`Catch`...`Finally` Konstruktion in einer anderen geschachtelt ist, kann ein `Catch` Block in den `Try` Block auf der eigenen Schachtelungs Ebene verzweigt werden, aber nicht in einen anderen `Try` Block. Eine geschachtelte `Try`...`Catch`...`Finally` Konstruktion muss vollständig in einem `Try` oder `Catch` Block der Konstruktion enthalten sein, in der Sie geschachtelt ist.  
  
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
