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
ms.openlocfilehash: b2e32dcca2e29a178af6dc985da536b47f0ebae6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="on-error-statement-visual-basic"></a>On Error-Anweisung (Visual Basic)
Aktiviert eine Fehlerbehandlungsroutine und gibt den Speicherort der Routine innerhalb einer Prozedur an. kann auch verwendet werden, um eine Fehlerbehandlungsroutine zu deaktivieren.  
  
 Ohne Fehlerbehandlung, alle Laufzeitfehler, der auftritt, ist ein schwerwiegender Fehler: eine Fehlermeldung angezeigt wird, und die Ausführung beendet.  
  
 Wann immer möglich, empfehlen wir Sie Exception Handling, strukturierte im Code behandeln, statt unstrukturierte Ausnahmebehandlung verwenden und die `On Error` Anweisung. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Die `Error` Schlüsselwort werden auch in der [Error-Anweisung](../../../visual-basic/language-reference/statements/error-statement.md), dieser wird für Abwärtskompatibilität unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`GoTo` `line`|Ermöglicht die Fehlerbehandlung-Routine, die in der Zeile angegeben, in das erforderliche beginnt `line` Argument. Die `line` Argument ist zeilenbezeichnung oder Zeilennummer. Tritt ein Laufzeitfehler auf, steuern Sie Verzweigungen in die angegebene Zeile, die den Fehlerhandler aktivieren. Die angegebene Zeile muss in der gleichen Prozedur wie die `On Error` -Anweisung oder einen Fehler während der Kompilierung erfolgt.|  
|`GoTo` 0|Deaktiviert die aktivierten Fehlerhandler in der aktuellen Prozedur und setzt es `Nothing`.|  
|`GoTo` -1|Deaktiviert die aktivierte Ausnahme in der aktuellen Prozedur und setzt es `Nothing`.|  
|`Resume Next`|Gibt an, dass wenn ein Laufzeitfehler auftritt, Steuerelement an die Anweisung sofort nach der Anweisung, in dem der Fehler aufgetreten ist, und die Ausführung wird fortgeführt, von diesem Punkt. Verwenden Sie dieses Formular anstatt `On Error GoTo` den Zugriff auf Objekte.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Wir empfehlen die Verwendung von strukturierter Ausnahmebehandlung im Code nach Möglichkeit statt mit der unstrukturierten Ausnahmebehandlung und das `On Error` Anweisung. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Ein "enabled" Fehlerhandler ist ein, die codeindizierung aktiviert ist, auf eine `On Error` Anweisung. Ein "aktiv" Fehlerhandler ist ein aktivierter Handler, der gerade Behandeln eines Fehlers an.  
  
 Wenn ein Fehler auftritt, während ein Fehlerhandler aktiv ist (zwischen dem Auftreten des Fehlers und einer `Resume`, `Exit Sub`, `Exit Function`, oder `Exit Property` Anweisung), die aktuelle Prozedur Fehlerhandler den Fehler behandeln kann nicht. Die Steuerung wird an die aufrufende Prozedur.  
  
 Wenn die aufrufende Prozedur eine Fehlerbehandlungsroutine aktiviert wurde, wird es aktiviert, um den Fehler zu behandeln. Wenn die aufrufende Prozedur Fehlerhandler auch aktiv ist, übergibt die Steuerung wieder über vorherige aufrufenden Prozeduren bis ein aktiviert, aber inaktive Fehlerhandler gefunden wird. Wenn kein solcher Fehlerhandler gefunden wird, ist der Fehler Schwerwiegender an dem Punkt, an dem er tatsächlich aufgetreten ist.  
  
 Jedes Mal, wenn der Fehlerhandler Steuerung wieder an eine aufrufende Prozedur übergeben, wird diese Prozedur zur aktuellen Prozedur. Nachdem ein Fehler durch einen Fehlerhandler in eine Prozedur behandelt wird, die Ausführung wird fortgesetzt, in der aktuellen Prozedur an dem Punkt, der vom angegebenen der `Resume` Anweisung.  
  
