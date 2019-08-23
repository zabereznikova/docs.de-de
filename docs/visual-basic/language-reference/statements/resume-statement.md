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
ms.openlocfilehash: 884bdaa0c19508b5a6bf6377568a53acc6880518
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957691"
---
# <a name="resume-statement"></a>Resume-Anweisung
Setzt die Ausführung fort, nachdem eine Fehler Behandlungs Routine abgeschlossen wurde.  
  
 Es wird empfohlen, dass Sie nach Möglichkeit die strukturierte Ausnahmebehandlung im Code verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und `On Error` die `Resume` -und-Anweisungen zu verwenden. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Teile  
 `Resume`  
 Erforderlich. Wenn der Fehler in derselben Prozedur wie der Fehlerhandler aufgetreten ist, wird die Ausführung mit der Anweisung fortgesetzt, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur aufgetreten ist, wird die Ausführung bei der Anweisung fortgesetzt, die zuletzt von der Prozedur mit der Fehler Behandlungs Routine aufgerufen wurde.  
  
 `Next`  
 Optional. Wenn der Fehler in derselben Prozedur wie der Fehlerhandler aufgetreten ist, wird die Ausführung mit der Anweisung unmittelbar nach der Anweisung fortgesetzt, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur aufgetreten ist, wird die Ausführung mit der Anweisung unmittelbar nach der Anweisung fortgesetzt, die zuletzt von der Prozedur mit der Fehler Behandlungs Routine `On Error Resume Next` (oder-Anweisung) aufgerufen wurde.  
  
 `line`  
 Optional. Die Ausführung wird in der Zeile fortgesetzt, die `line` im erforderlichen Argument angegeben ist. Das `line` -Argument ist eine Zeilen Bezeichnung oder Zeilennummer und muss sich in derselben Prozedur wie der Fehlerhandler befinden.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Es empfiehlt sich, nach Möglichkeit eine strukturierte Ausnahmebehandlung in Ihrem Code zu verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und `On Error` die `Resume` -und-Anweisungen zu verwenden. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Wenn Sie eine `Resume` -Anweisung an einer anderen Stelle als in einer Fehler Behandlungs Routine verwenden, tritt ein Fehler auf.  
  
 Die `Resume` -Anweisung kann nicht in einer Prozedur verwendet werden, `Try...Catch...Finally` die eine-Anweisung enthält.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `Resume` die-Anweisung verwendet, um die Fehlerbehandlung in einer Prozedur zu beenden und die Ausführung dann mit der Anweisung fortzusetzen, die den Fehler verursacht hat Die Fehlernummer 55 wird generiert, um die `Resume` Verwendung der-Anweisung zu veranschaulichen.  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Stadtverordneten** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Siehe auch

- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Error-Anweisung](../../../visual-basic/language-reference/statements/error-statement.md)
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
