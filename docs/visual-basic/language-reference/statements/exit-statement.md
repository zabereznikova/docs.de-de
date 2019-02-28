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
ms.openlocfilehash: e08d436686876a0a3d63f15167d35383e32221e7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967801"
---
# <a name="exit-statement-visual-basic"></a>Exit-Anweisung (Visual Basic)
Beendet eine Prozedur oder der Block und überträgt die Steuerung sofort an die Anweisung nach dem Prozeduraufruf oder der Blockdefinition.  
  
## <a name="syntax"></a>Syntax  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Anweisungen  
 `Exit Do`  
 Beendet sofort die `Do` wurde eine Schleife in der es angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung nach der `Loop` Anweisung. `Exit Do` kann verwendet werden, nur innerhalb einer `Do` Schleife. Bei der Verwendung in geschachtelten `Do` Schleifen `Exit Do` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene Schachtelungsebenen.  
  
 `Exit For`  
 Beendet sofort die `For` wurde eine Schleife in der es angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung nach der `Next` Anweisung. `Exit For` kann verwendet werden, nur innerhalb einer `For`... `Next` oder `For Each`... `Next` Schleife. Bei der Verwendung in geschachtelten `For` Schleifen `Exit For` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene Schachtelungsebenen.  
  
 `Exit Function`  
 Sofort beendet die `Function` Prozedur, die in der sie angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die Namen der `Function` Verfahren. `Exit Function` kann verwendet werden, nur innerhalb einer `Function` Verfahren.  
  
 Um einen Rückgabewert anzugeben, können Sie den Wert zuweisen, auf den Funktionsnamen in einer Zeile vor der `Exit Function` Anweisung. Weisen Sie den Rückgabewert und die Funktion in einer Anweisung beenden, können Sie stattdessen die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Sofort beendet die `Property` Prozedur, die in der sie angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung, die Namen der `Property` Prozedur, d. h. mit der Anweisung angefordert oder den Wert der Eigenschaft festgelegt. `Exit Property` kann verwendet werden, nur innerhalb einer Eigenschaft `Get` oder `Set` Verfahren.  
  
 An einen Rückgabewert in einer `Get` Verfahren können Sie den Wert auf den Funktionsnamen in einer Zeile vor dem Zuweisen der `Exit Property` Anweisung. Zuweisen von den Rückgabewert und Beenden der `Get` Prozedur in einer Anweisung können Sie stattdessen verwenden die `Return` Anweisung.  
  
 In einem `Set` Verfahren der `Exit Property` Anweisung entspricht der `Return` Anweisung.  
  
 `Exit Select`  
 Beendet sofort die `Select Case` -block in der es angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung nach der `End Select` Anweisung. `Exit Select` kann verwendet werden, nur innerhalb einer `Select Case` Anweisung.  
  
 `Exit Sub`  
 Sofort beendet die `Sub` Prozedur, die in der sie angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die Namen der `Sub` Verfahren. `Exit Sub` kann verwendet werden, nur innerhalb einer `Sub` Verfahren.  
  
 In einem `Sub` Verfahren der `Exit Sub` Anweisung entspricht der `Return` Anweisung.  
  
 `Exit Try`  
 Beendet sofort die `Try` oder `Catch` -block in der es angezeigt wird. Ausführung wird fortgeführt, mit der `Finally` blockieren, sofern vorhanden, oder mit der Anweisung nach der `End Try` Anweisung andernfalls. `Exit Try` kann verwendet werden, nur innerhalb einer `Try` oder `Catch` Block und nicht in eine `Finally` Block.  
  
 `Exit While`  
 Beendet sofort die `While` wurde eine Schleife in der es angezeigt wird. Ausführung wird fortgeführt, mit der Anweisung nach der `End While` Anweisung. `Exit While` kann verwendet werden, nur innerhalb einer `While` Schleife. Bei der Verwendung in geschachtelten `While` Schleifen, `Exit While` überträgt die Steuerung an die Schleife, die eine geschachtelte Ebene über der Schleife befindet, in denen `Exit While` auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Verwechseln Sie nicht `Exit` -Anweisungen mit `End` Anweisungen. `Exit` das Ende einer Anweisung werden keine definiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die schleifenbedingung die Schleife beendet, mit denen bei der `index` Variable ist größer als 100. Die `If` Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel weist den zurückgegeben Wert den Namen der Funktion `myFunction`, und verwendet dann `Exit Function` von der Funktion zurückgegeben.  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) weisen den Rückgabewert und die Funktion beenden.  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>Siehe auch
- [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md)
- [Stop-Anweisung](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
