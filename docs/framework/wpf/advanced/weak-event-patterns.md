---
title: Schwache Ereignismuster
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: e0cd6837de626fa6bcd560811c6a70f7f6604daa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669364"
---
# <a name="weak-event-patterns"></a>Schwache Ereignismuster
Bei Anwendungen ist es möglich, dass der Handler, die Ereignisquellen angefügt sind, nicht in Koordination mit dem Listenerobjekt zerstört werden, die die Quelle der Handler zugeordnet. Diese Situation kann zu Arbeitsspeicherverlusten führen. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt ein Entwurfsmuster, die verwendet werden kann, um dieses Problem zu beheben, indem Sie eine dedizierte Manager-Klasse für bestimmte Ereignisse bereitstellen und Implementieren einer Schnittstelle zum Listener für das betreffende Ereignis. Dieses Entwurfsmuster wird als bezeichnet die *Muster für schwache Ereignisse*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>Gründe für das Implementieren der schwache Ereignismuster  
 Überwachen von Ereignissen kann zu Arbeitsspeicherverlusten führen. Die normale Technik für die Überwachung auf ein Ereignis ist, die sprachspezifische Syntax zu verwenden, die einen Handler an ein Ereignis für eine Datenquelle angefügt wird. Z. B. in C#, dass die Syntax lautet: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Diese Methode erstellt einen starken Verweis aus der Ereignisquelle in den Ereignislistener. Normalerweise wird das Anhängen eines ereignishandlers für einen Listener die Überwachung für die eine Lebensdauer haben, die von der Quelle der Objektlebensdauer beeinflusst ist (es sei denn, der Ereignishandler explizit entfernt wird). Unter bestimmten Umständen Sie sollten jedoch die Objektlebensdauer des Listeners, der durch andere Faktoren gesteuert werden, wie z. B., ob er zurzeit an der visuellen Struktur der Anwendung und nicht von der Lebensdauer der Quelle gehört. Wenn die Lebensdauer der Energiequelle Objekt die Objektlebensdauer des Listeners, der erweitert wird, wird das normale Ereignismuster zu einem Speicherverlust führt: der Listener ist länger als vorgesehen aktiv bleiben.  
  
 Das Muster für schwache Ereignisse soll dieses Memory Leak Problem zu beheben. Das Muster für schwache Ereignisse kann verwendet werden, wenn ein Listener für ein Ereignis registrieren muss, aber der Listener ist nicht explizit bekannt beim Aufheben der Registrierung. Das Muster für schwache Ereignisse kann auch verwendet werden, wenn die Objektlebensdauer der Quelle des Listeners nützlich Objektlebensdauer überschreitet. (In diesem Fall *nützlich* wird bestimmt, indem Sie Sie.) Das Muster für schwache Ereignisse ermöglicht den Listener, um sich anzumelden und das Ereignis empfangen, ohne Auswirkungen auf die Objekteigenschaften für die Lebensdauer des Listeners in keiner Weise. Aktiviert ist, wird der implizite Verweis aus der Quelle nicht ermittelt werden, ob der Listener für die Garbagecollection ist. Der Verweis ist, einen schwachen Verweis, also die Benennung von am schwachen Ereignismuster und die zugehörigen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Der Listener kann Garbage gesammelt, oder andernfalls zerstört, und die Quelle kann weiterhin ohne Beibehaltung Handlerverweise auf ein jetzt zerstörte-Objekt.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>Wer sollte das Muster für schwache Ereignisse implementieren?  
 Implementieren der Muster für schwache Ereignisse ist in erster Linie für Autoren von Steuerelementen interessant. Als Autor eines Steuerelements sind Sie größtenteils verantwortlich für das Verhalten und die Kapselung der das Steuerelement und die Auswirkungen, die sie für Anwendungen in der er eingefügt wird. Dies schließt-Verhalten des Steuerelements Lebensdauer, insbesondere die Behandlung des Problems beschrieben Memory Leak.  
  
 Bestimmte Szenarien eignen sich grundsätzlich zur Anwendung des am schwachen Ereignismuster. Ein solches Szenario ist die Datenbindung. Bei der Datenbindung ist es üblich, dass das Quellobjekt ein Ziel einer Bindung ist vollkommen unabhängig von der kommunikationslistener-Objekt werden. Viele Aspekte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Datenbindung bereits am schwachen Ereignismuster in zur Implementierung von den Ereignissen angewendet haben.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Gewusst wie: Implementieren der schwache Ereignismuster  
 Es gibt drei Möglichkeiten zum Implementieren der Muster für schwache Ereignisse. In der folgende Tabelle sind die drei Ansätze sowie hilfreiche Informationen zur beim verwendet werden sollte.  
  
