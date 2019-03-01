---
title: On Error-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
ms.openlocfilehash: 5dc432f8e62430d48954b2c049cab3ebae4d442e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203742"
---
# <a name="on-error-statement-visual-basic"></a>On Error-Anweisung (Visual Basic)
Aktiviert eine Fehlerbehandlungsroutine und gibt den Speicherort der Routine in einer Prozedur an. kann auch verwendet werden, um eine Fehlerbehandlungsroutine zu deaktivieren.  
  
 Ohne Fehlerbehandlung wird alle Laufzeitfehler, das auftritt, schwerwiegender: eine Fehlermeldung angezeigt wird, und die Ausführung beendet.  
  
 Wann immer möglich, sollten Sie Sie strukturierte Ausnahmen behandeln, die in Ihrem Code statt mit der unstrukturierten Ausnahmebehandlung verwenden und die `On Error` Anweisung. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Die `Error` -Schlüsselwort wird auch verwendet, der [Error-Anweisung](../../../visual-basic/language-reference/statements/error-statement.md), dies wird für Abwärtskompatibilität unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`GoTo` `line`|Aktiviert die Fehlerbehandlungsroutine, die in der Zeile, die in die erforderlichen angegebenen beginnt `line` Argument. Die `line` Argument ist zeilenbezeichnung oder Zeilennummer. Wenn ein Laufzeitfehler auftritt, steuern Sie Branches in die angegebene Zeile, die den Fehlerhandler aktivieren. Die angegebene Zeile muss in der gleichen Prozedur wie die `On Error` -Anweisung oder ein Fehler während der Kompilierung erfolgt.|  
|`GoTo` 0|Aktivierte Fehlerhandler in der aktuellen Prozedur deaktiviert und setzt es `Nothing`.|  
|`GoTo` -1|Deaktiviert die aktivierte Ausnahme in der aktuellen Prozedur und setzt es `Nothing`.|  
|`Resume Next`|Gibt an, tritt ein Laufzeitfehler auf, wird die Kontrolle an die Anweisung sofort nach der Anweisung, in dem der Fehler aufgetreten ist, und die Ausführung wird fortgeführt, von diesem Punkt. Verwenden Sie dieses Formular statt `On Error GoTo` beim Zugriff auf Objekte.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie die strukturierte Ausnahmebehandlung im Code nach Möglichkeit anstelle der Verwendung nicht strukturierte Ausnahmebehandlung verwenden und die `On Error` Anweisung. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Ein "enabled" Fehlerhandler ist ein, die aktiviert ist ein `On Error` Anweisung. Ein "aktiven" Error-Handler ist ein aktivierter Handler, der bei der Verarbeitung eines Fehlers ist.  
  
 Wenn ein Fehler auftritt, während ein fehlerhandlers aktiv ist (zwischen dem Auftreten des Fehlers und einer `Resume`, `Exit Sub`, `Exit Function`, oder `Exit Property` Anweisung), kann nicht die aktuelle Prozedur Fehlerhandler den Fehler zu behandeln. Steuerung, die an die aufrufende Prozedur zurückgegeben werden.  
  
 Wenn die aufrufende Prozedur über eine aktivierte Fehlerhandler verfügt, wird es aktiviert, um den Fehler zu behandeln. Wenn die aufrufende Prozedur Fehlerhandler auch aktiv ist, übergibt die Steuerung zurück durch vorherigen Aufruf Prozeduren bis ein aktiviert, aber inaktive, Error-Handler gefunden wird. Wenn kein solcher Fehlerhandler gefunden wird, ist der Fehler Schwerwiegender, an dem Punkt, an dem er tatsächlich aufgetreten ist.  
  
 Jedes Mal, wenn der Fehlerhandler zurück an die aufrufende Prozedur, wird die Steuerung wird diese Prozedur der aktuellen Prozedur. Sobald ein Fehler durch einen Fehlerhandler in einer beliebigen Prozedur behandelt wurde, Ausführung fortgesetzt wird, in der aktuellen Prozedur, die zum Zeitpunkt der vom angegebenen die `Resume` Anweisung.  
  
