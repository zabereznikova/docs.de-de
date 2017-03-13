---
title: "Try...Catch...Finally Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Try...Catch...Finally"
  - "vb.when"
  - "vb.Finally"
  - "vb.Catch"
  - "vb.Try"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Try...Catch...Finally statements"
  - "Try statement"
  - "try-catch exception handling, Try...Catch...Finally statements"
  - "error handling, while running code"
  - "Try statement, Try...Catch...Finally"
  - "Finally keyword [Visual Basic], Try...Catch...Finally"
  - "Catch statement"
  - "When keyword"
  - "Visual Basic code, handling errors while running"
  - "structured exception handling, Try...Catch...Finally statements"
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 69
---
# Try...Catch...Finally Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Bietet eine Möglichkeit, einige oder alle möglichen Fehler zu behandeln, die in einem bestimmten Codeblock auftreten können, während dieser Code noch ausgeführt wird.  
  
## Syntax  
  
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
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`tryStatements`|Dies ist optional.  Anweisungen, in denen ein Fehler auftreten kann.  Hierbei kann es sich um eine zusammengesetzte Anweisung handeln.|  
|`Catch`|Dies ist optional.  Mehrere `Catch`\-Blöcke sind zulässig.  Wenn beim Verarbeiten des  `Try` \-Blocks eine Ausnahme auftritt, wird jede `Catch`\-Anweisung in Textreihenfolge überprüft, um festzustellen, ob sie die Ausnahme behandelt, wobei `exception` die ausgelöste Ausnahme darstellt.|  
|`exception`|Dies ist optional.  Ein beliebiger Variablenname.  Der Anfangswert von `exception` ist der Wert des ausgelösten Fehlers.  Wird mit `Catch` zur Angabe des abgefangenen Fehlers verwendet.  Wenn keine Angabe erfolgt, fängt die `Catch`\-Anweisung alle Ausnahmen ab.|  
|`type`|Dies ist optional.  Gibt den Typ des Klassenfilters an.  Wenn der Wert von `exception` dem von `type` angegebenen Typ oder einem abgeleiteten Typ entspricht, wird der Bezeichner an das Ausnahmeobjekt gebunden.|  
|`When`|Dies ist optional.  Eine `Catch`\-Anweisung mit einer `When`\-Klausel fängt nur Ausnahmen ab, wenn `expression` `True` ergibt.  Eine `When`\-Klausel wird nur angewendet, nachdem der Typ der Ausnahme überprüft wurde. `expression` kann auf den Bezeichner verweisen, der die Ausnahme darstellt.|  
|`expression`|Dies ist optional.  Muss implizit nach `Boolean` konvertierbar sein.  Ein beliebiger Ausdruck, der einen allgemeinen Filter beschreibt.  Dieses Argument wird meist zum Filtern nach Fehlernummern verwendet.  Wird mit dem `When`\-Schlüsselwort zur Angabe der Umstände, unter denen der Fehler abgefangen wurde, verwendet.|  
|`catchStatements`|Dies ist optional.  Anweisung\(en\) zur Behandlung von Fehlern, die im zugeordneten `Try`\-Block auftreten.  Hierbei kann es sich um eine zusammengesetzte Anweisung handeln.|  
|`Exit Try`|Dies ist optional.  Schlüsselwort zum Ausscheren aus der `Try...Catch...Finally`\-Struktur.  Die Ausführung wird mit dem Code fortgesetzt, der direkt auf die `End Try`\-Anweisung folgt.  Die `Finally`\-Anweisung wird weiterhin ausgeführt.  In `Finally`\-Blöcken nicht zulässig.|  
|`Finally`|Dies ist optional.  Ein `Finally`\-Block wird immer ausgeführt, wenn die Ausführung außerhalb eines beliebigen Teils der `Try...Catch`\-Anweisung erfolgt.|  
|`finallyStatements`|Dies ist optional.  Anweisungen, die ausgeführt werden, nachdem die gesamte übrige Fehlerbehandlung erfolgt ist.|  
|`End Try`|Beendet die `Try...Catch...Finally`\-Struktur.|  
  
