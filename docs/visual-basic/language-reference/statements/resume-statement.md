---
title: Resume-Anweisung (Visual Basic)
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
ms.openlocfilehash: fcb50a9c7e36bab046be25d7f82f91cfe0f9be8e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966917"
---
# <a name="resume-statement"></a>Resume-Anweisung
Setzt die Ausführung fort, nachdem eine Fehlerbehandlungsroutine abgeschlossen ist.  
  
 Es wird empfohlen, dass Sie die strukturierte Ausnahmebehandlung im Code nach Möglichkeit anstelle der Verwendung nicht strukturierte Ausnahmebehandlung verwenden und die `On Error` und `Resume` Anweisungen. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Teile  
 `Resume`  
 Erforderlich. Wenn der Fehler in der gleichen Prozedur wie der Fehlerhandler, setzt die Ausführung mit der Anweisung, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur setzt die Ausführung bei der Anweisung, die aus der Prozedur die Fehlerbehandlungsroutine mit dem letzten Aufruf.  
  
 `Next`  
 Dies ist optional. Wenn der Fehler in der gleichen Prozedur wie der Fehlerhandler, setzt die Ausführung mit der Anweisung sofort nach der Anweisung, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur Ausführung fortgesetzt wird, mit der Anweisung sofort nach der Anweisung, die aus der Prozedur die Fehlerbehandlungsroutine mit dem letzten Aufruf (oder `On Error Resume Next` Anweisung).  
  
 `line`  
 Dies ist optional. Ausführung fortgesetzt wird, in der Zeile, die in die erforderlichen angegebenen `line` Argument. Die `line` Argument ist eine zeilenbezeichnung oder Zeilennummer und muss in der gleichen Prozedur wie der Fehlerhandler.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie die strukturierte Ausnahmebehandlung im Code nach Möglichkeit anstelle der Verwendung nicht strukturierte Ausnahmebehandlung verwenden und die `On Error` und `Resume` Anweisungen. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Bei Verwendung einer `Resume` Anweisung überall außer in einer Fehlerbehandlungsroutine, ein Fehler auftritt.  
  
 Die `Resume` Anweisung kann nicht verwendet werden, in einer beliebigen Prozedur, die enthält eine `Try...Catch...Finally` Anweisung.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Resume` Anweisung, um die Fehlerbehandlung in einer Prozedur beendet, und klicken Sie dann fortsetzen Ausführung mit der Anweisung, die den Fehler verursacht hat. Fehlernummer 55 wird generiert, um die Verwendung von veranschaulichen die `Resume` Anweisung.  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Siehe auch
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Error-Anweisung](../../../visual-basic/language-reference/statements/error-statement.md)
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