> [!NOTE]
>  Eine Fehlerbehandlungsroutine ist keiner `Sub` Prozedur oder ein `Function` Verfahren. Es ist ein Codeabschnitt, die durch eine zeilenbezeichnung oder Zeilennummer gekennzeichnet.  
  
## <a name="number-property"></a>Number-Eigenschaft  
 Routinen zur Fehlerbehandlung ist abhängig von den Wert in der `Number` Eigenschaft der `Err` Objekt, das die Ursache des Fehlers zu ermitteln. Die Routine testen sollten, oder speichern Sie relevante Eigenschaftswerte in die `Err` -Objekt, bevor ein anderer Fehler auftreten kann, oder bevor eine Prozedur, die dazu führen, dass möglicherweise ein Fehler aufgerufen. Die Eigenschaftswerte die `Err` Objekt entsprechen nur den zuletzt aufgetretene Fehler. Die Fehlermeldung zugeordnet `Err.Number` befindet sich im `Err.Description`.  
  
## <a name="throw-statement"></a>Throw-Anweisung  
 Fehler, die ausgelöst wird, mit der `Err.Raise` Methode legt die `Exception` Eigenschaft, um eine neu erstellte Instanz von der <xref:System.Exception> Klasse. Um das Auslösen von Ausnahmen, die von abgeleiteten Typen, eine `Throw` -Anweisung wird in der Sprache unterstützt. Dies nimmt einen einzelnen Parameter, der die Ausnahmeinstanz ausgelöst werden. Das folgende Beispiel zeigt, wie diese Funktionen mit dem vorhandenen Unterstützung für Ausnahmebehandlung verwendet werden können:  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Beachten Sie, dass die `On Error GoTo` Anweisung fängt alle Fehler, unabhängig von der Ausnahmeklasse.  
  
## <a name="on-error-resume-next"></a>On Error Resume Next  
 `On Error Resume Next` wird die Ausführung fortgesetzt wird, mit der Anweisung unmittelbar nach der Anweisung, die den Laufzeit-Fehler verursacht hat, oder rufen Sie mit der Anweisung sofort nach der letzten aus die Prozedur mit der `On Error Resume Next` Anweisung. Mit dieser Anweisung können die Ausführung fort, obwohl ein Laufzeitfehler ausgegeben. Sie können platzieren, die Steuerung an eine andere Position innerhalb der Prozedur übertragen, anstatt die Fehlerbehandlungsroutine, wo der Fehler auftreten würden. Ein `On Error Resume Next` Anweisung wird inaktiv, wenn eine andere Prozedur aufgerufen wird, damit Sie ausgeführt werden soll, ein `On Error Resume Next` Anweisung in den einzelnen Routine aufgerufen, wenn es sich bei Inline-Fehlerbehandlung innerhalb dieser Routine werden sollen.  
  
> [!NOTE]
>  Die `On Error Resume Next` Konstrukt möglicherweise besser, `On Error GoTo` bei der Behandlung von Fehlern, die beim Zugriff auf andere Objekte generiert. Überprüfung `Err` nach jeder Interaktion mit einem Objekt darüber, welche Objekt, indem der Code zugegriffen wurde. Sie können Sie sicher, dass welches Objekt den Fehlercode in platziert werden `Err.Number`, und welches Objekt den Fehler ursprünglich generiert hat (das Objekt, das im angegebenen `Err.Source`).  
  
## <a name="on-error-goto-0"></a>On Error GoTo 0  
 `On Error GoTo 0` wird für die Fehlerbehandlung in der aktuellen Prozedur deaktiviert. Es angeben nicht Line 0 wird als Ausgangspunkt des Codes für die Fehlerbehandlung, auch wenn die Prozedur eine Zeile 0 enthält. Ohne eine `On Error GoTo 0` -Anweisung, einen Fehlerhandler wird automatisch deaktiviert, wenn eine Prozedur beendet wird.  
  
