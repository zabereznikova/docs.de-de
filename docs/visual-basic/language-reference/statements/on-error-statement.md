---
title: On Error-Anweisung
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
ms.openlocfilehash: 7e007d59292fc577c0c8927766423ba6f7896a71
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873184"
---
# <a name="on-error-statement-visual-basic"></a>On Error-Anweisung (Visual Basic)

Aktiviert eine Fehler Behandlungs Routine und gibt den Speicherort der Routine innerhalb einer Prozedur an. kann auch verwendet werden, um eine Fehler Behandlungs Routine zu deaktivieren. Die `On Error` -Anweisung wird bei der unstrukturierten Fehlerbehandlung verwendet und kann anstelle der strukturierten Ausnahmebehandlung verwendet werden. Die [strukturierte Ausnahmebehandlung](../../../standard/exceptions/index.md) ist in .NET integriert, ist im Allgemeinen effizienter und wird daher empfohlen, wenn Laufzeitfehler in der Anwendung behandelt werden.

 Ohne Fehlerbehandlung oder Ausnahmebehandlung ist jeder auftretende Laufzeitfehler schwerwiegend: eine Fehlermeldung wird angezeigt, und die Ausführung wird beendet.

> [!NOTE]
> Das- `Error` Schlüsselwort wird auch in der [Error-Anweisung](error-statement.md)verwendet, die aus Gründen der Abwärtskompatibilität unterstützt wird.

## <a name="syntax"></a>Syntax

```vb
On Error { GoTo [ line | 0 | -1 ] | Resume Next }
```

## <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`GoTo`*Zeile*|Aktiviert die Fehler Behandlungs Routine, die an der im erforderlichen *Zeilen* Argument angegebenen Zeile beginnt. Das *Zeilen* Argument ist eine beliebige Zeilen Bezeichnung oder Zeilennummer. Wenn ein Laufzeitfehler auftritt, Steuern Sie Verzweigungen in die angegebene Zeile, sodass der Fehlerhandler aktiv wird. Die angegebene Zeile muss sich in derselben Prozedur wie die- `On Error` Anweisung befinden, oder es tritt ein Kompilierzeitfehler auf.|
|`GoTo 0`|Deaktiviert den aktivierten Fehlerhandler in der aktuellen Prozedur und setzt ihn auf zurück `Nothing` .|
|`GoTo -1`|Deaktiviert die aktivierte Ausnahme in der aktuellen Prozedur und setzt Sie auf zurück `Nothing` .|
|`Resume Next`|Gibt an, dass die Steuerung bei Auftreten eines Lauf zeitfehlers direkt nach der Anweisung, in der der Fehler aufgetreten ist, an die Anweisung weitergeleitet wird und die Ausführung von diesem Punkt aus fortgesetzt wird. Verwenden Sie dieses Formular anstelle des `On Error GoTo` Zugriffs auf Objekte.|

## <a name="remarks"></a>Bemerkungen

> [!NOTE]
> Es empfiehlt sich, nach Möglichkeit eine strukturierte Ausnahmebehandlung in Ihrem Code zu verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und die-Anweisung zu verwenden `On Error` . Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md).

 Ein "aktivierter" Fehlerhandler ist ein Fehlerhandler, der von einer-Anweisung aktiviert wird `On Error` . Ein "aktiver" Fehlerhandler ist ein aktivierter Handler, der gerade einen Fehler behandelt.

 Wenn ein Fehler auftritt, während ein Fehlerhandler aktiv ist (zwischen dem Auftreten des Fehlers und einer-,-,- `Resume` `Exit Sub` `Exit Function` oder `Exit Property` -Anweisung), kann der Fehlerhandler der aktuellen Prozedur den Fehler nicht verarbeiten. Die Steuerung wird an die aufrufenden Prozedur zurückgegeben.
  
 Wenn die aufrufende Prozedur einen aktivierten Fehlerhandler aufweist, wird Sie zur Behandlung des Fehlers aktiviert. Wenn der Fehlerhandler der aufrufenden Prozedur ebenfalls aktiv ist, wird die Steuerung durch vorherige Aufruf Prozeduren zurückgeleitet, bis ein aktivierter, jedoch inaktiver Fehlerhandler gefunden wird. Wenn kein solcher Fehlerhandler gefunden wird, ist der Fehler an dem Punkt, an dem er tatsächlich aufgetreten ist, schwerwiegend.
  
 Jedes Mal, wenn der Fehlerhandler die Steuerung zurück an eine aufrufenden Prozedur übergibt, wird dieses Verfahren zur aktuellen Prozedur. Sobald ein Fehlerhandler in einer Prozedur behandelt wird, wird die Ausführung in der aktuellen Prozedur an dem von der-Anweisung festgelegten Punkt fortgesetzt `Resume` .
  
