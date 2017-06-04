---
title: "Implementieren des ereignisbasierten asynchronen Entwurfsmusters | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ereignisbasiertes asynchrones Muster"
  - "ProgressChangedEventArgs-Klasse"
  - "BackgroundWorker-Komponente"
  - "Ereignisse [.NET Framework], Asynchron"
  - "Asynchrones Muster"
  - "AsyncOperationManager-Klasse"
  - "Threading [.NET Framework], Asynchrone Funktionen"
  - "Komponenten [.NET Framework], asynchrone"
  - "AsyncOperation-Klasse"
  - "AsyncCompletedEventArgs-Klasse"
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Implementieren des ereignisbasierten asynchronen Entwurfsmusters
Wenn Sie eine Klasse mit einigen Vorgängen schreiben, die merkliche Verzögerung verursachen kann, sollten Sie es asynchrone Funktionalität durch die Implementierung [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Das ereignisbasierte asynchrone Muster bietet eine standardisierte Möglichkeit zum Verpacken einer Klasse, die über asynchrone Features verfügt. Wenn mit Hilfsklassen implementiert wie <xref:System.ComponentModel.AsyncOperationManager>, Ihre Klasse ordnungsgemäß funktioniert unter jedem beliebigen Anwendungsmodell, einschließlich [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], konsolenanwendungen und Windows Forms-Anwendung.  
  
 Ein Beispiel, das ereignisbasierte asynchrone Muster implementiert, wird, finden Sie unter [Gewusst wie: implementieren eine Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Für einfache asynchrone Operationen finden Sie möglicherweise die <xref:System.ComponentModel.BackgroundWorker> Komponente geeignet ist. Weitere Informationen zu <xref:System.ComponentModel.BackgroundWorker>, finden Sie unter [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
 Die folgende Liste beschreibt die Funktionen des ereignisbasierten asynchronen Musters in diesem Thema erläutert.  
  
-   Chancen für das ereignisbasierte asynchrone Muster implementieren  
  
-   Benennen von asynchronen Methoden  
  
-   Optionale Unterstützung von Abbrüchen  
  
-   Optionale Unterstützung der IsBusy-Eigenschaft  
  
-   Optional bieten Sie Unterstützung für Fortschrittsberichte  
  
-   Optional bieten Sie Unterstützung für die Rückgabe von inkrementeller Ergebnis  
  
-   Behandlung Out und Ref-Parameter in Methoden  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Chancen für das ereignisbasierte asynchrone Muster implementieren  
 Implementieren Sie das ereignisbasierte asynchrone Muster bei:  
  
-   Clients einer Klasse müssen nicht <xref:System.Threading.WaitHandle> und <xref:System.IAsyncResult> für asynchrone Vorgänge, d. h., die Abfrage der verfügbaren Objekte und <xref:System.Threading.WaitHandle.WaitAll%2A> oder <xref:System.Threading.WaitHandle.WaitAny%2A> müssen vom Client erstellt werden.  
  
-   Asynchrone Vorgänge vom Client mit der vertrauten Ereignis-und Delegatmodells verwaltet werden sollen.  
  
 Jeder Vorgang ist ein Kandidat für eine asynchrone Implementierung, aber Sie solche lange Wartezeiten übernommen wird, sollte berücksichtigt werden. Besonders geeignet sind Vorgänge, in denen Clients eine Methode aufrufen und bei Abschluss benachrichtigt werden, und kein weiterer Benutzereingriff erforderlich. Außerdem eignen sich Vorgänge, die fortlaufend ausgeführt werden in regelmäßigen Abständen Clients Fortschritte, inkrementelle Ergebnisse oder Zustandsänderungen benachrichtigen.  
  
 Weitere Informationen über die Gründe für die das ereignisbasierte asynchrone Muster unterstützen, finden Sie unter [entscheiden, wenn das ereignisbasierte asynchrone Muster implementieren](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).  
  
## <a name="naming-asynchronous-methods"></a>Benennen von asynchronen Methoden  
 Für jede synchrone Methode *MethodName* für die Sie ein asynchrones Gegenstück bereitstellen möchten:  
  
 Definieren einer *MethodName* `Async` Methode, die:  
  
-   Gibt `void`zurück.  
  
-   Verwendet die gleichen Parameter wie der *MethodName* Methode.  
  
-   Akzeptiert mehrere Aufrufe.  
  
 Definieren Sie optional eine *MethodName* `Async` Überladung, die mit *MethodName*`Async`, aber mit einem zusätzlichen Parameter Objektwerten aufgerufen `userState`. Wenn Sie vorbereitet sind, um mehrere gleichzeitige Aufrufe der Methode, in diesem Fall zu verwalten, müssen Sie der `userState` Wert an alle Ereignishandler, die Aufrufe der Methode zu unterscheiden, übermittelt werden. Außerdem können Sie dazu einfach als ein Ausgangspunkt für den späteren Abruf speichern.  
  
 Für jede Separate *MethodName* `Async` Methodensignatur:  
  
1.  Definieren Sie das folgende Ereignis in der gleichen Klasse wie die Methode ein:  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  Der folgende Delegat definieren und <xref:System.ComponentModel.AsyncCompletedEventArgs>. Diese werden wahrscheinlich außerhalb der Klasse selbst, aber im selben Namespace definiert.  
  
    ```vb  
    Public Delegate Sub MethodNameCompletedEventHandler( _  
        ByVal sender As Object, _  
        ByVal e As MethodNameCompletedEventArgs)  
  
    Public Class MethodNameCompletedEventArgs  
        Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As MyReturnType  
    End Property  
    ```  
  
    ```csharp  
    public delegate void MethodNameCompletedEventHandler(object sender,   
        MethodNameCompletedEventArgs e);  
  
    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
    {  
        public MyReturnType Result { get; }  
    }  
    ```  
  
    -   Sicherstellen, dass die *MethodName* `CompletedEventArgs` Klasse macht Member als schreibgeschützte Eigenschaften und keine Felder verfügbar, wie Felder binden von Daten verhindern.  
  
    -   Definieren einer <xref:System.ComponentModel.AsyncCompletedEventArgs>-abgeleitete Klassen für Methoden, die keine Ergebnisse erzeugen. Verwenden Sie einfach eine Instanz des <xref:System.ComponentModel.AsyncCompletedEventArgs> selbst.  
  
        > [!NOTE]
        >  Es ist durchaus akzeptabel, wenn möglich und zweckmäßig, Wiederverwendung von Delegat und <xref:System.ComponentModel.AsyncCompletedEventArgs> Typen. In diesem Fall die Benennung nicht konsistent sein werden, wie mit dem Methodennamen, da ein gegebener Delegat und <xref:System.ComponentModel.AsyncCompletedEventArgs> wird nicht an eine einzelne Methode gebunden werden.  
  
## <a name="optionally-support-cancellation"></a>Optionale Unterstützung von Abbrüchen  
 Wenn Ihre Klasse Abbruch asynchroner Operationen unterstützen, sollte die Abbruch an den Client bereitgestellt werden, wie unten beschrieben. Beachten Sie, dass zwei Entscheidungspunkte, die vor dem Definieren der Unterstützung für den Abbruch erreicht werden müssen:  
  
-   Verfügt Ihre Klasse, einschließlich erwarteten zukünftig zu erwartende, nur eine asynchrone Operation, die Abbruch unterstützt?  
  
-   Können Sie die asynchronen Vorgänge, die Unterstützung für den Abbruch mehrere ausstehende Vorgänge unterstützen? Ist, ist die *MethodName* `Async` -Methode einen `userState` -Parameter, und lässt mehrere Aufrufe Aufrufes gewartet?  
  
 Verwenden Sie die Antworten auf diese beiden Fragen in der folgenden Tabelle, um zu bestimmen, welche die Signatur Ihrer Abbruchmethode werden soll.  
  
### <a name="visual-basic"></a>Visual Basic  
  
||Gleichzeitige Unterstützung mehrerer Operationen|Nur ein Vorgang zu einem Zeitpunkt|  
|------|------------------------------------------------|----------------------------------|  
|Eine asynchrone Operation in der gesamten Klasse|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|Mehrere asynchrone Operationen in der Klasse|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>A#  
  
||Gleichzeitige Unterstützung mehrerer Operationen|Nur ein Vorgang zu einem Zeitpunkt|  
|------|------------------------------------------------|----------------------------------|  
|Eine asynchrone Operation in der gesamten Klasse|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|Mehrere asynchrone Operationen in der Klasse|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 Wenn Sie definieren die `CancelAsync(object userState)` -Methode, Clients müssen vorsichtig bei der Auswahl von deren Diese Statuswerte zwischen allen im Objekt aufgerufenen asynchronen Methoden und nicht nur zwischen allen Aufrufen einer einzelnen asynchronen Methode sein.  
  
 Die Entscheidung, benennen Sie die einzelnen asynchronen Operation Version *MethodName* `AsyncCancel` basiert auf wird die Methode in einer entwurfsumgebung wie Visual Studio IntelliSense leichter ermitteln können. Diese Gruppen von verwandten Elementen und unterscheiden sie sich von anderen Mitgliedern, die nichts mit der asynchronen Funktionalität zu tun haben. Wenn Sie davon ausgehen, dass möglicherweise weitere asynchrone Operationen hinzugefügt werden in zukünftigen Versionen ist es besser, definieren Sie `CancelAsync`.  
  
 Definieren Sie mehrere Methoden aus der obigen Tabelle nicht in der gleichen Klasse. Wird, die keinen Sinn machen, oder es wird die Klassenschnittstelle mit einer Verbreitung von Methoden überladen.  
  
 Diese Methoden in der Regel werden sofort zurückgegeben, und der Vorgang kann oder möglicherweise nicht tatsächlich abgebrochen. Im Ereignishandler für die *MethodName* `Completed` -Ereignis, das *MethodName* `CompletedEventArgs` Objekt enthält eine `Cancelled` -Feld, das Clients verwenden können, um zu bestimmen, ob ein Abbruch aufgetreten ist.  
  
 Halten Sie sich an das beschriebene Semantik [Best Practices für das ereignisbasierte asynchrone Muster implementieren](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-support-the-isbusy-property"></a>Optionale Unterstützung der IsBusy-Eigenschaft  
 Wenn Ihre Klasse mehrere gleichzeitige Aufrufe nicht unterstützt, ist es ein `IsBusy` Eigenschaft. Dies ermöglicht Entwicklern, um zu bestimmen, ob ein *MethodName* `Async` -Methode wird ausgeführt, ohne Abfangen einer Ausnahme von der *MethodName* `Async` Methode.  
  
 Halten Sie sich an den `IsBusy` Semantik beschrieben [Best Practices für das ereignisbasierte asynchrone Muster implementieren](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>Optional bieten Sie Unterstützung für Fortschrittsberichte  
 Es ist häufig wünschenswert, dass ein asynchroner Vorgang zum Fortschritt während des Betriebs. Das ereignisbasierte asynchrone Muster bietet eine Richtlinie dafür angeben.  
  
-   Definieren Sie optional eine Ereignis, um den asynchronen Vorgang ausgelöst und im entsprechenden Thread aufgerufen. Die <xref:System.ComponentModel.ProgressChangedEventArgs> -Objekt enthält eine Ganzzahlwert Statusanzeige, die zwischen 0 und 100 liegen soll.  
  
-   Nennen Sie dieses Ereignis wie folgt:  
  
    -   `ProgressChanged`Wenn die Klasse mehrere asynchrone Operationen besitzt (oder vermutlich noch um mehrere asynchrone Operationen in zukünftigen Versionen erweitert wird);  
  
    -   *MethodName* `ProgressChanged` Wenn die Klasse über eine einzelne asynchrone Operation verfügt.  
  
     Diese Benennungskonvention Auswahl entspricht, die für die Abbruchmethode, wie in der Abbruchmethode beschrieben.  
  
 Dieses Ereignis sollte verwenden die <xref:System.ComponentModel.ProgressChangedEventHandler> Signatur des Delegaten und <xref:System.ComponentModel.ProgressChangedEventArgs> Klasse. Auch wenn eine Anwendungsdomäne spezifischere Statusanzeige (für die Instanz, gelesene Bytes und die Gesamtanzahl der Bytes für ein Download-Vorgang) bereitgestellt werden kann, Sie sollten definieren eine abgeleitete Klasse von <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 Beachten Sie, dass nur ein `ProgressChanged` oder *MethodName* `ProgressChanged` -Ereignis für die Klasse, unabhängig von der Anzahl von asynchronen Methoden unterstützt. Clients verwenden sollen die `userState` -Objekt, das an die *MethodName* `Async` Methoden um Statusupdates auf mehrere gleichzeitige Vorgänge unterscheiden zu können.  
  
 Es gibt möglicherweise Situationen, in der mehrere Vorgänge unterstützt, und einen anderen Indikator für Status zurück. In diesem Fall kann ein einzelner `ProgressChanged` Ereignis ist nicht zulässig, und Sie sollten unterstützen mehrerer `ProgressChanged` Ereignisse. Verwenden Sie in diesem Fall einem Benennungsmuster *MethodName* `ProgressChanged` für jede *MethodName* `Async` Methode.  
  
 Halten Sie sich an die Fortschrittsberichterstattung Semantik beschrieben [Best Practices für das ereignisbasierte asynchrone Muster implementieren](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>Optional bieten Sie Unterstützung für die Rückgabe von inkrementeller Ergebnis  
 Manchmal kann ein asynchroner Vorgang inkrementelle Ergebnisse vor dem Abschluss zurückgeben. Es gibt eine Reihe von Optionen, die zur Unterstützung dieses Szenarios verwendet werden können. Es folgen einige Beispiele.  
  
### <a name="single-operation-class"></a>Einzelnen Operation-Klasse  
 Wenn Ihre Klasse nur eine einzelne asynchrone Operation unterstützt, und der Vorgang ist dann inkrementelle Ergebnisse zurückgeben:  
  
-   Erweitern der <xref:System.ComponentModel.ProgressChangedEventArgs> damit die inkrementellen Ergebnisdaten aufnehmen, und Definieren einer *MethodName* `ProgressChanged` Ereignis mit diesen erweiterten Daten.  
  
-   Dies wird *MethodName* `ProgressChanged` Ereignis, wenn es ein inkrementelles Ergebnis zu Berichten.  
  
 Diese Lösung bezieht sich ausdrücklich auf einer einzelnen asynchronen Operation-Klasse, da kein Problem mit dem gleichen Ereignis auftreten kann, dass inkrementelle Ergebnisse für "alle Operationen" zurückgegeben wird, als die *MethodName* `ProgressChanged` -Ereignis der Fall ist.  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Klasse mit mehreren Operationen mit homogenen, inkrementellen Ergebnissen  
 In diesem Fall die Klasse unterstützt mehrere asynchrone Methoden, die jeweils der inkrementelle Ergebnisse zurückgeben kann, und diese alle inkrementellen Ergebnisse haben denselben Datentyp aufweisen.  
  
 Befolgen Sie die einzelnen Operation-Klassen, wie dem oben beschriebenen <xref:System.EventArgs> -Struktur für alle inkrementellen Ergebnisse geeignet ist. Definieren einer `ProgressChanged` Ereignis, sondern mit einer *MethodName* `ProgressChanged` Ereignis, da es für mehrere asynchrone Methoden gilt.  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Klasse mit mehreren Operationen mit heterogenen, inkrementellen Ergebnissen  
 Wenn Ihre Klasse mehrere asynchrone Methoden unterstützt, sollte jeder eine andere Art von Daten zurückgeben Sie:  
  
-   Trennen des inkrementellen Resultsets aus Ihrem Fortschrittsberichterstattung reporting.  
  
-   Definieren Sie eine Separate *MethodName* `ProgressChanged` -Ereignis mit den entsprechenden <xref:System.EventArgs> für jede asynchrone Methode, diese Methode inkrementellen Ergebnisdaten behandeln.  
  
 Rufen Sie diesen Ereignishandler für den entsprechenden Thread wie unter [Best Practices für das ereignisbasierte asynchrone Muster implementieren](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>Behandlung Out und Ref-Parameter in Methoden  
 Obwohl die Verwendung von `out` und `ref` ist, im Allgemeinen abgeraten, in .NET Framework, hier sind die Regeln zu beachten, wenn sie vorhanden sind:  
  
 Eine synchrone Methode *MethodName*:  
  
-   `out`Parameter für *MethodName* muss nicht Teil des *MethodName*`Async`. Sie sollten stattdessen Teil sein *MethodName* `CompletedEventArgs` mit dem gleichen Namen wie dessen Parameter in *MethodName* (es sei denn, ein geeigneter Namen).  
  
-   `ref`Parameter für *MethodName* sollte angezeigt werden, als Teil des *MethodName*`Async`, und als Teil der *MethodName* `CompletedEventArgs` mit dem gleichen Namen wie dessen Parameter in *MethodName* (es sei denn, ein geeigneter Namen).  
  
 Angenommen:  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 Die asynchrone Methode und ihre <xref:System.ComponentModel.AsyncCompletedEventArgs> Klasse sieht wie folgt:  
  
```vb  
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)  
  
Public Class MethodNameCompletedEventArgs  
    Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As Integer   
    End Property  
    Public ReadOnly Property Arg2() As String   
    End Property  
    Public ReadOnly Property Arg3() As String   
    End Property  
End Class  
```  
  
```csharp  
public void MethodNameAsync(string arg1, string arg2);  
  
public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
{  
    public int Result { get; };  
    public string Arg2 { get; };  
    public string Arg3 { get; };  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.ProgressChangedEventArgs>   
 <xref:System.ComponentModel.AsyncCompletedEventArgs>   
 [Gewusst wie: implementieren eine Komponente, die das ereignisbasierte asynchrone Muster unterstützt,](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Gewusst wie: implementieren ein Formulars, das eine Hintergrundoperation verwendet](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Gründe für das ereignisbasierte asynchrone Muster implementieren.](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)   
 [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Bewährte Methoden für das ereignisbasierte asynchrone Muster implementieren](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)