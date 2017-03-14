---
title: "On Error Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.OnError"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, control flow"
  - "Resume Next statement"
  - "errors [Visual Basic], trapping"
  - "error handling, On Error statement"
  - "Next statement, On Error"
  - "control flow, branching"
  - "Error keyword"
  - "execution, conditional"
  - "Resume statement, and On Error statement"
  - "Error statement, and On Error statement"
  - "GoTo statement, and On Error statement"
  - "branching, on error"
  - "conditional statements, On Error"
  - "On Error statement, syntax"
  - "On keyword"
  - "run-time errors, handling"
  - "On Error statement"
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# On Error Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Aktiviert eine Fehlerbehandlungsroutine und gibt die Position der Routine innerhalb einer Prozedur an. Kann auch zum Deaktivieren einer Fehlerbehandlungsroutine verwendet werden.  
  
 Ohne `On Error`\-Anweisung ist jeder auftretende Laufzeitfehler ein schwerwiegender Fehler, d. h., es wird eine Fehlermeldung angezeigt und die Ausführung angehalten.  
  
 Beschränken wird empfohlen, vor, verwenden Sie die strukturierte Ausnahmebehandlung im Code anstelle der unstrukturierten Ausnahmebehandlung und der `On Error`\-Anweisung.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Das `Error`\-Schlüsselwort wird auch in der [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md) verwendet, die aus Gründen der Abwärtskompatibilität unterstützt wird.  
  
## Syntax  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`GoTo` `line`|Aktiviert die Fehlerbehandlungsroutine, die bei der im erforderlichen `line`\-Argument angegebenen Zeile beginnt.  Das `line`\-Argument ist eine beliebige Zeilenbezeichnung oder Zeilennummer.  Wenn ein Laufzeitfehler auftritt, zweigt die Steuerung zu der angegebenen Zeile ab, wodurch der Fehlerhandler aktiviert wird.  Die angegebene Zeile muss sich in der gleichen Prozedur befinden wie die `On Error`\-Anweisung, andernfalls tritt ein Kompilierungsfehler auf.|  
|`GoTo` 0|Deaktiviert den aktivierten Fehlerhandler in der aktuellen Prozedur und setzt ihn auf `Nothing` zurück.|  
|`GoTo` \-1|Deaktiviert die aktivierte Ausnahme in der aktuellen Prozedur und setzt sie auf `Nothing` zurück.|  
|`Resume Next`|Gibt an, dass beim Auftreten eines Laufzeitfehlers die Steuerung an die Anweisung übergeben wird, die direkt auf die Anweisung folgt, in der der Fehler aufgetreten ist, und die Ausführung an dieser Stelle fortgesetzt wird.  Verwenden Sie beim Zugriff auf Objekte diese Form und nicht `On Error GoTo`.|  
  
## Hinweise  
  
> [!NOTE]
>  Es wird empfohlen, die strukturierte Ausnahmebehandlung im Code verwenden, wann immer dies möglich ist, und nicht anhand der unstrukturierten Ausnahmebehandlung und der `On Error`\-Anweisung.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Ein "aktivierter" Fehlerhandler ist ein Fehlerhandler, der durch eine `On Error`\-Anweisung aktiviert wird.  Ein "aktiver" Fehlerhandler ist ein aktivierter Handler, der gegenwärtig einen Fehler behandelt.  
  
 Wenn ein Fehler auftritt, während ein Fehlerhandler aktiv ist \(zwischen dem Auftreten des Fehlers und einer der Anweisungen `Resume`, `Exit Sub`, `Exit Function` oder `Exit Property`\), kann der Fehlerhandler der aktuellen Prozedur den Fehler nicht behandeln.  Die Steuerung wird an die aufrufende Prozedur zurückgegeben.  
  
 Wenn die aufrufende Prozedur einen aktivierten Fehlerhandler besitzt, wird dieser aktiv, um den Fehler zu behandeln.  Wenn der Fehlerhandler der aufrufenden Prozedur außerdem aktiv ist, werden die vorherigen aufrufenden Prozeduren durchgegangen, bis ein aktivierter, aber inaktiver Fehlerhandler gefunden wird, bei dem die Ausführung dann fortgesetzt wird.  Wenn kein solcher Fehlerhandler gefunden wird, ist der Fehler an dem Punkt schwerwiegend, an dem er tatsächlich auftrat.  
  
 Jedes Mal, wenn der Fehlerhandler die Steuerung wieder an eine aufrufende Prozedur übergibt, wird diese Prozedur zur aktuellen Prozedur.  Sobald ein Fehler durch einen Fehlerhandler in einer beliebigen Prozedur behandelt wurde, wird die Ausführung in der aktuellen Prozedur an dem durch die `Resume`\-Anweisung angegebenen Punkt wieder aufgenommen.  
  
