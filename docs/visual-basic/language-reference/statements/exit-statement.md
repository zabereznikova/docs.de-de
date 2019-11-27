---
title: Exit-Anweisung
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
ms.openlocfilehash: 1bfe81428fd3c50663fd8978e05c6a945cd47df8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345939"
---
# <a name="exit-statement-visual-basic"></a>Exit-Anweisung (Visual Basic)

Beendet eine Prozedur oder einen Block und überträgt die Steuerung sofort an die Anweisung nach dem Prozedur-oder der Block Definition.

## <a name="syntax"></a>Syntax

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Anweisungen

 `Exit Do`  
 Beendet sofort die `Do` Schleife, in der Sie angezeigt wird. Die Ausführung wird mit der Anweisung nach der `Loop`-Anweisung fortgesetzt. `Exit Do` können nur innerhalb einer `Do`-Schleife verwendet werden. Wenn Sie in geschachtelten `Do` Schleifen verwendet wird, beendet `Exit Do` die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.

 `Exit For`  
 Beendet sofort die `For` Schleife, in der Sie angezeigt wird. Die Ausführung wird mit der Anweisung nach der `Next`-Anweisung fortgesetzt. `Exit For` können nur innerhalb einer `For`...`Next`-oder `For Each`...`Next`-Schleife verwendet werden. Wenn Sie in geschachtelten `For` Schleifen verwendet wird, beendet `Exit For` die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.

 `Exit Function`  
 Beendet sofort die `Function` Prozedur, in der Sie angezeigt wird. Die Ausführung wird mit der Anweisung nach der Anweisung fortgesetzt, die die `Function` Prozedur aufgerufen hat. `Exit Function` können nur innerhalb einer `Function` Prozedur verwendet werden.

 Zum Angeben eines Rückgabewerts können Sie den Wert in einer Zeile vor der `Exit Function` Anweisung dem Funktionsnamen zuweisen. Wenn Sie den Rückgabewert zuweisen und die Funktion in einer Anweisung beenden möchten, können Sie stattdessen die [Return-Anweisung](return-statement.md)verwenden.

 `Exit Property`  
 Beendet sofort die `Property` Prozedur, in der Sie angezeigt wird. Die Ausführung wird mit der Anweisung fortgesetzt, die die `Property` Prozedur aufgerufen hat, d. h. mit der Anweisung, die den Wert der Eigenschaft anfordert oder festlegt. `Exit Property` können nur innerhalb der `Get`-oder `Set` Prozedur einer Eigenschaft verwendet werden.

 Um einen Rückgabewert in einer `Get` Prozedur anzugeben, können Sie den Wert in einer Zeile vor der `Exit Property` Anweisung dem Funktionsnamen zuweisen. Um den Rückgabewert zuzuweisen und die `Get` Prozedur in einer Anweisung zu beenden, können Sie stattdessen die `Return`-Anweisung verwenden.

 In einer `Set` Prozedur entspricht die `Exit Property`-Anweisung der `Return`-Anweisung.

 `Exit Select`  
 Beendet sofort den `Select Case` Block, in dem er angezeigt wird. Die Ausführung wird mit der Anweisung nach der `End Select`-Anweisung fortgesetzt. `Exit Select` können nur innerhalb einer `Select Case`-Anweisung verwendet werden.

 `Exit Sub`  
 Beendet sofort die `Sub` Prozedur, in der Sie angezeigt wird. Die Ausführung wird mit der Anweisung nach der Anweisung fortgesetzt, die die `Sub` Prozedur aufgerufen hat. `Exit Sub` können nur innerhalb einer `Sub` Prozedur verwendet werden.

 In einer `Sub` Prozedur entspricht die `Exit Sub`-Anweisung der `Return`-Anweisung.

 `Exit Try`  
 Beendet sofort den `Try` oder `Catch` Block, in dem er angezeigt wird. Die Ausführung wird mit dem `Finally` Block fortgesetzt, sofern vorhanden, oder mit der Anweisung, die auf die `End Try` Anweisung folgt, andernfalls. `Exit Try` können nur in einem `Try` oder `Catch` Block verwendet werden, nicht innerhalb eines `Finally` Blocks.

 `Exit While`  
 Beendet sofort die `While` Schleife, in der Sie angezeigt wird. Die Ausführung wird mit der Anweisung nach der `End While`-Anweisung fortgesetzt. `Exit While` können nur innerhalb einer `While`-Schleife verwendet werden. Bei der Verwendung in geschachtelten `While` Schleifen `Exit While` überträgt die Steuerung an die Schleife, die eine geschachtelte Ebene oberhalb der Schleife ist, in der `Exit While` auftritt.

## <a name="remarks"></a>Hinweise

Verwechseln Sie `Exit`-Anweisungen nicht mit `End` Anweisungen. in `Exit` wird das Ende einer-Anweisung nicht definiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Schleife durch die Schleifen Bedingung beendet, wenn die `index` Variable größer als 100 ist. Die `If` Anweisung in der Schleife bewirkt jedoch, dass die `Exit Do` Anweisung die Schleife beendet, wenn die Index Variable größer als 10 ist.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der-Rückgabewert dem Funktionsnamen `myFunction`zugewiesen und dann `Exit Function` verwendet, um von der-Funktion zurückzugeben:

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [Return-Anweisung](return-statement.md) verwendet, um den Rückgabewert zuzuweisen und die-Funktion zu beenden:

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>Siehe auch

- [Continue-Anweisung](continue-statement.md)
- [Do...Loop-Anweisung](do-loop-statement.md)
- [End-Anweisung](end-statement.md)
- [For Each...Next-Anweisung](for-each-next-statement.md)
- [For...Next-Anweisung](for-next-statement.md)
- [Function-Anweisung](function-statement.md)
- [Return-Anweisung](return-statement.md)
- [Stop-Anweisung](stop-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md)
