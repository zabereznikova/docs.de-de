---
title: Versuchen Sie es... Catch... Finally-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
dev_langs:
- VB
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement, Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement
- When keyword
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 379359e3a338746ccd440dbe1ad58c483e562dbe
ms.lasthandoff: 03/13/2017

---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally-Anweisung (Visual Basic)
Bietet eine Möglichkeit, einige oder alle möglichen Fehler zu behandeln, die in einem bestimmten Codeblock auftreten können, während noch Code ausgeführt.  
  
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
|`tryStatements`|Optional. Anweisung(en), in dem ein Fehler auftreten kann. Kann eine Verbundanweisung sein.|  
|`Catch`|Optional. Mehrere `Catch` Blöcke zulässig. Wenn eine Ausnahme auftritt, bei der Verarbeitung der `Try` blockieren, jede `Catch` -Anweisung überprüft wird, in Textform Reihenfolge zu bestimmen, ob sie die Ausnahme, wobei behandelt `exception` , die die ausgelöste Ausnahme darstellt.|  
|`exception`|Optional. Ein beliebiger Variablenname. Der Anfangswert von `exception` ist der Wert des ausgelösten Fehlers. Mit verwendet `Catch` an der Fehler abgefangen. Wenn nicht angegeben, die `Catch` Anweisung fängt jede Ausnahme.|  
|`type`|Optional. Gibt den Typ der Klasse Filter. Wenn der Wert der `exception` des angegebenen Typs ist `type` oder eines abgeleiteten Typs, der Bezeichner an das Ausnahmeobjekt gebunden wird.|  
|`When`|Optional. Ein `Catch` -Anweisung mit einem `When` -Klausel fängt Ausnahmen nur, wenn `expression` ergibt `True`. Ein `When` -Klausel wird nur angewendet, nachdem der Typ der Ausnahme überprüft und `expression` bezieht sich möglicherweise auf den Bezeichner darstellt.|  
|`expression`|Optional. Muss implizit in `Boolean`. Ein beliebiger Ausdruck, der einen allgemeinen Filter beschreibt. In der Regel verwendet zum Filtern nach Fehlernummern. Mit verwendet `When` -Schlüsselwort verwenden, um die Angabe der Umstände, unter denen der Fehler abgefangen wird.|  
|`catchStatements`|Optional. Anweisung(en) zur Behandlung von Fehlern, die auftreten, in der zugeordneten `Try` Block. Kann eine Verbundanweisung sein.|  
|`Exit Try`|Optional. Schlüsselwort, das von unterbricht die `Try...Catch...Finally` Struktur. Die Ausführung wird fortgesetzt, durch den Code direkt nach der `End Try` Anweisung. Die `Finally` -Anweisung wird weiterhin ausgeführt werden. Nicht zulässig `Finally` blockiert.|  
|`Finally`|Optional. Ein `Finally` -Block wird immer ausgeführt, wenn die Ausführung eines beliebigen Teils der `Try...Catch` Anweisung.|  
|`finallyStatements`|Optional. Anweisung(en), die ausgeführt werden, nachdem sämtlicher Fehler aufgetreten ist.|  
|`End Try`|Beendet die `Try...Catch...Finally` Struktur.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie erwarten, dass eine bestimmte Ausnahme während eines bestimmten Codeabschnitts auftreten kann, fügen Sie den Code in eine `Try` blockieren, und verwenden eine `Catch` Block behalten die Kontrolle und die Ausnahme behandeln, wenn diese ausgeführt wird.  
  
 Ein `Try…Catch` -Anweisung besteht aus einem `Try` Block gefolgt von einer oder mehreren `Catch` Klauseln, die Handler für verschiedene Ausnahmen angeben. Wenn eine Ausnahme ausgelöst wird, einem `Try` Block [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sucht nach der `Catch` -Anweisung, die die Ausnahme behandelt. Wenn ein entsprechender `Catch` Anweisung nicht gefunden wird, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] überprüft die Methode, die die aktuelle Methode ist und so weiter oben in der Aufrufliste aufgerufen. Wenn kein `Catch` Block gefunden wird, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wird dem Benutzer eine nicht behandelte Ausnahme angezeigt, und beendet die Ausführung des Programms.  
  
 Sie können mehrere `Catch` -Anweisung in eine `Try…Catch` Anweisung. Wenn Sie die Reihenfolge der dazu die `Catch` Klauseln ist wichtig, da sie in der Reihenfolge untersucht werden. Fangen Sie spezifischere Ausnahmen vor den weniger spezifischen ab.  
  
 Die folgenden `Catch` Anweisung Zustände sind allgemeinsten und fängt alle Ausnahmen, die von der <xref:System.Exception>Klasse</xref:System.Exception> abgeleitet werden Verwenden eines Variationen in der Regel wie in den letzten `Catch` -Block in der `Try...Catch...Finally` -Struktur verwenden, nachdem Sie alle gewünschten spezifischen Ausnahmen abfangen. Kontrollfluss erreichen nie einen `Catch` -Block, der entweder der Variationen folgt.  
  