|Ansatz|Für implementieren|  
|--------------|-----------------------|  
|Verwenden Sie eine vorhandene schwache Ereignis-Manager-Klasse|Wenn das Ereignis, das Sie abonnieren möchten ein entsprechendes hat <xref:System.Windows.WeakEventManager>, verwenden Sie den vorhandenen schwache Ereignis-Manager. Eine Liste von Managern für schwache Ereignisse, die mit WPF enthalten sind, finden Sie in der Vererbungshierarchie in den <xref:System.Windows.WeakEventManager> Klasse. Da die enthalten schwache Ereignis-Manager beschränkt sind, müssen Sie wahrscheinlich eine der anderen Ansätze auszuwählen.|  
|Verwenden Sie eine generische schwache Ereignis-Manager-Klasse|Ein generisches <xref:System.Windows.WeakEventManager%602> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar ist, Sie möchten eine einfache Möglichkeit zum Implementieren und Sie sind nicht überlegen zu Effizienz. Die generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als eine vorhandene oder benutzerdefinierte WeakEvent-Manager. Beispielsweise ist die generische Klasse weitere Reflektion, um das Ereignis, erhält der Name eines Ereignisses zu ermitteln. Außerdem wird im Code, der das Ereignis zu registrieren, indem Sie mithilfe der allgemeinen <xref:System.Windows.WeakEventManager%602> ist mehr ausführlicher als die Verwendung einer vorhandenen oder benutzerdefinierten <xref:System.Windows.WeakEventManager>.|  
|Erstellen Sie eine benutzerdefinierte schwache Ereignis-Manager-Klasse|Erstellen eines benutzerdefinierten <xref:System.Windows.WeakEventManager> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar und soll die Optimierung der Effizienz. Mithilfe einer benutzerdefinierten <xref:System.Windows.WeakEventManager> zum Abonnieren ein Ereignisses wird effizienter sein, aber Sie fallen die Kosten für das Schreiben von weiteren Code am Anfang.|  
|Verwenden Sie einen Drittanbieter-schwache Ereignis-manager|NuGet kann [mehrere schwache Ereignis-Manager](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) und Frameworks für viele WPF unterstützen auch das Muster (z. B. finden Sie unter [von Prism-Dokumentation auf lose gekoppelte Ereignisabonnement](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).|

 In den folgenden Abschnitten wird beschrieben, wie das Muster für schwache Ereignisse zu implementieren.  Für den Rahmen dieser Erläuterung weist folgende Merkmale auf das Ereignis abonnieren.  
  
- Der Ereignisname wird `SomeEvent`.  
  
- Das Ereignis wird ausgelöst, durch die `EventSource` Klasse.  
  
- Der Ereignishandler verfügt über Typ: `SomeEventEventHandler` (oder `EventHandler<SomeEventEventArgs>`).  
  
- Das Ereignis übergibt einen Parameter vom Typ `SomeEventEventArgs` an die Ereignishandler.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Verwenden einer vorhandenen schwache Ereignis-Manager-Klasse  
  
1. Suchen Sie ein vorhandenes schwache Ereignis Manager.  
  
     Eine Liste von Managern für schwache Ereignisse, die mit WPF enthalten sind, finden Sie in der Vererbungshierarchie in den <xref:System.Windows.WeakEventManager> Klasse.  
  
2. Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.  
  
     Angenommen, Ihr Code im folgenden Format verwendet, um ein Ereignis abonnieren:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie ihn an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Auf ähnliche Weise, wenn im Code das folgende Muster verwendet, um ein Ereignisabonnement zu kündigen:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie ihn an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Mithilfe der generischen schwache Ereignis-Manager-Klasse  
  
1. Die generische <xref:System.Windows.WeakEventManager%602> -Klasse anstelle der normalen ereigniseinbindung.  
  
     Bei Verwendung von <xref:System.Windows.WeakEventManager%602> um Ereignislistener zu registrieren, geben Sie die Ereignisquelle und <xref:System.EventArgs> Typ wie die Typparameter von der Klasse und rufen <xref:System.Windows.WeakEventManager%602.AddHandler%2A> wie im folgenden Code gezeigt:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Erstellen eine benutzerdefinierte schwache Ereignis-Manager-Klasse  
  
1. Kopieren Sie die folgende Klassenvorlage in Ihr Projekt ein.  
  
     Diese Klasse erbt von der <xref:System.Windows.WeakEventManager> Klasse.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. Ersetzen Sie die `SomeEventWeakEventManager` durch den Namen Ihres eigenen Namen.  
  
3. Ersetzen Sie die drei Namen, die zuvor mit den entsprechenden Namen für das Ereignis beschrieben. (`SomeEvent`, `EventSource`, und `SomeEventEventArgs`)  
  
4. Legen Sie die Sichtbarkeit der WeakEvent-Manager-Klasse (öffentliche / private / interne), auf die gleiche Sichtbarkeit wie Ereignis, das er verwaltet.  
  
5. Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.  
  
     Angenommen, Ihr Code im folgenden Format verwendet, um ein Ereignis abonnieren:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie ihn an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Auf ähnliche Weise, wenn der Code das folgende Muster verwendet, um ein Ereignis kündigen:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie ihn an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
