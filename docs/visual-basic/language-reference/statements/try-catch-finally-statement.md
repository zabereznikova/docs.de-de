---
title: Try...Catch...Finally-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: "69"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08de4939960d8297269c82b1b040537dd43f3038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally-Anweisung (Visual Basic)
Bietet eine Möglichkeit, einige oder alle möglichen Fehler zu behandeln, die beim Ausführen von Code in einem bestimmten Codeblock auftreten können.  
  
## <a name="syntax"></a>Syntax  
  
```  
Try  
    [ tryStatements ]  
    [ Exit Try ]  
[ Catch [ exception [ As type ] ] [ When expression ]  
    [ catchStatements ]  
    [ Exit Try ] ]  
[ Catch ... ]  
[ Finally  
    [ finallyStatements ] ]  
End Try  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`tryStatements`|Dies ist optional. Anweisung(en), in dem ein Fehler auftreten kann. Kann eine Verbundanweisung sein.|  
|`Catch`|Dies ist optional. Mehrere `Catch` Blöcke zulässig. Wenn eine Ausnahme tritt bei der Verarbeitung der `Try` blockieren, jede `Catch` -Anweisung überprüft wird, in Textform Reihenfolge zu bestimmen, ob sie mit die Ausnahme behandelt `exception` , die die Ausnahme, die ausgelöst wurde, darstellt.|  
|`exception`|Dies ist optional. Ein beliebiger Variablenname. Der Anfangswert von `exception` ist der Wert des ausgelösten Fehlers. Mit verwendet `Catch` Angabe den Fehler abgefangen. Wenn nicht angegeben, die `Catch` Anweisung fängt jede Ausnahme.|  
|`type`|Dies ist optional. Gibt den Typ der Klasse Filter. Wenn der Wert der `exception` wird von den vom angegebenen Typ `type` oder eines abgeleiteten Typs, der Bezeichner wird an das Ausnahmeobjekt gebunden.|  
|`When`|Dies ist optional. Ein `Catch` -Anweisung mit einem `When` -Klausel fängt Ausnahmen nur, wenn `expression` ergibt `True`. Ein `When` Klausel wird nur angewendet, nachdem der Typ der Ausnahme überprüft und `expression` bezieht sich möglicherweise auf den Bezeichner, der die Ausnahme darstellt.|  
|`expression`|Dies ist optional. Muss implizit in `Boolean`. Ein beliebiger Ausdruck, der einen generischen Filter beschreibt. In der Regel verwendet zum Filtern nach Fehlernummer. Mit verwendet `When` Schlüsselwort an Umstände, unter denen der Fehler abgefangen wird.|  
|`catchStatements`|Dies ist optional. Anweisung(en), um Fehler zu behandeln, die in der zugeordneten auftreten `Try` Block. Kann eine Verbundanweisung sein.|  
|`Exit Try`|Dies ist optional. Schlüsselwort, das von unterbricht die `Try...Catch...Finally` Struktur. Die Ausführung wird fortgesetzt, durch den Code direkt nach der `End Try` Anweisung. Die `Finally` -Anweisung wird weiterhin ausgeführt werden. Nicht zulässig `Finally` blockiert.|  
|`Finally`|Dies ist optional. Ein `Finally` Block wird immer ausgeführt, wenn die Ausführung eines beliebigen Teils der `Try...Catch` Anweisung.|  
|`finallyStatements`|Dies ist optional. Anweisung(en), die ausgeführt werden, nachdem sämtlicher Fehler aufgetreten ist.|  
|`End Try`|Beendet die `Try...Catch...Finally` Struktur.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie erwarten, dass eine bestimmte Ausnahme während eines bestimmten Bereichs des Codes auftreten kann, platzieren Sie den Code in eine `Try` blockieren und das Verwenden einer `Catch` Block zum Beibehalten der Kontrolle und die Ausnahme zu behandeln, wenn diese auftreten.  
  
 Ein `Try…Catch` -Anweisung besteht aus einem `Try` -Block gefolgt von einer oder mehreren `Catch` Klauseln, die Handler für verschiedene Ausnahmen angeben. Wenn eine Ausnahme ausgelöst wird, einem `Try` Block [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sucht nach der `Catch` -Anweisung, die die Ausnahme behandelt. Wenn kein übereinstimmendes `Catch` Anweisung wurde nicht gefunden, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] überprüft die Methode, die die aktuelle Methode ist und so weiter oben in der Aufrufliste aufgerufen. Wenn kein `Catch` -Block gefunden wird, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zeigt eine nicht behandelte Ausnahme-Nachricht an den Benutzer und beendet die Ausführung des Programms.  
  
 Sie können mehrere `Catch` -Anweisung in eine `Try…Catch` Anweisung. Wenn Sie die Reihenfolge der dazu die `Catch` Klauseln ist wichtig, weil sie in der Reihenfolge untersucht werden. Fangen Sie spezifischere Ausnahmen vor den weniger spezifischen ab.  
  
 Die folgenden `Catch` Anweisung Bedingungen sind die spezifischen und fängt alle Ausnahmen, die Ableitung der <xref:System.Exception> Klasse. Kehren Sie in der Regel mithilfe einer dieser Varianten als das letzte `Catch` -block in der `Try...Catch...Finally` -Struktur verwenden, nachdem alle Sie erwarten, dass bestimmten Ausnahmen abfangen. Ablaufsteuerung erreichen nie eine `Catch` Block, der entweder diese Varianten folgt.  
  
-   Die `type` ist `Exception`, beispielsweise:`Catch ex As Exception`  
  
-   Die Anweisung hat keine `exception` -Variable verwenden, beispielsweise:`Catch`  
  
 Wenn eine `Try…Catch…Finally` in einer anderen Anweisung geschachtelt ist `Try` Block [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zuerst überprüft jede `Catch` -Anweisung in der innersten `Try` Block. Wenn kein übereinstimmender `Catch` Anweisung gefunden wird, wird die Suche wird fortgesetzt, die `Catch` Anweisungen des äußeren `Try…Catch…Finally` Block.  
  
 Lokale Variablen aus einem `Try` Block sind nicht verfügbar in einer `Catch` blockiert werden, da sie separate Datenblocks sind. Wenn Sie eine Variable in mehreren Blöcken verwenden möchten, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.  
  
> [!TIP]
>  Die `Try…Catch…Finally` -Anweisung ist als IntelliSense-Codeausschnitt verfügbar. Erweitern Sie im Codeausschnitt-Manager, **Codemustern – Wenn Sie für jedes try…catch, Eigenschaft usw.**, und klicken Sie dann **Fehlerbehandlung (Ausnahmen)**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="finally-block"></a>Finally-Block  
 Eine oder mehrere Anweisungen aufweist, die ausgeführt werden muss, bevor Sie verlassen der `Try` verwenden eine `Finally` Block. Die Steuerung an die `Finally` zu blockieren, nur verwendet werden, bevor sie übergeben die `Try…Catch` Struktur. Dies gilt auch, wenn eine Ausnahme in eine beliebige Stelle tritt auf, die `Try` Struktur.  
  
 Ein `Finally` -Block ist nützlich zum Ausführen von Code, ausführen muss, auch wenn eine Ausnahme aufgetreten ist. Erhält die Kontrolle der `Finally` Block unabhängig davon, wie der `Try...Catch` -Block beendet wird.  
  
 Der Code in einer `Finally` -Block ausgeführt, selbst wenn im Code auftritt eine `Return` -Anweisung in einer `Try` oder `Catch` Block. Steuerelement übergibt keine aus einer `Try` oder `Catch` -block, um das entsprechende `Finally` -block in den folgenden Fällen:  
  
-   Ein [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md) festgestellt wird, der `Try` oder `Catch` Block.  
  
-   Ein <xref:System.StackOverflowException> wird ausgelöst, der `Try` oder `Catch` Block.  
  
 Es ist nicht zulässig, die explizit die Ausführung in übertragen einer `Finally` Block. Übertragen die Ausführung von einem `Finally` Block ist nicht gültig, außer durch eine Ausnahme.  
  
 Wenn eine `Try` Anweisung enthält keine mindestens `Catch` Block, es darf eine `Finally` Block.  
  
> [!TIP]
>  Wenn Sie keine spezifische Ausnahmen abfangen der `Using` Anweisung verhält sich wie ein `Try…Finally` Block und garantiert die Freigabe von Ressourcen, unabhängig davon, wie Sie den Block zu beenden. Dies gilt auch bei einer nicht behandelten Ausnahme. Weitere Informationen finden Sie unter [using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="exception-argument"></a>Ausnahme-Argument  
 Die `Catch` Block `exception` Argument ist eine Instanz von der <xref:System.Exception> Klasse oder eine Klasse, abgeleitet wird, die `Exception` Klasse. Die `Exception` Klasseninstanz in aufgetretenen Fehlers entspricht der `Try` Block.  
  
 Die Eigenschaften der `Exception` -Objekt Hilfe ', um die Ursache und den Speicherort einer Ausnahme anzugeben. Z. B. die <xref:System.Exception.StackTrace%2A> Eigenschaft führt die aufgerufenen Methoden, die auf die Ausnahme, die Hilfestellung beim Suchen des Fehlers im Code geführt hat. <xref:System.Exception.Message%2A>Gibt eine Meldung, die die Ausnahme beschreibt. <xref:System.Exception.HelpLink%2A>Gibt einen Link zu einer zugeordneten Hilfedatei zurück. <xref:System.Exception.InnerException%2A>Gibt die `Exception` Objekt, das die aktuelle Ausnahme oder es verursacht zurückgegebenen `Nothing` Wenn keine ursprüngliche `Exception`.  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Überlegungen zur Verwendung von einem... Catch-Anweisung  
 Verwenden einer `Try…Catch` Anweisung nur für das Vorkommen des Programm ungewöhnliche oder unerwartete Ereignisse zu signalisieren. Die Gründe dafür:  
  
-   Abfangen von Ausnahmen zur Laufzeit zusätzlichen Verarbeitungsaufwand erstellt und wird wahrscheinlich langsamer als die Prüfung vor, um Ausnahmen zu vermeiden.  
  
-   Wenn eine `Catch` Block wird nicht ordnungsgemäß verarbeitet wird, die Ausnahme möglicherweise nicht ordnungsgemäß Benutzern gemeldet werden.  
  
-   Behandlung von Ausnahmen wird ein Programm komplexer.  
  
 Sie brauchen nicht immer eine `Try…Catch` Anweisung für eine Bedingung überprüft, die unwahrscheinlich ist. Das folgende Beispiel überprüft, ob eine Datei vorhanden ist, bevor Sie versuchen, ihn zu öffnen. Dies reduziert die Notwendigkeit für das Abfangen einer Ausnahme wird ausgelöst, durch die <xref:System.IO.File.OpenText%2A> Methode.  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Stellen Sie sicher, Code in `Catch` Blöcke Ausnahmen auf Benutzer über threadsichere Protokollierung oder entsprechende Nachrichten können ordnungsgemäß gemeldet werden. Andernfalls bleiben Ausnahmen möglicherweise unbekannt.  
  
## <a name="async-methods"></a>Asynchrone Methoden  
 Wenn Sie eine Methode mit kennzeichnen die [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Methode. Eine Anweisung mit der `Await` -Operator hält die Ausführung der Methode, bis die erwartete Aufgabe abgeschlossen ist. Die Aufgabe stellt derzeit ausgeführte Arbeit dar. Wenn die Aufgabe, die mit zugeordnetem der `Await` Operator abgeschlossen ist, setzt der Ausführung in derselben Methode. Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 Eine Aufgabe, die von einer asynchronen Methode zurückgegeben kann in einem fehlerhaften Zustand enden, der angibt, dass es aufgrund eines Ausnahmefehlers abgeschlossen. Eine Aufgabe kann auch in einem abgebrochenen Zustand, was zur Folge Enden einer `OperationCanceledException` aus der "await"-Ausdruck ausgelöst wird. Um entweder Typ der Ausnahme abzufangen, platzieren Sie die `Await` Ausdruck, der die Aufgabe zugeordnet ist ein `Try` blockieren, und fangen Sie die Ausnahme in der `Catch` Block. Ein Beispiel finden Sie weiter unten in diesem Thema.  
  
 Eine Aufgabe kann in einem fehlerhaften Zustand befinden, da mehrere Ausnahmen für die fehlgeschlagene verantwortlich sind. Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein. Wenn Sie eine solche Aufgabe warten, die abgefangene Ausnahme ist nur eine der Ausnahmen aus, und Sie können nicht vorhersagen, welche Ausnahme abgefangen wird. Ein Beispiel finden Sie weiter unten in diesem Thema.  
  
 Ein `Await` Ausdruck nicht innerhalb einer `Catch` Block oder `Finally` Block.  
  
## <a name="iterators"></a>Iteratoren  
 Ein Iteratorfunktion oder `Get` Accessor führt eine benutzerdefinierte Iteration durch eine Auflistung. Ein Iterator verwendet eine [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element der Auflistung zu einem Zeitpunkt zurückzugeben. Sie rufen eine Iteratorfunktion mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Ein `Yield` Anweisung kann innerhalb einer `Try` Block. Ein `Try` Block mit einer `Yield` -Anweisung kann verfügen `Catch` blockiert und können eine `Finally` Block. Finden Sie im Abschnitt "versuchen Blöcke in Visual Basic" [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) ein Beispiel.  
  
 Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.  
  
 Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, eine `Catch` Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird. Ein `Catch` Block innerhalb einer Iteratorfunktion fängt nur Ausnahmen, die innerhalb der Iteratorfunktion auftreten.  
  
## <a name="partial-trust-situations"></a>Teilweise vertrauenswürdigen Umgebungen  
 In teilweise vertrauenswürdigen Umgebungen, z. B. eine Anwendung, die auf einer Netzwerkfreigabe gehostet `Try...Catch...Finally` fängt keine Ausnahmen zur Codezugriffssicherheit, die auftreten, bevor die Methode, die den Aufruf enthält aufgerufen wird. Im folgenden Beispiel, wenn auf einer Serverfreigabe und dort ablegen, wird der Fehler "System.Security.SecurityException: Fehler bei der Anforderung." Weitere Informationen zu Sicherheitsausnahmen führen, finden Sie unter der <xref:System.Security.SecurityException> Klasse.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 In solchen einer teilweise vertrauenswürdigen Kontext versetzen stehen Ihnen die `Process.Start` Anweisung in einem separaten `Sub`. Der erste Aufruf der `Sub` schlägt fehl. Dadurch `Try...Catch` abzufangen, bevor die `Sub` enthält `Process.Start` wird gestartet und die Sicherheitsausnahme erstellt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Struktur der `Try...Catch...Finally` Anweisung.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `CreateException` -Methode löst eine `NullReferenceException`. Der Code, der die Ausnahme generiert befindet sich nicht in einem `Try` Block. Aus diesem Grund die `CreateException` Methode die Ausnahme nicht behandelt. Die `RunSample` Methode die Ausnahme behandeln, da der Aufruf der `CreateException` Methode wird in eine `Try` Block.  
  
 Das Beispiel schließt `Catch` Anweisungen für mehrere Typen von Ausnahmen, geordnet von der spezifischsten bis auf die allgemeinste.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine `Catch When` Anweisung, um nach einem bedingten Ausdruck zu filtern. Wenn der bedingte Ausdruck ergibt `True`, den Code in der `Catch` -Block ausgeführt.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ist ein `Try…Catch` -Anweisung, die in enthalten ist eine `Try` Block. Die innere `Catch` Block löst eine Ausnahme aus, dessen `InnerException` -Eigenschaft auf die ursprüngliche Ausnahme festgelegt. Die äußere `Catch` Block meldet seine eigene Ausnahme und der inneren Ausnahme.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Ausnahmebehandlung für asynchrone Methoden veranschaulicht. Eine Ausnahme abfangen, die für eine asynchrone Aufgabe, gilt die `Await` Ausdruck ist einer `Try` Block und des Aufrufers, der die Ausnahme ist aufgetreten, in der `Catch` Block.  
  
 Heben Sie die Auskommentierung der Zeile `Throw New Exception` im Beispiel auf, um die Ausnahmebehandlung zu veranschaulichen. Die Ausnahme abgefangen wird der `Catch` blockieren, der Aufgabe `IsFaulted` -Eigenschaftensatz auf `True`, und die Aufgabe `Exception.InnerException` Eigenschaftensatz auf die Ausnahme.  
  
 Heben Sie die Auskommentierung der Zeile `Throw New OperationCancelledException` auf, um zu veranschaulichen, was beim Abbrechen eines asynchronen Prozesses passiert. Die Ausnahme abgefangen wird der `Catch` Block und des Tasks `IsCanceled` -Eigenschaftensatz auf `True`. Unter bestimmten Bedingungen, die für dieses Beispiel nicht gelten jedoch `IsFaulted` festgelegt ist, um `True` und `IsCanceled` auf festgelegt ist `False`.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Behandlung von Ausnahmen in Fällen, in denen mehrere Aufgaben zu mehreren Ausnahmen führen können. Die `Try` -Block umfasst die `Await` Ausdruck für den Task, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> zurückgegeben. Die Aufgabe ist abgeschlossen, bei der drei, auf die Aufgaben <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> angewendet wird abgeschlossen sind.  
  
 Jede der drei Aufgaben löst eine Ausnahme aus. Die `Catch` -Block iteriert durch die Ausnahmen, die in sind die `Exception.InnerExceptions` -Eigenschaft des Tasks, `Task.WhenAll` zurückgegeben.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:System.Exception>  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Empfohlene Vorgehensweisen für die Verwendung von Codeausschnitten](/visualstudio/ide/best-practices-for-using-code-snippets)  
 [Ausnahmebehandlung](https://msdn.microsoft.com/library/dd997415)  
 [Throw-Anweisung](../../../visual-basic/language-reference/statements/throw-statement.md)