-   Die `type` ist `Exception`, beispielsweise:`Catch ex As Exception`  
  
-   Die Anweisung hat keine `exception` Variable, Beispiel:`Catch`  
  
 Wenn ein `Try…Catch…Finally` -Anweisung in einer anderen geschachtelt ist `Try` Block [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] zuerst überprüft jede `Catch` -Anweisung in der innersten `Try` Block. Wenn keine übereinstimmende `Catch` Anweisung gefunden wird, wird die Suche wird fortgesetzt, um die `Catch` -Anweisungen des äußeren `Try…Catch…Finally` Block.  
  
 Lokale Variablen aus einer `Try` Block sind nicht verfügbar in eine `Catch` blockiert werden, da sie eigene Blöcke handelt. Wenn Sie eine Variable in mehreren Blöcken verwenden möchten, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.  
  
> [!TIP]
>  Die `Try…Catch…Finally` -Anweisung ist als IntelliSense-Codeausschnitt verfügbar. Erweitern Sie im Codeausschnitt-Manager, **Codemuster - If, For Each, Try Catch, Eigenschaft usw.**, und klicken Sie dann **Fehlerbehandlung (Ausnahmen)**. Weitere Informationen finden Sie unter [Codeausschnitte](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="finally-block"></a>Finally-Block  
 Wenn Sie eine oder mehrere Anweisungen, die ausgeführt werden muss, bevor Sie verlassen haben die `Try` verwenden eine `Finally` Block. Die Steuerung an die `Finally` blockieren, kurz bevor sie übergeben die `Try…Catch` Struktur. Dies gilt auch beim Auftreten einer Ausnahme an einer beliebigen Stelle innerhalb der `Try` Struktur.  
  
 Ein `Finally` -Block ist nützlich zum Ausführen von Code, ausführen muss, auch wenn eine Ausnahme aufgetreten ist. Erhält die Kontrolle der `Finally` Block unabhängig davon, wie der `Try...Catch` -Block beendet wird.  
  
 Der Code in einer `Finally` -Block ausgeführt, auch wenn im Code auftritt einer `Return` -Anweisung in einer `Try` oder `Catch` Block. Steuerelement übergibt nicht aus einer `Try` oder `Catch` -block, um das entsprechende `Finally` blockieren in den folgenden Fällen:  
  
-   Ein [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md) gefunden wird in der `Try` oder `Catch` Block.  
  
-   Ein <xref:System.StackOverflowException>wird ausgelöst, der `Try` oder `Catch` Block.</xref:System.StackOverflowException>  
  
 Es ist nicht zulässig, die Ausführung in explizit übertragen ein `Finally` Block. Übertragen die Ausführung von einem `Finally` Block ist nicht gültig, außer durch eine Ausnahme.  
  
 Wenn ein `Try` Anweisung enthält keine mindestens `Catch` Block muss enthalten eine `Finally` Block.  
  
> [!TIP]
>  Wenn Sie keinen bestimmte Ausnahmen abfangen, die `Using` Anweisung verhält sich wie eine `Try…Finally` Block und garantiert die Freigabe von Ressourcen unabhängig davon, wie Sie den Block beenden. Dies gilt auch dann eine nicht behandelte Ausnahme. Weitere Informationen finden Sie unter [Using-Anweisung](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="exception-argument"></a>Ausnahme-Argument  
 Die `Catch` Block `exception` Argument ist eine Instanz von der <xref:System.Exception>Klasse oder eine Klasse, die von abgeleitet ist die `Exception` Klasse</xref:System.Exception> Die `Exception` -Klasseninstanz entspricht der aufgetretenen Fehler der `Try` Block.  
  
 Die Eigenschaften der `Exception` -Objekt Hilfe, um die Ursache und Ort einer Ausnahme zu identifizieren. Zum Beispiel die <xref:System.Exception.StackTrace%2A>-Eigenschaft führt die aufgerufenen Methoden, die auf die Ausnahme, führten des Fehlers im Code führte.</xref:System.Exception.StackTrace%2A> <xref:System.Exception.Message%2A>Gibt eine Meldung, die die Ausnahme beschreibt.</xref:System.Exception.Message%2A> <xref:System.Exception.HelpLink%2A>Gibt einen Link zu einer zugehörigen Hilfedatei zurück.</xref:System.Exception.HelpLink%2A> <xref:System.Exception.InnerException%2A>Gibt die `Exception` -Objekt, das die aktuelle Ausnahme oder verursacht gibt `Nothing` Wenn keine ursprüngliche `Exception`.</xref:System.Exception.InnerException%2A>  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Aspekte der Verwendung ein Try... Catch-Anweisung  
 Verwenden einer `Try…Catch` Anweisung nur für das Programm ungewöhnliche oder unerwartete Ereignisse auftreten signalisiert. Folgende: Gründe  
  
-   Abfangen von Ausnahmen zur Laufzeit führt zu zusätzlichem Aufwand und ist wahrscheinlich langsamer als Vorabüberprüfungen, um Ausnahmen zu vermeiden.  
  
-   Wenn ein `Catch` Block nicht ordnungsgemäß behandelt wird und die Ausnahme möglicherweise nicht korrekt für Benutzer gemeldet werden.  
  
-   Ausnahmebehandlung macht ein Programm komplexer.  
  
 Sie brauchen nicht immer eine `Try…Catch` Anweisung für eine Bedingung überprüft, die zu rechnen ist. Im folgenden Beispiel wird überprüft, ob eine Datei vorhanden ist, bevor Sie versuchen, ihn zu öffnen. Dies reduziert die Notwendigkeit für das Abfangen einer Ausnahme von der <xref:System.IO.File.OpenText%2A>-Methode.</xref:System.IO.File.OpenText%2A>  
  
 [!code-vb[VbVbalrStatements&#94;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Vergewissern Sie sich, Code in `Catch` Blöcke Ausnahmen für Benutzer über threadsichere oder die entsprechenden Nachrichten können ordnungsgemäß gemeldet werden. Andernfalls bleiben Ausnahmen möglicherweise unbekannt.  
  
## <a name="async-methods"></a>Asynchrone Methoden  
 Markieren Sie eine Methode mit der [Async](../../../visual-basic/language-reference/modifiers/async.md) -Modifizierer können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) -Operator in der Methode. Eine Anweisung mit der `Await` -Operator hält die Ausführung der Methode, bis die Aufgabe abgeschlossen ist. Die Aufgabe stellt derzeit ausgeführte Arbeit dar. Wenn die Aufgabe, die zugeordnet ist die `Await` Operator abgeschlossen ist, setzt der Ausführung in derselben Methode. Weitere Informationen finden Sie unter [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 Ein von einer asynchronen Methode zurückgegebene Task am Ende womöglich einen Fehlerzustand, der angibt, dass es aufgrund einer nicht behandelten Ausnahme abgeschlossen. Eine Aufgabe kann auch beenden, in einem abgebrochenen Zustand, wodurch eine `OperationCanceledException` ausgelöst wird, aus der Await-Ausdruck. Um entweder Typ von Ausnahme abfangen möchten, setzen Sie die `Await` -Ausdruck, der die Aufgabe zugeordnet ist ein `Try` blockieren, und die Ausnahme in der `Catch` Block. Ein Beispiel ist unten in diesem Thema bereitgestellt.  
  
 Eine Aufgabe kann in einem fehlerhaften Zustand sein, da mehrere Ausnahmen für die fehlgeschlagene verantwortlich waren. Der Task kann z. B. das Ergebnis eines Aufrufs von <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> werden. Wenn Sie eine solche Aufgabe warten, die abgefangene Ausnahme ist nur eine der Ausnahmen, und Sie nicht vorhersagen, welche Ausnahme abgefangen wird. Ein Beispiel ist unten in diesem Thema bereitgestellt.  
  
 Ein `Await` Ausdruck kann nicht innerhalb einer `Catch` Block oder `Finally` Block.  
  
## <a name="iterators"></a>Iteratoren  
 Ein Iteratorfunktion oder `Get` Accessor führt eine benutzerdefinierte Iteration durch eine Auflistung. Ein Iterator verwendet eine [ergeben](../../../visual-basic/language-reference/statements/yield-statement.md) -Anweisung jedes Element der Auflistung zu einem Zeitpunkt zurückgegeben. Rufen Sie eine Iteratorfunktion mit einem [für jeden... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Ein `Yield` Anweisung kann innerhalb einer `Try` Block. Ein `Try` Block mit einer `Yield` -Anweisung kann verfügen `Catch` blockiert, und kann einen `Finally` Block. Finden Sie im Abschnitt "versuchen Blöcke in Visual Basic" [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) ein Beispiel.  
  
 Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.  
  
 Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, ein `Catch` -Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird. Ein `Catch` Block innerhalb einer Iteratorfunktion nur Ausnahmen abzufangen, die innerhalb der Iteratorfunktion auftreten.  
  
## <a name="partial-trust-situations"></a>Teilweise vertrauenswürdigen Umgebungen  
 In teilweise vertrauenswürdigen Situationen, z. B. eine Anwendung, die auf einer Netzwerkfreigabe bereitgestellt `Try...Catch...Finally` fängt keine aufgetretenen Sicherheitsausnahmen angezeigt werden, bevor die Methode, die den Aufruf enthält aufgerufen wird. Im folgende Beispiel, wenn Sie es auf einer Serverfreigabe und dort ablegen, wird der Fehler "System.Security.SecurityException: Fehler bei der Anforderung." Weitere Informationen über Sicherheitsausnahmen finden Sie in der <xref:System.Security.SecurityException>Klasse.</xref:System.Security.SecurityException>  
  
 [!code-vb[VbVbalrStatements&#85;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 In einem teilweise vertrauenswürdigen solchen, muss die `Process.Start` Anweisung in einem separaten `Sub`. Der erste Aufruf der `Sub` schlägt fehl. Auf diese Weise können `Try...Catch` abzufangen, bevor die `Sub` , enthält `Process.Start` wird gestartet und die Sicherheitsausnahme erzeugt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Struktur der `Try...Catch...Finally` Anweisung.  
  
 [!code-vb[VbVbalrStatements&#86;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `CreateException` -Methode löst eine `NullReferenceException`. Der Code, der die Ausnahme generiert befindet sich nicht in einem `Try` Block. Aus diesem Grund die `CreateException` Methode die Ausnahme nicht behandelt. Die `RunSample` Methode die Ausnahme behandeln, da der Aufruf der `CreateException` -Methode wird in einer `Try` Block.  
  
 Das Beispiel enthält `Catch` Anweisungen für verschiedene Arten von Ausnahmen, geordnet von der spezifischsten bis zur die allgemeinste.  
  
 [!code-vb[VbVbalrStatements&#91;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine `Catch When` Anweisung, um nach einem bedingten Ausdruck zu filtern. Wenn der bedingte Ausdruck ergibt `True`, den Code in der `Catch` -Block ausgeführt.  
  
 [!code-vb[VbVbalrStatements&#92;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ist ein `Try…Catch` -Anweisung, die in enthalten ist ein `Try` Block. Die innere `Catch` Block löst eine Ausnahme aus, dessen `InnerException` -Eigenschaft auf die ursprüngliche Ausnahme festgelegt. Die äußere `Catch` -Block meldet seine eigene Ausnahme und die innere Ausnahme.  
  
 [!code-vb[VbVbalrStatements&#93;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Ausnahmebehandlung für asynchrone Methoden veranschaulicht. Eine Ausnahme abfangen, die für eine asynchrone Aufgabe, gilt die `Await` Ausdruck wird einer `Try` in Block der Aufrufer und die Ausnahme abgefangen der `Catch` Block.  
  
 Heben Sie die Auskommentierung der Zeile `Throw New Exception` im Beispiel auf, um die Ausnahmebehandlung zu veranschaulichen. Wird die Ausnahme der `Catch` zu blockieren, der Aufgabe `IsFaulted` -Eigenschaft auf festgelegt ist `True`, und die Aufgabe `Exception.InnerException` Eigenschaft auf die Ausnahme festgelegt ist.  
  
 Kommentieren Sie die `Throw New OperationCancelledException` Zeile zeigen, was passiert, wenn Sie einen asynchronen Prozess abbrechen. Wird die Ausnahme der `Catch` -Block ausgeführt, und der Aufgabe `IsCanceled` -Eigenschaft auf festgelegt ist `True`. Jedoch unter bestimmten Umständen, die für dieses Beispiel gelten nicht `IsFaulted` Wert `True` und `IsCanceled` Wert `False`.  
  
 [!code-vb[CsAsyncExceptions&#1;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Behandlung von Ausnahmen in Fällen, in denen mehrere Aufgaben zu mehreren Ausnahmen führen können. Die `Try` -Block ist die `Await` Ausdruck für die Aufgabe, die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>zurückgegeben.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Die Aufgabe ist abgeschlossen, wenn die drei, auf die Aufgaben <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>angewendet wird abgeschlossen sind.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>  
  
 Jede der drei Aufgaben löst eine Ausnahme aus. Die `Catch` Block durchläuft die Ausnahmen, die in enthalten sind die `Exception.InnerExceptions` -Eigenschaft der Aufgabe, die `Task.WhenAll` zurückgegeben.  
  
 [!code-vb[CsAsyncExceptions&3;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.Err%2A></xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception></xref:System.Exception>   
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Bewährte Methoden für die Verwendung von Codeausschnitten](https://docs.microsoft.com/visualstudio/ide/best-practices-for-using-code-snippets)   
 [Behandlung von Ausnahmen](https://msdn.microsoft.com/library/dd997415)   
 [Throw-Anweisung](../../../visual-basic/language-reference/statements/throw-statement.md)