> [!NOTE]
>  Eine Fehlerbehandlungsroutine ist eine `Sub` Prozedur oder eine `Function` Prozedur. Es ist einem Codeabschnitt gekennzeichnet durch eine zeilenbezeichnung oder eine Zeilennummer.  
  
## <a name="number-property"></a>Number-Eigenschaft  
 Fehlerbehandlungsroutinen basieren auf dem Wert in der `Number` Eigenschaft von der `Err` Objekt, das die Ursache des Fehlers zu ermitteln. Die Routine testen oder speichern Sie die entsprechenden Eigenschaftswerte im sollte die `Err` Objekt vor alle anderen Fehler auftreten kann, oder bevor eine Prozedur, die dazu führen, dass möglicherweise ein Fehler aufgerufen wird. Die Eigenschaftswerte die `Err` Objekt widerzuspiegeln, nur den zuletzt aufgetretenen Fehler. Die Fehlermeldung zugeordnete `Err.Number` befindet sich im `Err.Description`.  
  
## <a name="throw-statement"></a>Throw-Anweisung  
 Fehler, die ausgelöst wird, mit der `Err.Raise` Methode legt die `Exception` Eigenschaft, um eine neu erstellte Instanz von der <xref:System.Exception> Klasse. Um das Auslösen von Ausnahmen abgeleitete Ausnahmetypen, unterstützen einen `Throw` -Anweisung wird in der Sprache unterstützt. Dies nimmt einen Parameter, der die Ausnahmeinstanz ausgelöst wird. Das folgende Beispiel zeigt, wie diese Funktionen mit der Unterstützung für die Ausnahmebehandlung verwendet werden können:  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 Beachten Sie, dass die `On Error GoTo` Anweisung alle Fehler, unabhängig von der Ausnahmeklasse aufgefangen.  
  
## <a name="on-error-resume-next"></a>On Error Resume Next  
 `On Error Resume Next` bewirkt, dass die Ausführung zu fortfahren mit der Anweisung unmittelbar nach der Anweisung, die Laufzeitfehler verursacht hat, oder rufen Sie mit der Anweisung unmittelbar nach der letzten aus der Prozedur mit der `On Error Resume Next` Anweisung. Diese Anweisung ermöglicht die Ausführung fortsetzen trotz einen Laufzeitfehler. Sie können die Fehlerbehandlung-Routine, in dem der Fehler auftreten würden, anstatt die Steuerung an eine andere Position innerhalb der Prozedur übertragen platzieren. Ein `On Error Resume Next` Anweisung wird inaktiv, wenn eine andere Prozedur aufgerufen wird, damit Sie ausgeführt werden soll, ein `On Error Resume Next` in jeder Anweisung aufgerufen Routine ggf. Inline-Fehlerbehandlung innerhalb dieser Routine.  
  
> [!NOTE]
>  Die `On Error Resume Next` Konstrukt möglicherweise vorzuziehen `On Error GoTo` bei der Behandlung von Fehlern während des Zugriffs auf andere Objekte generiert. Überprüfung `Err` nach jeder Interaktion mit einem Objekt der Code zugegriffen. Sie können sicher sein, welches Objekt den Fehlercode in platziert `Err.Number`, sowie welches Objekt den Fehler ursprünglich generiert hat (das Objekt, das im angegebenen `Err.Source`).  
  
## <a name="on-error-goto-0"></a>On Error GoTo 0  
 `On Error GoTo 0` deaktiviert die Fehlerbehandlung in der aktuellen Prozedur. Er ist nicht als Anfang der Fehlerbehandlungscode Zeile 0 angeben, auch wenn die Prozedur eine Zeile 0 enthält. Ohne eine `On Error GoTo 0` einen Fehlerhandler-Anweisung wird automatisch deaktiviert, wenn eine Prozedur beendet wird.  
  
