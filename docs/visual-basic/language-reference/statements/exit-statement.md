---
title: "Exit Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Exit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "execution, ending"
  - "files, closing"
  - "programs, quitting"
  - "code, exiting"
  - "Exit statement"
  - "program termination"
  - "execution, stopping"
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Exit Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Beendet eine Prozedur oder einen Block und überträgt die Steuerung sofort an die Anweisung, die auf den Prozeduraufruf oder die Blockdefinition folgt.  
  
## Syntax  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## Anweisungen  
 `Exit Do`  
 Beendet die umgebende `Do`\-Schleife mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung nach der `Loop`\-Anweisung fortgesetzt.  `Exit Do` kann nur in einer `Do`\-Schleife verwendet werden.  Bei Verwendung in geschachtelten `Do`\-Schleifen beendet `Exit Do` die innerste Schleife und überträgt die Steuerung auf die nächsthöhere Schachtelungsebene.  
  
 `Exit For`  
 Beendet die umgebende `For`\-Schleife mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung nach der `Next`\-Anweisung fortgesetzt.  `Exit For` kann nur in einer `For`...`Next`\-Schleife oder in einer `For Each`...`Next`\-Schleife verwendet werden.  Bei Verwendung in geschachtelten `For`\-Schleifen beendet `Exit For` die innerste Schleife und überträgt die Steuerung auf die nächsthöhere Schachtelungsebene.  
  
 `Exit Function`  
 Beendet die umgebende `Function`\-Prozedur mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung nach der Anweisung fortgesetzt, die die `Function`\-Prozedur aufgerufen hat.  `Exit Function` kann nur in einer `Function`\-Prozedur verwendet werden.  
  
 Um einen Rückgabewert anzugeben, können Sie den Wert dem Funktionsnamen in einer Zeile vor der `Exit Function`\-Anweisung zuweisen.  Um den Rückgabewert zuzuweisen und die Funktion in einer Anweisung zu beenden, können Sie stattdessen [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) verwenden.  
  
 `Exit Property`  
 Beendet die umgebende `Property`\-Prozedur mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung fortgesetzt, die die `Property`\-Prozedur aufgerufen hat, d. h. mit der Anweisung, die den Wert der Eigenschaft angefordert oder festgelegt hat.  `Exit Property` kann nur in der `Get`\-Prozedur oder der `Set`\-Prozedur einer Eigenschaft verwendet werden.  
  
 Um einen Rückgabewert in einer `Get`\-Prozedur anzugeben, können Sie den Wert dem Funktionsnamen in einer Zeile vor der `Exit Property`\-Anweisung zuweisen.  Um den Rückgabewert zuzuweisen und die `Get`\-Prozedur in einer Anweisung zu beenden, können Sie stattdessen die `Return`\-Anweisung verwenden.  
  
 In einer `Set`\-Prozedur entspricht die `Exit Property`\-Anweisung der `Return`\-Anweisung.  
  
 `Exit Select`  
 Beendet den umgebenden `Select Case`\-Block mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung nach der `End Select`\-Anweisung fortgesetzt.  `Exit Select` kann nur in einer `Select Case`\-Anweisung verwendet werden.  
  
 `Exit Sub`  
 Beendet die umgebende `Sub`\-Prozedur mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung nach der Anweisung fortgesetzt, die die `Sub`\-Prozedur aufgerufen hat.  `Exit Sub` kann nur in einer `Sub`\-Prozedur verwendet werden.  
  
 In einer `Sub`\-Prozedur entspricht die `Exit Sub`\-Anweisung der `Return`\-Anweisung.  
  
 `Exit Try`  
 Beendet den umgebenden `Try`\-Block oder `Catch`\-Block mit sofortiger Wirkung.  Die Ausführung wird mit dem `Finally`\-Block fortgesetzt, falls vorhanden, und andernfalls mit der Anweisung nach der `End Try`\-Anweisung.  `Exit Try` kann nur in einem `Try`\-Block oder einem `Catch`\-Block und nicht in einem `Finally`\-Block verwendet werden.  
  
 `Exit While`  
 Beendet die umgebende `While`\-Schleife mit sofortiger Wirkung.  Die Ausführung wird mit der Anweisung nach der `End While`\-Anweisung fortgesetzt.  `Exit While` kann nur in einer `While`\-Schleife verwendet werden.  In geschachtelten `While`\-Schleifen überträgt `Exit While` die Steuerung an die Schleife auf der Schachtelungsebene über der Schleife, in der sich `Exit While` befindet.  
  
## Hinweise  
 `Exit`\-Anweisungen sind nicht mit `End`\-Anweisungen zu verwechseln.  `Exit` definiert nicht das Ende einer Anweisung.  
  
## Beispiel  
 Im folgenden Beispiel beendet die Schleifenbedingung die Schleife, wenn die `index`\-Variable größer als 100 ist.  Die `If`\-Anweisung in der Schleife führt jedoch dazu, dass die `Exit Do`\-Anweisung beendet wird, um die Schleife zu stoppen, wenn die Index\-Variable größer als 10 ist.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/exit-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird der Rückgabewert dem Funktionsnamen `myFunction` zugewiesen und dann mit der `Exit Function`\-Anweisung von der Funktion zurückgegeben.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/exit-statement_2.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mit [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) der Rückgabewert zugewiesen und die Funktion beendet wird.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/exit-statement_3.vb)]  
  
## Siehe auch  
 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)   
 [Stop Statement](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)