## Hinweise  
 Wenn Sie erwarten, dass eine bestimmte Ausnahme während der Ausführung eines bestimmten Codeabschnitts auftreten könnte, fügen Sie diesen Code in einen `Try`\-Block ein, und verwenden Sie einen `Catch`\-Block, um die Kontrolle zu behalten und die Ausnahme zu behandeln, falls sie auftritt.  
  
 Eine `Try…Catch`\-Anweisung besteht aus einem `Try`\-Block gefolgt von einer oder mehreren `Catch`\-Klauseln, die Handler für verschiedene Ausnahmen angeben.  Wenn in einem `Try`\-Block eine Ausnahme ausgelöst wird, sucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] nach der `Catch`\-Anweisung, die die Ausnahme behandelt.  Wenn eine entsprechende `Catch`\-Anweisung nicht gefunden wird, untersucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die Methode, die die aktuelle Methode aufgerufen hat, und so weiter nach oben in der Aufrufliste.  Wird kein `Catch`\-Block gefunden, zeigt [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] eine nicht bearbeitete Ausnahmemeldung für den Benutzer an und hält die Ausführung des Programms an.  
  
 Sie können mehr als eine `Catch`\-Anweisung in einer `Try…Catch`\-Anweisung verwenden.  Wenn Sie dies tun, ist die Reihenfolge der `Catch`\-Klauseln bedeutend, weil sie nacheinander überprüft werden.  Präziser definierte Ausnahmen sollten vor weniger präzisen abgefangen werden.  
  
 Die folgenden `Catch`\-Anweisungsbedingungen sind am unspezifischsten und fangen alle Ausnahmen, die von der <xref:System.Exception>\-Klasse abgeleitet sind, ab.  Sie sollten üblicherweise eine dieser Variationen als letzten `Catch`\-Block in der `Try...Catch...Finally`\-Struktur verwenden, nachdem Sie alle spezifischen Ausnahmen abgefangen haben, die Sie erwarten.  Die Ablaufsteuerung kann einen `Catch`\-Block, auf der eine dieser Variationen folgt, niemals erreichen.  
  
-   Der `type` lautet `Exception`, z. B.: `Catch ex As Exception`  
  
