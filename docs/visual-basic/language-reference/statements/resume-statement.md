---
title: Resume-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resume-statement"></a>Resume-Anweisung
Setzt die Ausführung fort, nachdem eine Fehlerbehandlungsroutine abgeschlossen ist.  
  
 Es wird empfohlen, strukturierte Ausnahmebehandlung im Code nach Möglichkeit statt mit der unstrukturierten Ausnahmebehandlung zu verwenden und die `On Error` und `Resume` Anweisungen. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Teile  
 `Resume`  
 Erforderlich. Wenn in der gleichen Prozedur wie der Fehlerhandler der Fehler aufgetreten ist, setzt die Ausführung mit der Anweisung, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur setzt die Ausführung bei der Anweisung, die zuletzt aus der Prozedur mit der Fehlerbehandlungsroutine aufgerufen.  
  
 `Next`  
 Dies ist optional. Wenn in der gleichen Prozedur wie der Fehlerhandler der Fehler aufgetreten ist, setzt die Ausführung mit der Anweisung sofort nach der Anweisung, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur die Ausführung wird fortgesetzt, mit der Anweisung sofort nach der Anweisung, die zuletzt aus der Prozedur mit der Fehlerbehandlungsroutine aufgerufen (oder `On Error Resume Next` Anweisung).  
  
 `line`  
 Dies ist optional. Die Ausführung wird fortgesetzt, in der Befehlszeile angegeben werden, in das erforderliche `line` Argument. Die `line` Argument ist eine zeilenbezeichnung oder Zeilennummer und muss in der gleichen Prozedur wie der Fehlerhandler.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Wir empfehlen die Verwendung von strukturierter Ausnahmebehandlung im Code nach Möglichkeit statt mit der unstrukturierten Ausnahmebehandlung und das `On Error` und `Resume` Anweisungen. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Bei Verwendung einer `Resume` Anweisung überall außer in eine Fehlerbehandlungsroutine, ein Fehler auftritt.  
  
 Die `Resume` Anweisung kann nicht verwendet werden, in einer Prozedur, deren enthält eine `Try...Catch...Finally` Anweisung.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Resume` Anweisung für die Fehlerbehandlung in einer Prozedur zu beenden, und klicken Sie dann fortsetzen Ausführung mit der Anweisung, die den Fehler verursacht hat. Fehlernummer 55 generiert, um die Verwendung der veranschaulichen die `Resume` Anweisung.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")  
  
## <a name="see-also"></a>Siehe auch  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Error-Anweisung](../../../visual-basic/language-reference/statements/error-statement.md)  
 [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