## <a name="on-error-goto--1"></a>On Error GoTo-1  
 `On Error GoTo -1` deaktiviert die Ausnahme in der aktuellen Prozedur. Es gibt keine Zeile-1 als Anfang der Fehlerbehandlungscode an, selbst wenn die Prozedur eine Zeile mit der Nummer-1 enthält. Ohne eine `On Error GoTo -1` -Anweisung, eine Ausnahme wird automatisch deaktiviert, wenn eine Prozedur beendet wird.  
  
 Um zu verhindern, dass Fehlerbehandlungscode ausgeführt, wenn kein Fehler aufgetreten ist, platziert eine `Exit Sub`, `Exit Function`, oder `Exit Property` Anweisung unmittelbar vor der Fehlerbehandlungsroutine, wie das folgende Fragment:  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 Der Fehlerbehandlungscode Hier folgt der `Exit Sub` Anweisung und vor der `End Sub` Anweisung von den Verfahrensfluss abzugrenzen. Sie können Fehlerbehandlungscode an einer beliebigen Stelle in einer Prozedur platzieren.  
  
## <a name="untrapped-errors"></a>Nicht abgefangene Fehler  
 Nicht abgefangene Fehler in Objekten werden an die steuernde Anwendung zurückgegeben, wenn das Objekt als eine ausführbare Datei ausgeführt wird. Nicht abgefangene Fehler werden in der Entwicklungsumgebung an die steuernde Anwendung zurückgegeben, nur, wenn die entsprechenden Optionen festgelegt werden. Finden Sie in Ihrer hostanwendung Dokumentation für eine Beschreibung der Optionen werden sollen, während des Debuggens, wie sie festgelegt, und gibt an, ob der Host Klassen erstellen kann.  
  
 Wenn Sie ein Objekt, die auf andere Objekte zugreift erstellen, sollten Sie alle nicht behandelte Fehler zu behandeln, die sie zurück zu übergeben. Wenn Sie nicht möglich ist, sind, die Fehlercodes in zugeordnet `Err.Number` auf einen Fehler und übergeben sie an den Aufrufer des Objekts zurück. Sie sollten den Fehler festlegen, indem Sie den Fehlercode der `VbObjectError` konstant. Beispielsweise lautet der Fehlercode 1052, weisen Sie ihn wie folgt:  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  Systemfehler beim Aufrufen von Windows Dynamic Link Libraries (DLLs) keine Ausnahmen auslösen und können nicht mit Visual Basic-Fehlerbehebung abgefangen werden. Überprüfen Sie beim Aufrufen von DLL-Funktionen jeden Rückgabewert Erfolg oder Misserfolg (gemäß der API-Spezifikationen), und ein Fehler auftritt, überprüfen Sie den Wert der `Err` des Objekts `LastDLLError` Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel wird zunächst mit der `On Error GoTo` Anweisung, um den Speicherort einer Routine für die Fehlerbehandlung innerhalb einer Prozedur anzugeben. Im Beispiel generiert Versuch ein Division durch 0 (null) Fehlernummer 6. Der Fehler wird in der Fehlerbehandlung Routine behandelt, und Steuerelement dann an die Anweisung, die den Fehler verursacht hat zurückgegeben wird. Die `On Error GoTo 0` -Anweisung deaktiviert das Abfangen von Fehlern. Die `On Error Resume Next` Anweisung dient zum Zurückstellen, Fehlerbehebung, damit der Kontext für den Fehler generiert, die für die nächste Anweisung für bestimmte bekannt sein kann. Beachten Sie, dass `Err.Clear` dient zum Löschen der `Err` Eigenschaften des Objekts, nachdem der Fehler behandelt wird.  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Resume-Anweisung](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Fehlermeldungen](../../../visual-basic/language-reference/error-messages/index.md)  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