> [!NOTE]
> Eine Fehler Behandlungs Routine ist weder eine `Sub` Prozedur noch eine `Function` Prozedur. Es handelt sich um einen Code Abschnitt, der durch eine Zeilen Bezeichnung oder eine Zeilennummer gekennzeichnet ist.
  
## <a name="number-property"></a>Number-Eigenschaft

 Fehlerbehandlungsroutinen basieren auf dem Wert in der- `Number` Eigenschaft des- `Err` Objekts, um die Ursache des Fehlers zu bestimmen. Die Routine sollte relevante Eigenschaftswerte im Objekt testen oder speichern `Err` , bevor ein anderer Fehler auftreten kann, oder bevor eine Prozedur aufgerufen wird, die möglicherweise einen Fehler verursacht. Die Eigenschaftswerte im- `Err` Objekt spiegeln nur den letzten Fehler wider. Die Fehlermeldung, die zugeordnet `Err.Number` ist, ist in enthalten `Err.Description` .  
  
## <a name="throw-statement"></a>Throw-Anweisung  

 Ein Fehler, der mit der-Methode ausgelöst wird, `Err.Raise` legt die- `Exception` Eigenschaft auf eine neu erstellte Instanz der- <xref:System.Exception> Klasse fest. Um das Auftreten von Ausnahmen abgeleiteter Ausnahme Typen zu unterstützen, `Throw` wird eine-Anweisung in der-Sprache unterstützt. Dabei wird ein einzelner Parameter benötigt, bei dem es sich um die Ausnahme Instanz handelt. Im folgenden Beispiel wird gezeigt, wie diese Funktionen mit der vorhandenen Unterstützung für die Ausnahmebehandlung verwendet werden können:

 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 Beachten Sie, dass die- `On Error GoTo` Anweisung unabhängig von der Exception-Klasse alle Fehler abgefangen hat.
  
## <a name="on-error-resume-next"></a>Bei Fehler fortsetzen als nächstes

 `On Error Resume Next` bewirkt, dass die Ausführung mit der Anweisung unmittelbar nach der-Anweisung fortgesetzt wird, die den Laufzeitfehler verursacht hat, oder mit der-Anweisung, die unmittelbar nach dem letzten Aufruf der Prozedur, die die Anweisung enthält, ausgeführt wird `On Error Resume Next` . Mit dieser Anweisung kann die Ausführung trotz eines Lauf zeitfehlers fortgesetzt werden. Sie können die Fehler Behandlungs Routine platzieren, in der der Fehler auftritt, anstatt die Steuerung an einen anderen Speicherort innerhalb der Prozedur zu übertragen. Wenn eine- `On Error Resume Next` Anweisung aufgerufen wird, wenn eine andere Prozedur aufgerufen wird, sollten Sie `On Error Resume Next` in jeder aufgerufenen Routine eine-Anweisung ausführen, wenn Sie eine Inline Fehlerbehandlung innerhalb dieser Routine ausführen möchten.
  
> [!NOTE]
> Das- `On Error Resume Next` Konstrukt kann bei der `On Error GoTo` Behandlung von Fehlern, die während des Zugriffs auf andere Objekte generiert werden, vorzuziehen sein. `Err`Durch das überprüfen nach jeder Interaktion mit einem Objekt werden Mehrdeutigkeiten darüber entfernt, auf welches Objekt der Code zugegriffen hat. Sie können sicherstellen, welches Objekt den Fehlercode in eingefügt `Err.Number` hat, und welches Objekt den Fehler ursprünglich generiert hat (das in angegebene Objekt `Err.Source` ).

## <a name="on-error-goto-0"></a>Bei Fehler "GoTo 0"

 `On Error GoTo 0` deaktiviert die Fehlerbehandlung in der aktuellen Prozedur. Die Zeile 0 wird nicht als Start des Fehler Behandlungs Codes angegeben, auch wenn die Prozedur eine Zeile mit der nummerierten 0 enthält. Ohne eine- `On Error GoTo 0` Anweisung wird ein Fehlerhandler automatisch deaktiviert, wenn eine Prozedur beendet wird.

