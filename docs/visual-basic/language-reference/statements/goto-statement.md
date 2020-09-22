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
ms.openlocfilehash: 000f6754575bcce6b2d79d85541e755219aca956
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866624"
---
# <a name="goto-statement"></a>GoTo-Anweisung

Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Teil  

 `line`  
 Erforderlich. Eine beliebige Zeilen Bezeichnung.  
  
## <a name="remarks"></a>Bemerkungen  

 Die- `GoTo` Anweisung kann nur an Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird. Die Linie muss über eine Zeilen Bezeichnung verfügen, `GoTo` auf die verwiesen werden kann. Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](../../programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo` -Anweisungen können das Lesen und Verwalten des Codes erschweren. Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur. Weitere Informationen finden Sie unter [Control Flow](../../programming-guide/language-features/control-flow/index.md).  
  
 Sie können keine- `GoTo` Anweisung verwenden, um eine Verzweigung außerhalb eines...,. `For` `Next` `For Each` .. `Next` , `SyncLock` `End SyncLock` `Try` `Catch` ...,... ... `Finally` , `With` ... `End With` oder `Using` ... `End Using` in eine Bezeichnung in.  
  
## <a name="branching-and-try-constructions"></a>Verzweigungen und Versuchs Konstruktionen  

 In einer `Try` ... `Catch` ...`Finally` die folgenden Regeln gelten für die Verzweigung mit der- `GoTo` Anweisung.  
  
|Block oder Region|Verzweigungen von außerhalb|Verzweigungen aus innerhalb|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`-Block|Nur aus einem `Catch` Block desselben Baus <sup>1</sup>|Nur für die gesamte Konstruktion|  
|`Catch`-Block|Nie zulässig|Nur für die gesamte Konstruktion oder den `Try` Block der gleichen Konstruktion <sup>1</sup>|  
|`Finally`-Block|Nie zulässig|Nie zulässig|  
  
 <sup>1</sup> `Try` .. `Catch` . ...`Finally` die Konstruktion ist in einer anderen geschachtelt, ein `Catch` Block kann in den `Try` Block auf der eigenen Schachtelungs Ebene, aber nicht in einen anderen Block verzweigen `Try` . Ein `Try` ... `Catch` ...`Finally` die Konstruktion muss vollständig in einem- `Try` oder- `Catch` Block der Konstruktion enthalten sein, in der Sie geschachtelt ist.  
  
 Die folgende Abbildung zeigt eine `Try` in einer anderen geschachtelte Konstruktion. Verschiedene Verzweigungen zwischen den Blöcken der beiden Konstruktionen werden als gültig oder ungültig angegeben.  
  
 ![Grafisches Diagramm zum Branchen in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die- `GoTo` Anweisung verwendet, um Zeilen Bezeichnungen in einer-Prozedur zu verzweigen.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Do...Loop-Anweisung](do-loop-statement.md)
- [For...Next-Anweisung](for-next-statement.md)
- [For Each...Next-Anweisung](for-each-next-statement.md)
- [If...Then...Else-Anweisung](if-then-else-statement.md)
- [Select...Case-Anweisung](select-case-statement.md)
- [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md)
- [While...End While-Anweisung](while-end-while-statement.md)
- [With...End With-Anweisung](with-end-with-statement.md)