> [!NOTE]
>  Eine Fehlerbehandlungsroutine ist keine `Sub`\-Prozedur oder `Function`\-Prozedur.  Sie ist ein Codeabschnitt, der durch eine Zeilenbezeichnung oder eine Zeilennummer gekennzeichnet wird.  
  
## Number\-Eigenschaft  
 Fehlerbehandlungsroutinen benötigen den Wert in der `Number`\-Eigenschaft des `Err`\-Objekts, um die Ursache des Fehlers bestimmen zu können.  Die Routine sollte die relevanten Eigenschaftswerte im `Err`\-Objekt überprüfen oder speichern, bevor ein anderer Fehler auftreten kann oder bevor eine Prozedur aufgerufen wird, die einen Fehler verursachen kann.  Die Eigenschaftswerte im `Err`\-Objekt geben nur den letzten Fehler wieder.  Die `Err.Number` zugeordnete Fehlermeldung befindet sich in `Err.Description`.  
  
## Throw\-Anweisung  
 Ein Fehler, der mit der `Err.Raise`\-Methode ausgelöst wird, legt die `Exception`\-Eigenschaft auf eine neu erstellte Instanz der <xref:System.Exception>\-Klasse fest.  Um das Auslösen von Ausnahmen abgeleiteter Ausnahmetypen zu unterstützen, wird in dieser Sprache die `Throw`\-Anweisung unterstützt.  Hierbei ist ein einzelner Parameter die auszulösende Ausnahmeinstanz.  Das folgende Beispiel veranschaulicht die Verwendung dieser Features in Verbindung mit der unterstützten Ausnahmebehandlung:  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 Beachten Sie, dass die `On Error GoTo`\-Anweisung alle Fehler unabhängig von der Ausnahmeklasse abfängt.  
  
## On Error Resume Next  
 Nach einer On Error Resume Next\-Anweisung wird die Ausführung mit der Anweisung fortgesetzt, die unmittelbar auf die Anweisung folgt, die den Laufzeitfehler verursachte, oder mit der Anweisung, die unmittelbar auf den letzten Aufruf aus derjenigen Prozedur folgt, in der die `On Error Resume Next`\-Anweisung enthalten ist.  Dadurch kann das Programm die Ausführung trotz eines Laufzeitfehlers fortsetzen.  Sie können die Fehlerbehandlungsroutine an die Stelle platzieren, an der der Fehler auftritt, anstatt die Steuerung an eine andere Position innerhalb der Prozedur zu übergeben.  Eine `On Error Resume Next`\-Anweisung wird inaktiv, wenn eine andere Prozedur aufgerufen wird. Deshalb sollten Sie in jeder aufgerufenen Routine eine `On Error Resume Next`\-Anweisung ausführen, wenn eine Inlinefehlerbehandlung in dieser Routine benötigt wird.  
  
> [!NOTE]
>  Das `On Error Resume Next`\-Konstrukt ist `On Error GoTo` bei der Behandlung von Fehlern, die beim Zugriff auf andere Objekte generiert wurden, unter Umständen vorzuziehen.  Durch Überprüfen von `Err` nach jeder Interaktion mit einem Objekt können Sie eindeutig feststellen, auf welches Objekt der Code zugegriffen hat.  Sie können zweifelsfrei ermitteln, welches Objekt den Fehlercode in `Err.Number` eingefügt und welches Objekt den Fehler ursprünglich generiert hat \(das in `Err.Source` angegebene Objekt\).  
  
## On Error GoTo 0  
 `On Error GoTo 0` deaktiviert die Fehlerbehandlung in der aktuellen Prozedur.  Es wird nicht Zeile "0" als Anfang des Fehlerbehandlungscodes angegeben, selbst wenn die Prozedur eine mit der Nummer "0" versehene Zeile enthält.  Ohne eine `On Error GoTo 0`\-Anweisung wird ein Fehlerhandler beim Beenden einer Prozedur automatisch deaktiviert.  
  