## <a name="on-error-goto--1"></a>Bei Fehler "GoTo-1"

 `On Error GoTo -1` deaktiviert die Ausnahme in der aktuellen Prozedur. Die Zeile-1 wird nicht als Start des Fehler Behandlungs Codes angegeben, auch wenn die Prozedur eine Zeile mit der nummerierten-1 enthält. Ohne eine- `On Error GoTo -1` Anweisung wird eine Ausnahme automatisch deaktiviert, wenn eine Prozedur beendet wird.

 Um zu verhindern, dass der Fehler Behandlungs Code ausgeführt wird, wenn kein Fehler aufgetreten ist, platzieren Sie eine- `Exit Sub` ,- `Exit Function` oder- `Exit Property` Anweisung unmittelbar vor der Fehler Behandlungs Routine, wie im folgenden Fragment:

 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]

 Hier befolgt der Fehler Behandlungs Code die `Exit Sub` -Anweisung und steht vor der- `End Sub` Anweisung, um Sie vom Ablauf der Prozedur zu trennen. Sie können den Code für die Fehlerbehandlung an beliebiger Stelle in einer Prozedur platzieren.

## <a name="untrapped-errors"></a>Nicht aufgetreppte Fehler

 Nicht aufgetreppte Fehler in Objekten werden an die steuernde Anwendung zurückgegeben, wenn das Objekt als ausführbare Datei ausgeführt wird. Innerhalb der Entwicklungsumgebung werden nicht aufgetreppte Fehler nur dann an die steuernde Anwendung zurückgegeben, wenn die richtigen Optionen festgelegt sind. Eine Beschreibung der Optionen, die während des Debuggens festgelegt werden müssen, und der Art und Weise, wie der Host Klassen erstellen kann, finden Sie in der Dokumentation der Host Anwendung.

 Wenn Sie ein Objekt erstellen, das auf andere Objekte zugreift, sollten Sie versuchen, nicht behandelte Fehler zu behandeln, die zurückgegeben werden. Wenn dies nicht möglich ist, ordnen Sie die Fehlercodes in `Err.Number` einem ihrer eigenen Fehler zu, und übergeben Sie Sie dann wieder an den Aufrufer des Objekts. Sie sollten den Fehler angeben, indem Sie den Fehlercode der `VbObjectError` Konstante hinzufügen. Wenn der Fehlercode z. b. 1052 lautet, weisen Sie ihn wie folgt zu:

 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]

> [!CAUTION]
> System Fehler bei Aufrufen von Windows Dynamic Link Libraries (DLLs) geben keine Ausnahmen aus und können nicht mit Visual Basic fehlerabfang nicht erfasst werden. Wenn Sie DLL-Funktionen aufrufen, sollten Sie jeden Rückgabewert auf Erfolg oder Fehler (gemäß den API-Spezifikationen) überprüfen. Überprüfen Sie im Fall eines Fehlers den Wert in der `Err` -Eigenschaft des-Objekts `LastDLLError` .

## <a name="example"></a>Beispiel

 In diesem Beispiel wird zuerst die `On Error GoTo` -Anweisung verwendet, um den Speicherort einer Fehler Behandlungs Routine innerhalb einer Prozedur anzugeben. Im Beispiel generiert ein Versuch, eine Division durch 0 (null), die Fehlernummer 6. Der Fehler wird in der Fehler Behandlungs Routine behandelt, und die Steuerung wird dann an die Anweisung zurückgegeben, die den Fehler verursacht hat. Mit der- `On Error GoTo 0` Anweisung wird die Fehlerbehebung deaktiviert. Anschließend wird die- `On Error Resume Next` Anweisung verwendet, um das Abfangen von Fehlern zu verzögern, sodass der Kontext für den Fehler, der von der nächsten Anweisung generiert wird, auf bestimmte Weise bekannt ist. Beachten Sie, dass `Err.Clear` verwendet wird, um die Eigenschaften des Objekts zu löschen, `Err` nachdem der Fehler behandelt wurde.

 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]

## <a name="requirements"></a>Anforderungen

 **Namespace:** [Microsoft. VisualBasic](../runtime-library-members.md)

 **Assembly:** Visual Basic Lauf Zeit Bibliothek (in Microsoft.VisualBasic.dll)

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [End Statement](end-statement.md)
- [Exit-Anweisung](exit-statement.md)
- [Resume-Anweisung](resume-statement.md)
- [Fehlermeldungen](../error-messages/index.md)
- [Try... Catch... Abschließend-Anweisung](try-catch-finally-statement.md)
