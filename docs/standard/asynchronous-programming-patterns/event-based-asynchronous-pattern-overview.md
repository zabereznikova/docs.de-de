---
title: Übersicht über ereignisbasierte asynchrone Muster
description: In diesem Artikel werden ereignisbasierte asynchrone Muster in .NET erläutert, die die Vorteile von Multithreadanwendungen verfügbar machen und gewisse Designschwierigkeiten beseitigen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 792aa8da-918b-458e-b154-9836b97735f3
ms.openlocfilehash: 18fbdb29e5a1fb02601dea00964538144c07122c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768858"
---
# <a name="event-based-asynchronous-pattern-overview"></a>Übersicht über ereignisbasierte asynchrone Muster
Für Anwendungen, die viele Aufgaben gleichzeitig durchführen, aber weiterhin auf Benutzerinteraktionen reagieren, ist oft ein Entwurf erforderlich, der mehrere Threads verwendet. Der <xref:System.Threading>-Namespace bietet alle erforderlichen Tools für die Erstellung von leistungsstarken Multithreadanwendungen, aber für eine effektive Verwendung dieser Tools ist eine umfassende Erfahrung mit der Multithread-Softwareentwicklung erforderlich. Für relativ einfache Multithreadanwendungen bietet die <xref:System.ComponentModel.BackgroundWorker>-Komponente eine unkomplizierte Lösung. Für komplexere asynchrone Anwendungen sollten Sie die Implementierung einer Klasse in Betracht ziehen, die den ereignisbasierten asynchronen Muster entspricht.  
  
 Das ereignisbasierte asynchrone Muster stellt die Vorteile von Multithreadanwendungen zur Verfügung und blendet gleichzeitig viele komplexe Aspekte von Multithreadentwürfen aus. Die Verwendung einer Klasse, die dieses Muster unterstützt, ermöglicht Folgendes:  
  
- Führen Sie zeitaufwendige Aufgaben wie Downloads und Datenbankvorgänge „in Hintergrund“ aus, ohne Ihre Anwendung zu unterbrechen.  
  
- Führen Sie mehrere Vorgänge gleichzeitig aus, und erhalten Sie Benachrichtigungen, wenn jede abgeschlossen ist.  
  
- Warten Sie, bis Ressourcen verfügbar werden, ohne Ihre Anwendung anzuhalten („blockieren“).  
  
- Kommunizieren Sie mit ausstehenden asynchronen Vorgängen über das vertraute Modell mit Ereignissen und Delegaten. Weitere Informationen zum Verwenden von Ereignishandlern und Delegaten finden Sie unter [Ereignisse](../events/index.md).  
  
 Eine Klasse, die das ereignisbasierte asynchrone Muster unterstützt, verfügt über mindesten eine Methode namens _MethodName_**Async**. Diese Methoden spiegeln möglicherweise synchrone Versionen wider, die denselben Vorgang im aktuellen Thread durchführen. Die Klasse kann darüber hinaus auch über ein _MethodName_**Completed**-Ereignis und eine _MethodName_**AsyncCancel**-Methode (kurz **CancelAsync**) verfügen.  
  
 <xref:System.Windows.Forms.PictureBox> ist eine typische Komponente, die das ereignisbasierte asynchrone Muster unterstützt. Sie können ein Image synchron herunterladen, indem Sie seine <xref:System.Windows.Forms.PictureBox.Load%2A>-Methode aufrufen, aber wenn das Image groß oder die Netzwerkverbindung langsam ist, reagiert Ihre Anwendung nicht mehr, bis der Downloadvorgang abgeschlossen ist und der Aufruf an <xref:System.Windows.Forms.PictureBox.Load%2A> zurückgegeben wird.  
  
 Wenn Sie möchten, dass Ihre Anwendung während des Ladens des Images weiter ausgeführt wird, können Sie die <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>-Methode aufrufen und das <xref:System.Windows.Forms.PictureBox.LoadCompleted>-Ereignis verarbeiten, wie Sie jedes andere Ereignis verarbeiten würden. Wenn Sie die <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>-Methode aufrufen, wird Ihre Anwendung weiterhin ausgeführt, während der Download in einem separaten Thread („im Hintergrund“) fortgesetzt wird. Ihr Ereignishandler wird aufgerufen, wenn der Ladevorgang für das Image abgeschlossen ist, und Ihr Ereignishandler kann den Parameter <xref:System.ComponentModel.AsyncCompletedEventArgs> untersuchen, um festzustellen, ob der Download erfolgreich abgeschlossen wurde.  
  
 Das ereignisbasierte asynchrone Muster erfordert, dass ein asynchroner Vorgang abgebrochen werden kann, und das <xref:System.Windows.Forms.PictureBox>-Steuerelement unterstützt diese Anforderung mit der <xref:System.Windows.Forms.PictureBox.CancelAsync%2A>-Methode. Bei Aufrufen von <xref:System.Windows.Forms.PictureBox.CancelAsync%2A> wird eine Anforderung übermittelt, um den ausstehenden Download zu beenden. Wenn die Aufgabe abgebrochen wird, wird das <xref:System.Windows.Forms.PictureBox.LoadCompleted>-Ereignis ausgelöst.  
  
