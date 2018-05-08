---
title: Exit-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 05a65dd84a00478f52c8cd7d8b46341644512718
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exit-statement-visual-basic"></a>Exit-Anweisung (Visual Basic)
Eine Prozedur oder den Block beendet, und überträgt die Steuerung sofort an die Anweisung nach dem Prozeduraufruf oder der Blockdefinition.  
  
## <a name="syntax"></a>Syntax  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Anweisungen  
 `Exit Do`  
 Beendet sofort die `Do` wurde eine Schleife in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung nach der `Loop` Anweisung. `Exit Do` kann verwendet werden, nur innerhalb einer `Do` Schleife. Bei Verwendung in geschachtelten `Do` Schleifen `Exit Do` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene der Schachtelung.  
  
 `Exit For`  
 Beendet sofort die `For` wurde eine Schleife in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung nach der `Next` Anweisung. `Exit For` kann verwendet werden, nur innerhalb einer `For`... `Next` oder `For Each`... `Next` Schleife. Bei Verwendung in geschachtelten `For` Schleifen `Exit For` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene der Schachtelung.  
  
 `Exit Function`  
 Beendet sofort die `Function` Prozedur, in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die aufgerufen der `Function` Prozedur. `Exit Function` kann verwendet werden, nur innerhalb einer `Function` Prozedur.  
  
 Um einen Rückgabewert anzugeben, können Sie den Wert dem Funktionsnamen in einer Zeile vor dem Zuweisen der `Exit Function` Anweisung. Um weisen den Rückgabewert, und die Funktion in einer Anweisung zu beenden, können Sie stattdessen die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Beendet sofort die `Property` Prozedur, in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung, die aufgerufen der `Property` Prozedur, d. h. mit der Anweisung angefordert oder den Wert der Eigenschaft festgelegt. `Exit Property` kann verwendet werden, nur in einer Eigenschaft `Get` oder `Set` Prozedur.  
  
 An einen Rückgabewert in einer `Get` Verfahren können Sie den Wert dem Funktionsnamen in einer Zeile vor dem Zuweisen der `Exit Property` Anweisung. Zuweisen von den Rückgabewert und Beenden der `Get` Prozedur in einer Anweisung, stattdessen können Sie die `Return` Anweisung.  
  
 In einem `Set` Prozedur, die `Exit Property` Anweisung entspricht der `Return` Anweisung.  
  
 `Exit Select`  
 Beendet sofort die `Select Case` -block in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung nach der `End Select` Anweisung. `Exit Select` kann verwendet werden, nur innerhalb einer `Select Case` Anweisung.  
  
 `Exit Sub`  
 Beendet sofort die `Sub` Prozedur, in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die aufgerufen der `Sub` Prozedur. `Exit Sub` kann verwendet werden, nur innerhalb einer `Sub` Prozedur.  
  
 In einem `Sub` Prozedur, die `Exit Sub` Anweisung entspricht der `Return` Anweisung.  
  
 `Exit Try`  
 Beendet sofort die `Try` oder `Catch` -block in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der `Finally` blockieren, sofern vorhanden, oder mit der Anweisung nach der `End Try` Anweisung andernfalls. `Exit Try` kann verwendet werden, nur innerhalb einer `Try` oder `Catch` Block, und nicht in eine `Finally` Block.  
  
 `Exit While`  
 Beendet sofort die `While` wurde eine Schleife in dem er angezeigt wird. Die Ausführung wird fortgeführt, mit der Anweisung nach der `End While` Anweisung. `Exit While` kann verwendet werden, nur innerhalb einer `While` Schleife. Bei Verwendung in geschachtelten `While` Schleifen, `Exit While` überträgt die Steuerung an die Schleife, die eine geschachtelte Ebene über die Schleife ist, in dem `Exit While` auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Verwechseln Sie nicht `Exit` -Anweisungen mit `End` Anweisungen. `Exit` das Ende einer Anweisung werden keine definiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die schleifenbedingung die Schleife beendet bei der `index` Variable größer als 100 ist. Die `If` -Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel weist den Rückgabewert den Namen der Funktion `myFunction`, und verwendet dann `Exit Function` , von der Funktion zurückkehren.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) weisen den Rückgabewert und die Funktion beenden.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)  
 [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md)  
 [Stop-Anweisung](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