## On Error GoTo \-1  
 `On Error GoTo -1` deaktiviert die Ausnahme in der aktuellen Prozedur.  Es wird nicht Zeile \-1 als Anfang des Fehlerbehandlungscodes angegeben, selbst wenn die Prozedur eine mit der Nummer \-1 versehene Zeile enthält.  Ohne eine `On Error GoTo -1`\-Anweisung wird beim Beenden einer Prozedur eine Ausnahme automatisch deaktiviert.  
  
 Um zu verhindern, dass Fehlerbehandlungscode ausgeführt wird, wenn kein Fehler aufgetreten ist, fügen Sie eine der Anweisungen `Exit Sub`, `Exit Function` oder `Exit Property` unmittelbar vor der Fehlerbehandlungsroutine ein, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 Hier steht der Fehlerbehandlungscode nach der `Exit Sub`\-Anweisung und vor der `End Sub`\-Anweisung, sodass er vom übrigen Prozedurablauf getrennt ist.  Sie können Fehlerbehandlungscode an einer beliebigen Stelle in einer Prozedur platzieren.  
  
## Nicht abgefangene Fehler  
 Nicht abgefangene Fehler in Objekten werden an die steuernde Anwendung zurückgegeben, wenn das Objekt als ausführbare Datei verwendet wird.  Innerhalb der Entwicklungsumgebung werden nicht abgefangene Fehler nur dann an die steuernde Anwendung zurückgegeben, wenn die entsprechenden Optionen eingestellt sind.  Informationen dazu, welche Optionen während des Debuggens eingestellt sein sollten, wie Sie diese Optionen einstellen und ob der Host Klassen erstellen kann, finden Sie in der Dokumentation zur Hostanwendung.  
  
 Wenn Sie ein Objekt erstellen, das auf andere Objekte zugreift, sollten Sie versuchen, alle von diesen Objekten zurückgegebenen nicht behandelten Fehler zu beheben.  Falls dies nicht möglich ist, ordnen Sie die Fehlercodes in `Err.Number` einem eigenen Fehler zu und geben sie dann an den Aufrufer des Objekts zurück.  Geben Sie den Fehler an, indem Sie der `VbObjectError`\-Konstante den Fehlercode hinzufügen.  Ist der Fehlercode beispielsweise 1052, weisen Sie ihn wie folgt zu:  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  Ein Systemfehler während eines Aufrufs einer Windows\-DLL \(Dynamic\-Link Library\) löst keine Ausnahme aus und kann nicht mithilfe der Fehlerbehebung von Visual Basic abgefangen werden.  Überprüfen Sie beim Aufrufen von DLL\-Funktionen jeden Rückgabewert dahingehend, ob der Aufruf erfolgreich war \(gemäß der API\-Spezifikationen\), und überprüfen Sie im Falle eines Fehlers den Wert in der `LastDLLError`\-Eigenschaft des `Err`\-Objekts.  
  
## Beispiel  
 In diesem Beispiel wird zuerst mithilfe der `On Error GoTo`\-Anweisung die Position einer Fehlerbehandlungsroutine in einer Prozedur festgelegt.  Im Beispiel generiert der Versuch einer Division durch null die Fehlernummer 6.  Der Fehler wird in der Fehlerbehandlungsroutine behandelt, und das Steuerelement wird dann an die Anweisung zurückgegeben, die den Fehler verursacht hat.  Die `On Error GoTo 0`\-Anweisung deaktiviert das Abfangen von Fehlern.  Danach wird mithilfe der `On Error Resume Next`\-Anweisung die Fehlerbehebung verschoben, sodass der Kontext des von der nächsten Anweisung erzeugten Fehlers eindeutig festgestellt werden kann.  Beachten Sie, dass `Err.Clear` zum Löschen der Eigenschaften des `Err`\-Objekts verwendet wird, nachdem der Fehler behandelt wurde.  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Visual Basic\-Laufzeitbibliothek \(in Microsoft.VisualBasic.dll\)  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>   
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Resume Statement](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [Error Messages](../../../visual-basic/language-reference/error-messages/index.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)