## <a name="on-error-goto--1"></a>On Error GoTo -1  
 `On Error GoTo -1` wird die Ausnahme in der aktuellen Prozedur deaktiviert. Es gibt keine Zeile-1 als Ausgangspunkt des Codes für die Fehlerbehandlung an, selbst wenn die Prozedur eine Zeile mit der Nummer 1, enthält. Ohne eine `On Error GoTo -1` -Anweisung, eine Ausnahme wird automatisch deaktiviert, wenn eine Prozedur beendet wird.  
  
 Um zu verhindern, dass Fehlerbehandlungscode ausgeführt, wenn kein Fehler aufgetreten ist, platzieren ein `Exit Sub`, `Exit Function`, oder `Exit Property` Anweisung unmittelbar vor der Fehlerbehandlungsroutine, wie das folgende Fragment:  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 Hier ist der Fehlerbehandlungscode folgt die `Exit Sub` Anweisung und wird vor dem die `End Sub` Anweisung für die Trennung der Ablauf der Prozedur. Sie können Fehlerbehandlungscode in einer Prozedur an einer beliebigen Stelle platzieren.  
  
## <a name="untrapped-errors"></a>Nicht abgefangene Fehler  
 Nicht abgefangene Fehler in Objekten werden an die steuernde Anwendung zurückgegeben, wenn das Objekt als eine ausführbare Datei ausgeführt wird. Nicht abgefangene Fehler werden in der Entwicklungsumgebung der Anwendung steuern zurückgegeben, nur, wenn die entsprechenden Optionen festgelegt werden. Finden Sie in der hostanwendung Dokumentation eine Beschreibung der Optionen liegen Gruppe während des Debuggens, wie diese festgelegt und gibt an, ob der Host Klassen erstellen kann.  
  
 Wenn Sie ein Objekt, die auf andere Objekte zugreift erstellen, sollten Sie nicht behandelte Fehler zu behandeln, die sie zurück zu übergeben. Wenn Sie die Fehlercodes in zugeordnet sind, nicht möglich ist, `Err.Number` eines eigenen Fehler und übergeben Sie sie an den Aufrufer des Objekts zurück. Sie sollten den Fehler angeben, indem Sie den Fehlercode zum Hinzufügen der `VbObjectError` Konstanten. Beispielsweise ist der Fehlercode 1052, weisen Sie ihn wie folgt:  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  Systemfehler beim Aufrufen von Windows-Dynamic Link Libraries (DLLs) keine Ausnahmen auslösen und können nicht mit Visual Basic das Abfangen von Fehlern nicht abgefangen werden. Beim Aufrufen von DLL-Funktionen, überprüfen Sie jeden Rückgabewert für den Erfolg oder Misserfolg (gemäß der API-Spezifikationen), und ein Fehler auftritt, überprüfen Sie den Wert der `Err` des Objekts `LastDLLError` Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verwendet zuerst die `On Error GoTo` Anweisung, um den Speicherort einer Routine für die Fehlerbehandlung in einer Prozedur anzugeben. Im Beispiel führt der Versuch Division durch 0 (null) Fehlernummer 6. Der Fehler wird in der Fehlerbehandlung Routine behandelt, und die Steuerung dann wieder an die Anweisung, die den Fehler verursacht hat. Die `On Error GoTo 0` Anweisung deaktiviert das Abfangen von Fehlern. Die `On Error Resume Next` -Anweisung verwendet, um zurückstellen Fehler abfangen, damit der Kontext für den Fehler generiert, indem Sie die nächste Anweisung für bestimmte bekannt sein kann. Beachten Sie, dass `Err.Clear` dient zum Löschen der `Err` Eigenschaften des Objekts, nachdem der Fehler behandelt wird.  
  
 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Resume-Anweisung](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Fehlermeldungen](../../../visual-basic/language-reference/error-messages/index.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