-   Die Anweisung hat keine `exception`\-Variable, Beispiel: `Catch`  
  
 Wenn eine `Try…Catch…Finally`\-Anweisung in einem anderen `Try`\-Block geschachtelt ist, untersucht [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] zunächst jede `Catch`\-Anweisung im innersten `Try`\-Block.  Wenn keine übereinstimmende `Catch`\-Anweisung gefunden wird, wird die Suche in den `Catch`\-Anweisungen äußeren `Try…Catch…Finally`\-Blocks fortgeführt.  
  
 Lokale Variablen aus einem `Try`\-Block sind in einem `Catch`\-Block nicht verfügbar, weil es sich um eigene Blöcke handelt.  Wenn Sie eine Variable in mehreren Blöcken verwenden möchten, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally`\-Struktur.  
  
> [!TIP]
>  Die `Try…Catch…Finally`\-Anweisung ist als IntelliSense\-Codeausschnitt verfügbar.  Erweitern Sie im Codeausschnitt\-Manager **Codemuster \- If, For Each, Try Catch, Property usw.** und dann **Fehlerbehandlung \(Ausnahmen\)**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
## Finally\-Block  
 Wenn Sie über eine oder mehrere Anweisungen verfügen, die ausgeführt werden müssen, bevor die `Try`\-Struktur beendet wird, verwenden Sie einen `Finally`\-Block.  Kurz vor Beendigung der `Try…Catch`\-Struktur wird die Steuerung an den `Finally`\-Block übergeben.  Dies gilt auch, wenn in der `Try`\-Struktur eine Ausnahme auftritt.  
  
 Ein `Finally`\-Block ist nützlich zum Ausführen von Code, der ausgeführt werden muss, selbst wenn eine Ausnahme da ist.  Die Steuerung wird an den `Finally`\-Block übertragen, unabhängig davon, wie der `Try...Catch`\-Block beendet wird.  
  
 Der Code in einem `Finally`\-Block wird ausgeführt, selbst wenn Ihr Code einer `Return`\-Anweisung in einem `Try`\- oder `Catch`\-Block begegnet.  In den folgenden Fällen wird die Steuerung von einem `Try`\-Block oder `Catch`\-Block nicht an den entsprechenden `Finally`\-Block übergeben:  
  
-   Es befindet sich ein [End Statement](../../../visual-basic/language-reference/statements/end-statement.md) innerhalb des `Try`\-Blocks oder des `Catch`\-Blocks.  
  
-   Innerhalb des `Try`\-Blocks oder `Catch`\-Blocks wird eine <xref:System.StackOverflowException>\-Ausnahme ausgelöst.  
  
 Es ist nicht zulässig, Ausführung in einen `Finally`\-Block explizit zu übertragen.  Ausführung aus einem `Finally`\-Block zu übertragen ist, außer durch eine Ausnahme ungültig.  
  
 Wenn die `Try`\-Anweisung nicht mindestens einen `Catch`\-enthält, muss sie einen `Finally`\-Block enthalten.  
  
> [!TIP]
>  Sofern nicht bestimmte Ausnahmen abgefangen werden müssen, verhält sich die `Using`\-Anweisung wie ein `Try…Finally`\-Block und garantiert die Freigabe von Ressourcen unabhängig davon, wie die Ausführung des Blocks beendet wurde.  Dies gilt auch bei einer unbehandelten Ausnahme.  Weitere Informationen finden Sie unter [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## Ausnahmeargument  
 Das `exception`\-Argument des `Catch`\-Blocks ist eine Instanz der <xref:System.Exception>\-Klasse oder eine von der `Exception`\-Klasse abgeleitete Klasse.  Die `Exception`\-Klasseninstanz entspricht dem im `Try`\-Block aufgetretenen Fehler.  
  
 Die Eigenschaften des Objekts `Exception` helfen, die Ursache und den Ort einer Ausnahme zu bestimmen.  Die <xref:System.Exception.StackTrace%2A>\-Eigenschaft führt z. B. die aufgerufenen Methoden auf, die zur Ausnahme führten, und hilft Ihnen damit zu bestimmen, an welcher Stelle der Fehler im Code aufgetreten ist.  <xref:System.Exception.Message%2A> gibt eine Meldung zurück, in der die Ausnahme beschrieben wird.  <xref:System.Exception.HelpLink%2A> gibt einen Link auf eine zugehörige Hilfedatei zurück.  <xref:System.Exception.InnerException%2A> gibt das `Exception`\-Objekt zurück, das die aktuelle Ausnahme verursacht hat, oder es gibt `Nothing` zurück, wenn keine ursprüngliche `Exception` da ist.  
  
## Überlegungen beim Verwenden einer Try…Catch\-Anweisung  
 Verwenden Sie eine `Try…Catch`\-Anweisung nur, um das Eintreten ungewöhnlicher oder unerwarteter Programmereignisse zu signalisieren.  Dies geschieht aus den folgenden Gründen:  
  
-   Das Abfangen von Ausnahmen zur Laufzeit führt zu zusätzlichem Aufwand und ist wahrscheinlich langsamer als Vorabüberprüfungen, um Ausnahmen zu vermeiden.  
  
-   Wenn ein `Catch`\-Block nicht ordnungsgemäß behandelt wird, kann die Ausnahme für Benutzer möglicherweise nicht korrekt gemeldet werden.  
  
-   Ausnahmebehandlung macht ein Programm komplexer.  
  
 Sie brauchen nicht immer eine `Try…Catch` Anweisung, um eine Bedingung zu überprüfen, die wahrscheinlich ist.  Im folgenden Beispiel wird überprüft, ob eine Datei vorhanden ist, bevor versucht wird, sie zu öffnen.  Dies reduziert die Notwendigkeit des Abfangens einer Ausnahme, die von der Methode <xref:System.IO.File.OpenText%2A> ausgelöst wird.  
  
 [!code-vb[VbVbalrStatements#94](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Stellen Sie sicher, dass Code in `Catch`\-Blöcken ordnungsgemäß Ausnahmen für Benutzer melden können, sei es durch threadsichere Protokollierung oder entsprechende Meldungen.  Andernfalls bleiben Ausnahmen möglicherweise unbekannt.  
  
## Async\-Methoden  
 Wenn Sie eine Methode mit dem [Async](../../../visual-basic/language-reference/modifiers/async.md)\-Modifizierer markieren, können Sie den [Rechnen Sie](../../../visual-basic/language-reference/operators/await-operator.md)\-Operator in der Methode verwenden.  Eine Anweisung mit dem `Await`\-Operator enthält Ausführung der Methode an, bis die erwartete Aufgabe ausführt.  Die Aufgabe wird derzeit ausgeführte Arbeit dar.  Wenn die Aufgabe, die mit den `Await`\-Operatorenden zugeordnet ist, führen in derselben Methode fortgesetzt.  Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Eine Aufgabe, die von einer Async\-Methode zurückgegeben wird, befindet sich in einem Zustand "Faulted" und angibt, dass aufgrund eines Ausnahme abgeschlossen wurde.  Eine Aufgabe beendet möglicherweise auch in einem abgebrochenen Zustand, der `OperationCanceledException` ergibt, das aus dem Erwartungsausdruck out ausgelöst wird.  Um jeden Ausnahmetyp abzufangen, fügen Sie den `Await` Ausdruck der mit der Aufgabe in einem `Try`\-Block zugeordnet ist, und die Ausnahme im `Catch`\-Block abzufangen.  Ein Beispiel wird weiter unten in diesem Thema.  
  
 Eine Aufgabe kann in einem "Faulted" Zustand befinden, da mehrere Ausnahmen für sein Bemängeln zuständig waren.  Beispielsweise könnte die Aufgabe das Ergebnis eines Aufrufs zu <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Wenn Sie eine solche Aufgabe erwarten, dass die abgefangene Ausnahme nur eine der Ausnahmen, und Sie können nicht vorhergesagt werden, welche Ausnahme abgefangen wird.  Ein Beispiel wird weiter unten in diesem Thema.  
  
 Ein `Await` Ausdruck kann nicht innerhalb eines `Catch`\-Blocks oder `Finally`\-Blocks sein.  
  
## Iteratoren  
 Eine Iteratorfunktion oder ein `Get` Accessor führt eine benutzerdefinierte Iteration über einer Auflistung aus.  Ein Iterator verwendet eine [Yield](../../../visual-basic/language-reference/statements/yield-statement.md)\-Anweisung, um jedes Element der Auflistung separat zurückzugeben.  Sie rufen eine Iteratorfunktion an, indem Sie [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) verwenden.  
  
 Eine `Yield`\-Anweisung kann innerhalb eines Blocks `Try` sein.  Ein `Try`\-Block, der eine `Yield`\-Anweisung enthält, kann `Catch` Blöcke haben und kann einen `Finally`\-Block haben.  Siehe den "Try\-Blöcke in Visual Basic" Abschnitt von [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md) als ein Beispiel.  
  
 Eine `Yield`\-Anweisung kann nicht innerhalb eines `Catch`\-Blocks oder eines Blocks `Finally` sein.  
  
 Wenn der `For Each` Text \(außerhalb der Iteratorfunktion\) eine Ausnahme auslöst, wird ein `Catch`\-Block in der Iteratorfunktion nicht ausgeführt, aber ein `Finally`\-Block in der Iteratorfunktion wird ausgeführt.  Ein `Catch`\-Block in einer Iteratorfunktion fängt nur Ausnahmen ab, die in der Iteratorfunktion auftreten.  
  
## Teilweise vertrauenswürdige Situationen  
 In teilweise vertrauenswürdigen Kontexten, z. B. in einer Anwendung, die auf einer Netzwerkfreigabe bereitgestellt wird, fängt `Try...Catch...Finally` keine Sicherheitsausnahmen ab, die vor dem Aufrufen der den Aufruf enthaltenden Methode auftreten.  Wenn der Code im folgenden Beispiel auf einer Serverfreigabe bereitgestellt und von dort ausgeführt wird, wird der Fehler "System.Security.SecurityException: Fehler bei der Anforderung" ausgelöst. Weitere Informationen über Sicherheitsausnahmen finden Sie in der <xref:System.Security.SecurityException>\-Klasse.  
  
 [!code-vb[VbVbalrStatements#85](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 In einem solchen teilweise vertrauenswürdigen Kontext müssen Sie die `Process.Start`\-Anweisung in eine eigene `Sub` einfügen.  Der ursprüngliche Aufruf von `Sub` schlägt fehl.  Dies ermöglicht  `Try...Catch` die Ausnahme abzufangen, bevor die `Sub`, die  `Process.Start` enthält, gestartet und die Sicherheitsausnahme ausgelöst wird.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Struktur für die `Try...Catch...Finally`\-Anweisung.  
  
 [!code-vb[VbVbalrStatements#86](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## Beispiel  
 Im folgenden Beispiel löst die `CreateException`\-Methode eine `NullReferenceException` aus.  Der Code, der die Ausnahme generiert, ist nicht in einem `Try`\-Block.  Daher behandelt die `CreateException`\-Methode die Ausnahme nicht.  Die `RunSample`\-Methode behandeln die Ausnahme, da sich der Aufruf der Methode `CreateException` in einem `Try`\-Block befindet.  
  
 Das Beispiel enthält die `Catch`\-Anweisungen für verschiedene Arten von Ausnahmen, geordnet von der speziellsten zur allgemeinsten.  
  
 [!code-vb[VbVbalrStatements#91](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine `Catch When`\-Anweisung verwendet wird, um einen bedingten Ausdruck zu filtern.  Wenn der bedingte Ausdruck zu `True` ausgewertet wird, wird der Code im Block `Catch` ausgeführt.  
  
 [!code-vb[VbVbalrStatements#92](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## Beispiel  
 Im folgenden Beispiel ist eine `Try…Catch` \-Anweisung, die in einem `Try`\-Block enthalten ist.  Der innere `Catch`\-Block löst eine Ausnahme aus, bei der die `InnerException`\-Eigenschaft auf die ursprüngliche Ausnahme festgelegt ist.  Der äußere `Catch`\-Block meldet seine eigene Ausnahme und die innere Ausnahme.  
  
 [!code-vb[VbVbalrStatements#93](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Ausnahmebehandlung für asynchrone Methoden.  Wenn Sie eine Ausnahme abfangen, die auf eine asynchrone Aufgabe gilt, wird der `Await` Ausdruck in einem `Try`\-Block des Aufrufers, und die Ausnahme wird im `Catch`\-Block abgefangen.  
  
 Heben Sie die Auskommentierung `Throw New Exception` Zeile im Beispiel, um Ausnahmebehandlung zu veranschaulichen.  Die Ausnahme wird im `Catch`\-Block abgefangen, wird die `IsFaulted`\-Eigenschaft der Aufgabe zu `True` festgelegt, und die `Exception.InnerException`\-Eigenschaft der Aufgabe wird zur Ausnahme festgelegt.  
  
 Heben Sie die Auskommentierung der Zeile auf `Throw New OperationCancelledException`, um zu veranschaulichen, was geschieht, wenn Sie einen asynchronen Prozess abbrechen.  Die Ausnahme wird im `Catch`\-Block abgefangen, und die `IsCanceled`\-Eigenschaft der Aufgabe wird zu `True` festgelegt.  jedoch unter verschiedenen Bedingungen, die nicht auf dieses Beispiel anwenden, wird `IsFaulted` zu `True` festgelegt und `IsCanceled` wird zu `False` festgelegt.  
  
 [!code-vb[csAsyncExceptions#1](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Ausnahmebehandlung, in der mehrere Aufgaben mehrere Ausnahmen führen können.  Der `Try`\-Block hat den `Await` Ausdruck für die Aufgabe, die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> zurückgegeben hat.  Die Aufgabe ist abgeschlossen, wenn die drei Aufgaben, mit denen <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> angewendet wird, abgeschlossen sind.  
  
 Jede der drei Aufgabenursachen eine Ausnahme.  Der `Catch`\-Block durchläuft die Ausnahmen durch, die in der `Exception.InnerExceptions`\-Eigenschaft der Aufgabe gefunden werden, die `Task.WhenAll` zurückgegeben hat.  
  
 [!code-vb[csAsyncExceptions#3](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception>   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Empfohlene Vorgehensweisen für die Verwendung von Codeausschnitten](/visual-studio/ide/best-practices-for-using-code-snippets)   
 [Ausnahmebehandlung](../Topic/Exception%20Handling%20\(Task%20Parallel%20Library\).md)   
 [Throw Statement](../../../visual-basic/language-reference/statements/throw-statement.md)