> [!CAUTION]
> Es ist möglich, dass der Download gerade in dem Moment abgeschlossen wird, in dem die <xref:System.Windows.Forms.PictureBox.CancelAsync%2A>-Anforderung erfolgt, sodass <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A> die Anforderung zum Abbrechen möglicherweise nicht widerspiegelt. Dies wird als *Racebedingung* bezeichnet und ist ein typisches Problem bei der Multithreadprogrammierung. Weitere Informationen zu Problemen bei der Multithreadprogrammierung finden Sie unter [Empfohlene Vorgehensweise für das verwaltete Threading](../threading/managed-threading-best-practices.md).  
  
## <a name="characteristics-of-the-event-based-asynchronous-pattern"></a>Eigenschaften des ereignisbasierten asynchronen Musters  
 Das ereignisbasierte asynchrone Muster kann je nach Komplexität der von einer bestimmten Klasse unterstützten Vorgänge mehrere Formen annehmen. Die einfachsten Klassen verfügen möglicherweise über eine einzige _MethodName_**Async**-Methode und ein entsprechendes _MethodName_**Completed**-Ereignis. Komplexere Klassen verfügen möglicherweise über mehrere _MethodName_**Async**-Methoden mit jeweils einem entsprechenden _MethodName_**Completed**-Ereignis sowie synchronen Versionen dieser Methoden. Klassen können optional das Abbrechen, die Statusberichterstellung und inkrementelle Ergebnisse für jede asynchrone Methode unterstützen.  
  
 Eine asynchrone Methode kann außerdem mehrere ausstehende Aufrufe (mehrere parallele Aufrufe) unterstützen, sodass Ihr Code diese beliebig oft aufrufen kann, bevor andere ausstehende Vorgänge abgeschlossen werden. Für eine ordnungsgemäße Handhabung dieser Situation muss Ihre Anwendung möglicherweise den Abschluss jedes Vorgangs nachverfolgen.  
  
### <a name="examples-of-the-event-based-asynchronous-pattern"></a>Beispiele für das ereignisbasierte asynchrone Muster  
 Die Komponenten <xref:System.Media.SoundPlayer> und <xref:System.Windows.Forms.PictureBox> stellen einfache Implementierungen des ereignisbasierten asynchronen Musters dar. Die Komponenten <xref:System.Net.WebClient> und <xref:System.ComponentModel.BackgroundWorker> stellen komplexere Implementierungen des ereignisbasierten asynchronen Musters dar.  
  
 Im Folgenden sehen Sie ein Beispiel für eine Klassendeklaration, die dem Muster entspricht:  
  
```vb  
Public Class AsyncExample  
    ' Synchronous methods.  
    Public Function Method1(ByVal param As String) As Integer
    Public Sub Method2(ByVal param As Double)
  
    ' Asynchronous methods.  
    Overloads Public Sub Method1Async(ByVal param As String)
    Overloads Public Sub Method1Async(ByVal param As String, ByVal userState As Object)
    Public Event Method1Completed As Method1CompletedEventHandler  
  
    Overloads Public Sub Method2Async(ByVal param As Double)
    Overloads Public Sub Method2Async(ByVal param As Double, ByVal userState As Object)
    Public Event Method2Completed As Method2CompletedEventHandler  
  
    Public Sub CancelAsync(ByVal userState As Object)
  
    Public ReadOnly Property IsBusy () As Boolean  
  
    ' Class implementation not shown.  
End Class  
```  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 Die fiktive `AsyncExample`-Klasse verfügt über zwei Methoden, die beide synchrone und asynchrone Aufrufe unterstützen. Die synchronen Überladungen verhalten sich wie jeder beliebige Methodenaufruf und führen den Vorgang im aufrufenden Thread aus. Wenn der Vorgang zeitaufwendig ist, kommt es möglicherweise zu einer spürbaren Verzögerung, bis der Aufruf zurückgegeben wird. Die asynchronen Überlastungen starten den Vorgang in einem anderen Thread und geben dann sofort zurück, sodass der aufrufende Thread fortgesetzt werden kann, während der Vorgang „im Hintergrund“ ausgeführt wird.  
  
### <a name="asynchronous-method-overloads"></a>Asynchrone Methodenüberladungen  
 Es gibt potenziell zwei Überladungen für die asynchronen Vorgänge: einzelner Aufruf und mehrere Aufrufe. Sie können die zwei Formen anhand ihrer Methodensignaturen unterscheiden: Die Form mit mehreren Aufrufen hat einen zusätzlichen Parameter namens `userState`. Diese Form ermöglicht Ihrem Code, `Method1Async(string param, object userState)` mehrmals aufzurufen, ohne darauf warten zu müssen, dass ausstehende asynchrone Vorgänge abgeschlossen werden. Wenn Sie andererseits versuchen, `Method1Async(string param)` aufzurufen, bevor ein vorheriger Aufruf abgeschlossen ist, löst die Methode eine <xref:System.InvalidOperationException> aus.  
  
 Der Parameter `userState` für die Überladungen mit mehreren Aufrufen ermöglicht Ihnen, zwischen asynchronen Vorgängen zu unterscheiden. Sie stellen einen eindeutigen Wert (z.B. eine GUID oder einen Hashcode) für jeden Aufruf an `Method1Async(string param, object userState)` bereit. Wenn jeder Vorgang abgeschlossen ist, kann Ihr Ereignishandler bestimmen, welche Instanz des Vorgangs das Abschlussereignis ausgelöst hat.  
  
