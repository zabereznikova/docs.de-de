---
title: Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 4acd2094-4f46-4eff-9190-92d0d9ff47db
ms.openlocfilehash: 66979415f2951acc78dc4eb7b2aafe3c84e85397
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289940"
---
# <a name="best-practices-for-implementing-the-event-based-asynchronous-pattern"></a>Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters
Das ereignisbasierte asynchrone Muster bietet Ihnen eine effektive Methode, um asynchrones Verhalten in Klassen mit einer vertrauten Ereignis- und Delegatsemantik verfügbar zu machen. Für eine Implementierung des ereignisbasierten asynchronen Musters müssen Sie einige spezielle Verhaltensanforderungen befolgen. In den folgenden Abschnitten sind Anforderungen und Richtlinien beschrieben, die Sie bei der Implementierung einer Klasse berücksichtigen sollten, die dem ereignisbasierten asynchronen Muster folgt.  
  
 Eine Übersicht finden Sie unter [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="required-behavioral-guarantees"></a>Erforderliche Verhaltensgarantien  
 Wenn Sie das ereignisbasierte asynchrone Muster implementieren, müssen Sie eine Reihe von Garantien bereitstellen, um sicherzustellen, dass sich Ihre Klasse ordnungsgemäß verhält und die Clients Ihrer Klasse sich auf dieses Verhalten verlassen können.  
  
### <a name="completion"></a>Abschluss  
 Rufen Sie immer den Ereignishandler <em>MethodName</em>**Completed** auf, wenn ein erfolgreicher Abschluss, ein Fehler oder ein Abbruch vorliegt. Anwendungen sollten niemals auf eine Situation treffen, in der sie im Leerlauf bleiben und ein Abschluss niemals erfolgt. Eine Ausnahme dieser Regel ist, wenn der asynchrone Vorgang an sich so entwickelt wurde, dass er nie abgeschlossen wird.  
  
### <a name="completed-event-and-eventargs"></a>Abgeschlossenes Event und EventArgs  
 Wenden Sie für jede separate <em>MethodName</em>**Async**-Methode die folgenden Entwurfsanforderungen an:  
  
- Definieren Sie ein <em>MethodName</em>**Completed**-Ereignis in derselben Klasse wie die Methode.  
  
- Definieren Sie eine <xref:System.EventArgs>-Klasse und einen begleitenden Delegaten für das <em>MethodName</em>**Completed**-Ereignis, das von der <xref:System.ComponentModel.AsyncCompletedEventArgs>-Klasse abgeleitet ist. Der Standardklassenname sollte die Form <em>MethodName</em>**CompletedEventArgs** aufweisen.  
  
- Stellen Sie sicher, dass die Klasse <xref:System.EventArgs> für die Rückgabewerte der Methode <em>MethodName</em> spezifisch ist. Wenn Sie die Klasse <xref:System.EventArgs> verwenden, sollten Sie von Entwicklern niemals verlangen, das Ergebnis umzuwandeln.  
  
     Das folgende Codebeispiel zeigt jeweils eine gute und eine schlechte Implementierung dieser Entwurfsanforderung.  
  
```csharp  
// Good design  
private void Form1_MethodNameCompleted(object sender, xxxCompletedEventArgs e)
{
    DemoType result = e.Result;  
}  
  
// Bad design  
private void Form1_MethodNameCompleted(object sender, MethodNameCompletedEventArgs e)
{
    DemoType result = (DemoType)(e.Result);  
}  
```  
  
- Definieren Sie keine <xref:System.EventArgs>-Klasse zum Zurückgeben von Methoden, die `void` zurückgeben. Verwenden Sie stattdessen eine Instanz der <xref:System.ComponentModel.AsyncCompletedEventArgs>-Klasse.  
  
- Stellen Sie sicher, dass Sie immer das <em>MethodName</em>**Completed**-Ereignis auslösen. Dieses Ereignis sollte bei einem erfolgreichen Abschluss, einem Fehler oder einem Abbruch ausgelöst werden. Anwendungen sollten niemals auf eine Situation treffen, in der sie im Leerlauf bleiben und ein Abschluss niemals erfolgt.  
  
- Stellen Sie sicher, dass Sie alle Ausnahmen abfangen, die im asynchronen Vorgang auftreten und die abgefangene Ausnahme der Eigenschaft <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> zuweisen.  
  
- Wenn beim Abschließen der Aufgabe ein Fehler aufgetreten ist, sollte auf die Ergebnisse nicht zugegriffen werden können. Wenn die Eigenschaft <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> nicht `null` entspricht, stellen Sie sicher, dass der Zugriff auf eine beliebige Eigenschaft in der <xref:System.EventArgs>-Struktur eine Ausnahme auslöst. Verwenden Sie die Methode <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A>, um diese Überprüfung durchzuführen.  
  
- Modellieren Sie einen Timeout als Fehler. Wenn es zu einem Timeout kommt, lösen Sie das <em>MethodName</em>**Completed**-Ereignis aus und weisen der Eigenschaft <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> eine <xref:System.TimeoutException> zu.  
  
- Wenn Ihre Klasse mehrere gleichzeitige Aufrufe unterstützt, stellen Sie sicher, dass das <em>MethodName</em>**Completed**-Ereignis das geeignete `userSuppliedState`-Objekt enthält.  
  
- Stellen Sie sicher, dass das <em>MethodName</em>**Completed**-Ereignis im geeigneten Thread und zum geeigneten Zeitpunkt im Anwendungslebenszyklus ausgelöst wird. Weitere Informationen finden Sie im Abschnitt „Threading und Kontexte“.  
  
### <a name="simultaneously-executing-operations"></a>Gleichzeitige Ausführung von Vorgängen  
  
- Wenn Ihre Klasse mehrere gleichzeitige Aufrufe unterstützt, ermöglichen Sie dem Entwickler, jeden Aufruf separat nachzuverfolgen. Hierzu definieren Sie die <em>MethodName</em>**Async**-Überladung, die einen State-Parameter mit Objektwert oder eine Task-ID namens `userSuppliedState` akzeptiert. Dieser Parameter sollte immer der letzte Parameter in der Signatur der <em>MethodName</em>**Async**-Methode sein.  
  
- Wenn Ihre Klasse die <em>MethodName</em>**Async**-Überladung definiert, die einen State-Parameter mit Objektwert oder eine Task-ID akzeptiert, stellen Sie sicher, dass Sie die Lebensdauer des Vorgangs mit dieser Task-ID nachverfolgen und eine Rückgabe an den Abschlusshandler erfolgt. Es sind Hilfsklassen zur Unterstützung verfügbar. Weitere Informationen zur Parallelitätsverwaltung finden Sie unter [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](component-that-supports-the-event-based-asynchronous-pattern.md).  
  
- Wenn Ihre Klasse die <em>MethodName</em>**Async**-Methode ohne den State-Parameter definiert und nicht mehrere gleichzeitige Aufrufe unterstützt, stellen Sie sicher, dass jeder Versuch, <em>MethodName</em>**Async** aufzurufen, bevor der vorherige <em>MethodName</em>**Async**-Aufruf abgeschlossen wurde, eine <xref:System.InvalidOperationException> auslöst.  
  
- Im Allgemeinen sollte keine Ausnahme ausgelöst werden, wenn die <em>MethodName</em>**Async**-Methode ohne den `userSuppliedState`-Parameter mehrmals aufgerufen wird, sodass mehrere ausstehende Vorgänge vorhanden sind. Sie können eine Ausnahme auslösen, wenn Ihre Klasse diese Situation explizit nicht verarbeiten kann, aber gehen Sie davon aus, dass Entwickler diese mehrfachen, nicht unterscheidbare Rückrufe handhaben können.  
  
### <a name="accessing-results"></a>Zugreifen auf Ergebnisse  
  
- Wenn während der Ausführung des asynchronen Vorgangs ein Fehler aufgetreten ist, sollte ein Zugriff auf die Ergebnisse nicht möglich sein. Stellen Sie sicher, dass beim Zugreifen auf eine beliebige Eigenschaft in <xref:System.ComponentModel.AsyncCompletedEventArgs>, wenn <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> nicht `null` ist, die von <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> referenziert Ausnahme ausgelöst wird. Die <xref:System.ComponentModel.AsyncCompletedEventArgs>-Klasse stellt für diesen Zweck die <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A>-Methode bereit.  
  
- Stellen Sie sicher, dass bei allen Versuchen, auf das Ergebnis zuzugreifen, eine <xref:System.InvalidOperationException> ausgelöst wird, die angibt, dass der Vorgang abgebrochen wurde. Verwenden Sie die Methode <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=nameWithType>, um diese Überprüfung durchzuführen.  
  
### <a name="progress-reporting"></a>Statusberichterstellung  
  
- Unterstützen Sie die Statusberichterstellung, wenn möglich. Damit können Entwickler eine bessere Benutzerfreundlichkeit für die Anwendung bereitstellen, wenn sie Ihre Klasse verwenden.  
  
- Wenn Sie ein **ProgressChanged**- oder <em>MethodName</em>**ProgressChanged**-Ereignis implementieren, stellen Sie sicher, dass solche Ereignisse nicht für einen bestimmten asynchronen Vorgang ausgelöst werden, nachdem das <em>MethodName</em>**Completed**-Ereignis dieses Vorgangs ausgelöst wurde.  
  
- Wenn der Standardwert für <xref:System.ComponentModel.ProgressChangedEventArgs> ausgefüllt wird, stellen Sie sicher, dass <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> immer als ein Prozentsatz interpretiert werden kann. Der Prozentsatz muss nicht präzise sein, sollte aber einen Prozentsatz darstellen. Wenn die Metrik für Ihre Statusberichterstellung etwas anderes als ein Prozentsatz sein muss, leiten Sie eine Klasse von der <xref:System.ComponentModel.ProgressChangedEventArgs>-Klasse ab, und behalten Sie 0 für <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> bei. Vermeiden Sie die Verwendung einer anderen Berichtsmetrik als einen Prozentsatz.  
  
- Stellen Sie sicher, dass das `ProgressChanged`-Ereignis im geeigneten Thread und zum geeigneten Zeitpunkt im Anwendungslebenszyklus ausgelöst wird. Weitere Informationen finden Sie im Abschnitt „Threading und Kontexte“.  
  
### <a name="isbusy-implementation"></a>IsBusy-Implementierung  
  
- Machen Sie keine `IsBusy`-Eigenschaft verfügbar, wenn Ihre Klasse mehrere parallele Aufrufe unterstützt. XML-Webdienstproxies machen beispielsweise keine `IsBusy`-Eigenschaft verfügbar, weil sie mehrere parallele Aufrufe von asynchronen Methoden unterstützen.  
  
- Die `IsBusy`-Eigenschaft sollte `true` zurückgeben, nachdem die <em>MethodName</em>**Async**-Methode aufgerufen wurde und bevor das <em>MethodName</em>**Completed**-Ereignis ausgelöst wird. Andernfalls sollte `false` zurückgegeben werden. Die Komponenten <xref:System.ComponentModel.BackgroundWorker> und <xref:System.Net.WebClient> sind Beispiele für Klassen, die eine `IsBusy`-Eigenschaft verfügbar machen.  
  
### <a name="cancellation"></a>Abbruch  
  
- Unterstützen Sie einen Abbruch, wenn möglich. Damit können Entwickler eine bessere Benutzerfreundlichkeit für die Anwendung bereitstellen, wenn sie Ihre Klasse verwenden.  
  
- Im Fall eines Abbruchs legen Sie das <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A>-Flag im <xref:System.ComponentModel.AsyncCompletedEventArgs>-Objekt fest.  
  
- Stellen Sie sicher, dass bei allen Versuchen, auf das Ergebnis zuzugreifen, eine <xref:System.InvalidOperationException> ausgelöst wird, die angibt, dass der Vorgang abgebrochen wurde. Verwenden Sie die Methode <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=nameWithType>, um diese Überprüfung durchzuführen.  
  
- Stellen Sie sicher, dass die Aufrufe an eine Abbruchmethode immer erfolgreich zurückgegeben werden und niemals eine Ausnahme auslösen. Im Allgemeinen wird ein Client nicht benachrichtigt, ob ein Vorgang zu einem gegebenen Zeitpunkt wirklich abbrechbar ist und ob ein zuvor ausgegebener Abbruch erfolgreich war. Die Anwendung wird jedoch immer benachrichtigt, wenn ein Abbruch erfolgreich war, da die Anwendung am Abschlussstatus teilnimmt.  
  
- Lösen Sie das <em>MethodName</em>**Completed**-Ereignis aus, wenn der Vorgang abgebrochen wird.  
  
### <a name="errors-and-exceptions"></a>Fehler und Ausnahmen  
  
- Fangen Sie alle Ausnahmen ab, die im asynchronen Vorgang auftreten, und legen Sie den Wert der <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>-Eigenschaft auf diese Ausnahme fest.  
  
### <a name="threading-and-contexts"></a>Threading und Kontexte  
 Für die korrekte Funktionsweise Ihrer Klasse ist es wichtig, dass die Ereignishandler des Clients im richtigen Thread oder Kontext des entsprechenden Anwendungsmodells aufgerufen werden, einschließlich ASP.NET- und Windows Forms-Anwendungen. Es werden zwei wichtige Hilfsklassen bereitgestellt, um sicherzustellen, dass sich Ihre asynchrone Klasse unter jedem Anwendungsmodell korrekt verhält: <xref:System.ComponentModel.AsyncOperation> und <xref:System.ComponentModel.AsyncOperationManager>.  
  
 <xref:System.ComponentModel.AsyncOperationManager> stellt eine Methode bereit, <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>, die <xref:System.ComponentModel.AsyncOperation> zurückgibt. Ihre <em>MethodName</em>**Async**-Methode ruft <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> auf, und Ihre Klasse verwendet den zurückgegebenen <xref:System.ComponentModel.AsyncOperation>, um die Lebensdauer des asynchronen Tasks nachzuverfolgen.  
  
 Für einen Statusbericht, inkrementelle Ergebnisse und Abschluss auf dem Client rufen Sie die Methoden <xref:System.ComponentModel.AsyncOperation.Post%2A> und <xref:System.ComponentModel.AsyncOperation.OperationCompleted%2A> in <xref:System.ComponentModel.AsyncOperation> auf. <xref:System.ComponentModel.AsyncOperation> ist für das Marshalling von Aufrufen an die Ereignishandler des Clients an den richtigen Thread oder Kontext verantwortlich.  
  
> [!NOTE]
> Sie können diese Regeln umgehen, wenn Sie explizit gegen die Richtlinie des Anwendungsmodell vorgehen möchten, aber dennoch von den anderen Vorteilen der Verwendung des ereignisbasierten asynchronen Musters profitieren. Möglicherweise möchten Sie zum Beispiel, dass eine in Windows Forms betriebene Klasse eine Freethread-Klasse ist. Sie können eine Freethread-Klasse erstellen, solange Entwickler die implizierten Einschränkungen verstehen. Konsolenanwendungen führen keine Synchronisierung von <xref:System.ComponentModel.AsyncOperation.Post%2A>-Aufrufen durch. Das kann dazu führen, dass `ProgressChanged`-Ereignisse nicht in der richtigen Reihenfolge ausgelöst werden. Wenn Sie eine serialisierte Ausführung von <xref:System.ComponentModel.AsyncOperation.Post%2A>-Aufrufen wünschen, implementieren und installieren Sie eine <xref:System.Threading.SynchronizationContext?displayProperty=nameWithType>-Klasse.  
  
 Weitere Informationen zur Verwendung von <xref:System.ComponentModel.AsyncOperation> und <xref:System.ComponentModel.AsyncOperationManager> für Ihre asynchronen Vorgänge finden Sie unter [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="guidelines"></a>Richtlinien  
  
- Idealerweise sollte jeder Methodenaufruf unabhängig von anderen erfolgen. Sie sollten vermeiden, Aufrufe mit freigegebenen Ressourcen zu koppeln. Wenn Ressourcen unter Aufrufen freigegeben werden sollen, müssen einen richtigen Synchronisierungsmechanismus in Ihrer Implementierung bereitstellen.  
  
- Entwürfe, bei denen der Client eine Synchronisierung implementieren muss, sind nicht empfehlenswert. Wenn Sie beispielsweise eine asynchrone Methode haben, die ein globales statisches Objekt als Parameter erhält, könnten mehrere parallele Aufrufe einer solchen Methode zur Datenbeschädigungen oder Deadlocks führen.  
  
- Wenn Sie eine Methode mit der Überladung mit mehreren Aufrufen (`userState` in der Signatur) implementieren, muss Ihre Klasse eine Sammlung von Benutzerstatus oder Aufgaben-IDs und ihre entsprechenden ausstehenden Vorgänge verwalten. Diese Auflistung sollte mit `lock`-Regionen geschützt werden, da die verschiedenen Aufrufe `userState`-Objekte in der Auflistung hinzufügen und daraus entfernen.  
  
- Ziehen Sie die erneute Verwendung von `CompletedEventArgs`-Klassen in Betracht, wenn diese machbar und angemessen ist. In diesem Fall ist die Benennung nicht konsistent mit dem Methodennamen, da ein gegebener Delegat und <xref:System.EventArgs>-Typ nicht an eine einzige Methode gebunden sind. Dennoch ist es niemals akzeptabel, Entwickler zu zwingen, den von einer Eigenschaft in <xref:System.EventArgs> abgerufenen Wert umzuwandeln.  
  
- Wenn Sie eine Klasse entwickeln, die von <xref:System.ComponentModel.Component> abgeleitet ist, implementieren und installieren Sie nicht Ihre eigene <xref:System.Threading.SynchronizationContext>-Klasse. Die verwendete <xref:System.Threading.SynchronizationContext> werden von Anwendungsmodellen, nicht von Komponenten gesteuert.  
  
- Wenn Sie Multithreading irgendeiner Art verwenden, setzen Sie sich potenziell ernsthaften und komplexen Fehlern aus. Bevor Sie eine Lösung implementieren, in der Multithreading verwendet wird, sollten Sie den Artikel [Verwaltetes Threading – bewährte Methoden](../threading/managed-threading-best-practices.md) lesen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.BackgroundWorker>
- [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](implementing-the-event-based-asynchronous-pattern.md)
- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](event-based-asynchronous-pattern-eap.md)
- [Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)
- [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](component-that-supports-the-event-based-asynchronous-pattern.md)
