---
title: Ausnahmebehandlung (Task Parallel Library)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e62498376d321d8ff22a53315b9d5f18a8865056
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling-task-parallel-library"></a>Ausnahmebehandlung (Task Parallel Library)
Nicht behandelte Ausnahmen, die von innerhalb einer Aufgabe ausgeführtem Benutzercode ausgelöst werden, werden zurück zum aufrufenden Thread geleitet. Hiervon ausgenommen sind bestimmte Szenarios, die weiter unten in diesem Thema beschrieben werden. Ausnahmen werden weitergegeben, wenn Sie eine der statischen verwenden oder die Instanz <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> oder <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` Methoden und Behandlung dieser schließen Sie den Aufruf in einer `try` / `catch` Anweisung. Wenn eine Aufgabe das übergeordnete Element angefügter untergeordneter Aufgaben ist oder wenn Sie auf mehrere Aufgaben warten, können mehrere Ausnahmen ausgelöst werden.  
  
 Um alle Ausnahmen zurück an den aufrufenden Thread zu leiten, schließt die Aufgabeninfrastruktur diese in eine <xref:System.AggregateException> -Instanz ein. Die <xref:System.AggregateException> -Ausnahme verfügt über eine <xref:System.AggregateException.InnerExceptions%2A> -Eigenschaft, die aufgelistet werden kann, um alle ursprünglich ausgelösten Ausnahmen zu analysieren und jede Ausnahme einzeln zu behandeln (bzw. nicht zu behandeln). Sie können auch die ursprünglichen Ausnahmen behandeln, indem die <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> Methode.  
  
 Auch wenn nur eine Ausnahme ausgelöst wurde, wird diese in eine <xref:System.AggregateException> -Ausnahme eingeschlossen, wie im nachfolgenden Beispiel veranschaulicht.  
  
 [!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
 [!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]  
  
 Unbehandeltes Ausnahmen vermeiden Sie, indem Sie nur die <xref:System.AggregateException> erfassen und die inneren Ausnahmen nicht beachten. Hiervon wird jedoch abgeraten, da dies dem Erfassen des grundlegenden <xref:System.Exception> -Typs in nicht parallelen Szenarios entspricht. Wenn Sie eine Ausnahme erfassen, ohne Maßnahmen zu deren Behandlung zu ergreifen, weist das Programm ggf. einen unbestimmten Zustand auf.  
  
 Wenn nicht aufgerufen werden soll die <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> oder <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` -Methode für den Abschluss einer Aufgabe warten, können Sie auch Abrufen der <xref:System.AggregateException> Ausnahme für die Aufgabe <xref:System.Threading.Tasks.Task.Exception%2A> -Eigenschaft wie im folgenden Beispiel gezeigt. Weitere Informationen finden Sie im Abschnitt [Beachten von Ausnahmen mit der Task.Exception-Eigenschaft](#ExceptionProp) dieses Themas.  
  
 [!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
 [!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]  
  
 Wenn Sie nicht auf eine Aufgabe warten, die eine Ausnahme weitergibt, oder auf deren <xref:System.Threading.Tasks.Task.Exception%2A> -Eigenschaft zugreifen, wird die Ausnahme entsprechend der .NET-Ausnahmerichtlinie eskaliert, sofern die Aufgabe der Garbage Collection unterliegt.  
  
 Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Aufgabe nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den folgenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen **Nur eigenen Code** unter **Extras, Optionen, Debugging, Allgemein**.  
  
## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a>Angefügte untergeordnete Aufgaben und geschachtelte AggregateExceptions  
 Wenn eine Aufgabe über eine angefügte untergeordnete Aufgabe verfügt, die eine Ausnahme auslöst, wird diese Ausnahme in <xref:System.AggregateException> eingeschlossen, bevor sie an die übergeordnete Aufgabe weitergegeben wird, die diese Ausnahme in eine eigene <xref:System.AggregateException> einschließt und sie anschließend an den aufrufenden Thread zurückgibt. In solchen Fällen die <xref:System.AggregateException.InnerExceptions%2A> Eigenschaft von der <xref:System.AggregateException> am abgefangenen Ausnahme die <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> oder <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` oder <xref:System.Threading.Tasks.Task.WaitAny%2A> oder <xref:System.Threading.Tasks.Task.WaitAll%2A> Methode enthält mindestens <xref:System.AggregateException> -Instanzen bestehen, nicht die ursprünglichen Ausnahmen, die den Fehler verursacht hat. Geschachtelt zu vermeiden, dass zum Durchlaufen <xref:System.AggregateException> Ausnahmen, die Sie verwenden die <xref:System.AggregateException.Flatten%2A> Methode, um alle Entfernen der geschachtelten <xref:System.AggregateException> Ausnahmen, damit die <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> -Eigenschaft die ursprünglichen Ausnahmen enthält. Im folgenden Beispiel werden geschachtelte <xref:System.AggregateException> -Instanzen vereinfacht und in nur einen Schleife behandelt.  
  
 [!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
 [!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]  
  
 Können Sie auch die <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> Methode, um die inneren Ausnahmen von mehreren rethrow <xref:System.AggregateException> Instanzen, die von mehreren Aufgaben in einem einzelnen ausgelöst <xref:System.AggregateException> Instanz, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
 [!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]  
  
## <a name="exceptions-from-detached-child-tasks"></a>Ausnahmen bei getrennten untergeordneten Aufgaben  
 Standardmäßig werden untergeordnete Aufgaben als getrennte Aufgaben erstellt. Von getrennten Aufgaben ausgelöste Ausnahmen müssen in der unmittelbar übergeordneten Aufgabe behandelt oder erneut ausgelöst werden. Sie werden nicht auf die gleiche Weise wie angefügte untergeordnete Aufgaben an den aufrufenden Thread zurück geleitet. Das übergeordnete Element der höchsten Ebene kann eine Ausnahme von einem getrennten untergeordneten Element manuell erneut auslösen, sodass diese in eine <xref:System.AggregateException> eingeschlossen und an den aufrufenden Thread zurück geleitet wird.  
  
 [!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
 [!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]  
  
 Selbst wenn Sie mithilfe einer Fortsetzung eine Ausnahme in einer untergeordneten Aufgabe beachten, muss die Ausnahme dennoch von der übergeordneten Aufgabe beachtet werden.  
  
## <a name="exceptions-that-indicate-cooperative-cancellation"></a>Ausnahmen mit einem kooperativen Abbruch  
 Wenn Benutzercode in einer Aufgabe auf eine Abbruchanforderung reagiert, besteht das korrekte Verfahren darin, dass eine <xref:System.OperationCanceledException> ausgelöst wird, die in dem Abbruchtoken, in dem die Anforderung übermittelt wurde, übergeben wird. Bevor die Ausnahme weitergeleitet wird, vergleicht die Aufgabeninstanz das Token in der Ausnahme mit dem Token, das beim Erstellen an sie übergeben wurde. Stimmen beide Token überein, gibt die Aufgabe eine <xref:System.Threading.Tasks.TaskCanceledException> weiter, die in die <xref:System.AggregateException>eingeschlossen ist. Diese ist zu sehen, wenn die inneren Ausnahmen analysiert werden. Wenn der aufrufende Thread jedoch nicht auf die Aufgabe wartet, wird diese Ausnahme nicht weitergegeben. Weitere Informationen finden Sie unter [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
 [!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
 [!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]  
  
## <a name="using-the-handle-method-to-filter-inner-exceptions"></a>Filtern von inneren Ausnahmen mithilfe der Handle-Methode  
 Mit der <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType>-Methode können Sie Ausnahmen filtern, die ohne weitere Logik als "behandelt" definiert werden können. Im Benutzerdelegaten, der an die <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> -Methode, können Sie den Ausnahmetyp Überprüfen seiner <xref:System.Exception.Message%2A> -Eigenschaft oder beliebige andere Informationen, mit denen Sie bestimmen, ob es keine Auswirkungen. Alle Ausnahmen, die für die der Delegat zurückgegeben `false` erneut ausgelöst werden, in einem neuen <xref:System.AggregateException> Instanz unmittelbar nach dem die <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> -Methode zurückkehrt.  
  
 Im folgende Beispiel entspricht funktional dem ersten Beispiel in diesem Thema, das jede Ausnahme überprüft die <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> Auflistung.  Dieser Ausnahmehandler ruft stattdessen die <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> datenquellenmethodenobjekt für jede Ausnahme und die einzige-Methodenobjekt Ausnahmen, die nicht `CustomException` Instanzen.  
  
 [!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
 [!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]  
  
 Folgender Ausdruck ist ein vollständiges Beispiel, verwendet der <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> -Methode zum Bereitstellen von spezielle Behandlung für eine <xref:System.UnauthorizedAccessException> Ausnahme beim Auflisten von Dateien.  
  
 [!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
 [!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]  
  
<a name="ExceptionProp"></a>   
## <a name="observing-exceptions-by-using-the-taskexception-property"></a>Beachten von Ausnahmen mit der Task.Exception-Eigenschaft  
 Wenn eine Aufgabe mit einem <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType>-Zustand abgeschlossen wird, kann die zugehörige <xref:System.Threading.Tasks.Task.Exception%2A>-Eigenschaft analysiert werden, um die spezifische Ausnahme zu ermitteln, die den Fehler verursacht hat. Eine gute Möglichkeit, die <xref:System.Threading.Tasks.Task.Exception%2A> -Eigenschaft zu beachten, ist eine Fortsetzung, die nur bei einem Fehler in der vorausgehenden Aufgabe ausgeführt wird, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
 [!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]  
  
 In einer realen Anwendung würde der Fortsetzungsdelegat ausführliche Informationen zu der Ausnahme protokollieren und möglicherweise neue Aufgaben erzeugen, um die Ausnahme zu beheben.  
  
## <a name="unobservedtaskexception-event"></a>UnobservedTaskException-Ereignis  
 In einigen Szenarien können häufig Ausnahmen ohne Auswirkungen auftreten (z. B. wenn Sie nicht vertrauenswürdige Plug-Ins hosten), und es kann schwierig sein, alle Ausnahmen manuell zu überwachen. In diesen Fällen können Sie das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType>-Ereignis behandeln. Mit der an den Handler übergebenen <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType>-Instanz kann verhindert werden, dass die nicht überwachte Ausnahme wieder an den Verbindungsthread übergeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