### <a name="tracking-pending-operations"></a>Nachverfolgen ausstehender Vorgänge  
 Wenn Sie die Überladungen mit mehreren Aufrufen verwenden, muss Ihr Code die `userState`-Objekte (Aufgaben-IDs) für ausstehende Aufgaben nachverfolgen. Für jeden Aufruf an `Method1Async(string param, object userState)` generieren Sie in der Regel ein neues eindeutiges `userState`-Objekt und fügen es einer Auflistung hinzu. Wenn die diesem `userState`-Objekt entsprechende Aufgabe das Abschlussereignis auslöst, untersucht Ihre Abschlussmethodenimplementierung <xref:System.ComponentModel.AsyncCompletedEventArgs.UserState%2A?displayProperty=nameWithType> und entfernt es aus Ihrer Auflistung. Auf diese Weise verwendet übernimmt der Parameter `userState` die Rolle einer Aufgaben-ID.  
  
> [!NOTE]
> Sie müssen darauf achten, einen eindeutigen Wert für `userState` in Ihren Aufrufen an Überladungen mit mehreren Aufrufen bereitzustellen. Nicht eindeutige Aufgaben-IDs führen dazu, dass die asynchrone Klasse eine <xref:System.ArgumentException> auslöst.  
  
### <a name="canceling-pending-operations"></a>Abbrechen ausstehender Vorgänge  
 Es ist wichtig, dass asynchrone Vorgänge jederzeit vor Ihrem Abschluss abgebrochen werden können. Klassen, die das ereignisbasierte asynchrone Muster implementieren, verfügen über eine `CancelAsync`-Methode (wenn nur eine asynchrone Methode vorhanden ist) oder eine _MethodName_**AsyncCancel**-Methode (wenn mehrere asynchrone Methoden vorhanden sind).  
  
 Methoden, die mehrere Aufrufe zulassen, nehmen einen `userState`-Parameter an, der verwendet werden kann, um die Lebensdauer jeder Aufgabe nachzuverfolgen. `CancelAsync` nimmt einen `userState`-Parameter an, mit dem Sie bestimmte ausstehende Aufgaben abbrechen können.  
  
 Methoden, die nur einen einzigen ausstehenden Vorgang auf einmal unterstützen, wie `Method1Async(string param)`, können nicht abgebrochen werden.  
  
### <a name="receiving-progress-updates-and-incremental-results"></a>Erhalten von Statusaktualisierungen und inkrementellen Ergebnissen  
 Eine Klasse, die dem ereignisbasierten asynchronen Muster entspricht, kann optional ein Ereignis für die Statusverfolgung und inkrementelle Ergebnisse bereitstellen. Diese wird normalerweise `ProgressChanged` oder _MethodName_**ProgressChanged** genannt, und ihr entsprechender Ereignishandler nimmt den Parameter <xref:System.ComponentModel.ProgressChangedEventArgs> an.  
  
 Der Ereignishandler für das `ProgressChanged`-Ereignis kann die Eigenschaft <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A?displayProperty=nameWithType> untersuchen, um festzustellen, welcher Prozentsatz eines asynchronen Tasks abgeschlossen wurde. Diese Eigenschaft liegt zwischen 0 und 100 und kann verwendet werden, um die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft von <xref:System.Windows.Forms.ProgressBar> zu aktualisieren. Wenn mehrere asynchrone Vorgänge ausstehen, können Sie die Eigenschaft <xref:System.ComponentModel.ProgressChangedEventArgs.UserState%2A?displayProperty=nameWithType> verwenden, um zu unterscheiden, welcher Vorgang den Status meldet.  
  
 Einige Klassen melden möglicherweise inkrementelle Ergebnisse, wenn asynchrone Vorgänge fortgesetzt werden. Diese Ergebnisse werden in einer Klasse gespeichert, die von <xref:System.ComponentModel.ProgressChangedEventArgs> abgeleitet ist und als Eigenschaften in der abgeleiteten Klasse angezeigt. Sie können auf diese Ergebnisse im Ereignishandler für das `ProgressChanged`-Ereignis so zugreifen, wie Sie auf die <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>-Eigenschaft zugreifen würden. Wenn mehrere asynchrone Vorgänge ausstehen, können Sie die Eigenschaft <xref:System.ComponentModel.ProgressChangedEventArgs.UserState%2A> verwenden, um zu unterscheiden, welcher Vorgang inkrementelle Ergebnisse meldet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [How to: How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)
- [How to: Ausführen eines Vorgangs im Hintergrund](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [How to: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Ereignisbasiertes asynchrones Muster (EAP)](event-based-asynchronous-pattern-eap.md)
- [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
