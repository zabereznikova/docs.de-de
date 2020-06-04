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
ms.openlocfilehash: 3f49f05f1deb2027b03bbf3443ca44f30c44344e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404212"
---
# <a name="resume-statement"></a>Resume-Anweisung
Setzt die Ausführung fort, nachdem eine Fehler Behandlungs Routine abgeschlossen wurde.  
  
 Es wird empfohlen, dass Sie nach Möglichkeit die strukturierte Ausnahmebehandlung im Code verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und die `On Error` -und-Anweisungen zu verwenden `Resume` . Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Bestandteile  
 `Resume`  
 Erforderlich. Wenn der Fehler in derselben Prozedur wie der Fehlerhandler aufgetreten ist, wird die Ausführung mit der Anweisung fortgesetzt, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur aufgetreten ist, wird die Ausführung bei der Anweisung fortgesetzt, die zuletzt von der Prozedur mit der Fehler Behandlungs Routine aufgerufen wurde.  
  
 `Next`  
 Optional. Wenn der Fehler in derselben Prozedur wie der Fehlerhandler aufgetreten ist, wird die Ausführung mit der Anweisung unmittelbar nach der Anweisung fortgesetzt, die den Fehler verursacht hat. Wenn der Fehler in einer aufgerufenen Prozedur aufgetreten ist, wird die Ausführung mit der Anweisung unmittelbar nach der Anweisung fortgesetzt, die zuletzt von der Prozedur mit der Fehler Behandlungs Routine (oder- `On Error Resume Next` Anweisung) aufgerufen wurde.  
  
 `line`  
 Optional. Die Ausführung wird in der Zeile fortgesetzt, die im erforderlichen Argument angegeben ist `line` . Das `line` -Argument ist eine Zeilen Bezeichnung oder Zeilennummer und muss sich in derselben Prozedur wie der Fehlerhandler befinden.  
  
## <a name="remarks"></a>Bemerkungen  
  
> [!NOTE]
> Es empfiehlt sich, nach Möglichkeit eine strukturierte Ausnahmebehandlung in Ihrem Code zu verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und die `On Error` -und-Anweisungen zu verwenden `Resume` . Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md).  
  
 Wenn Sie eine- `Resume` Anweisung an einer anderen Stelle als in einer Fehler Behandlungs Routine verwenden, tritt ein Fehler auf.  
  
 Die- `Resume` Anweisung kann nicht in einer Prozedur verwendet werden, die eine- `Try...Catch...Finally` Anweisung enthält.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel `Resume` wird die-Anweisung verwendet, um die Fehlerbehandlung in einer Prozedur zu beenden und die Ausführung dann mit der Anweisung fortzusetzen, die den Fehler verursacht hat Die Fehlernummer 55 wird generiert, um die Verwendung der-Anweisung zu veranschaulichen `Resume` .  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Assembly:** Visual Basic-Lauf Zeit Bibliothek (in "Microsoft. VisualBasic. dll")  
  
## <a name="see-also"></a>Weitere Informationen

- [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md)
- [Error-Anweisung](error-statement.md)
- [On Error-Anweisung](on-error-statement.md)
