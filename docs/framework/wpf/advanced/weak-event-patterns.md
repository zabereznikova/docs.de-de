---
title: Schwache Ereignismuster
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a27e17e4940ff68f34d1e7e4accfb9e112bc412b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="weak-event-patterns"></a>Schwache Ereignismuster
Bei Anwendungen ist es möglich, dass ein Handler, die auf Ereignisquellen angefügt sind nicht in Abstimmung mit dem Listenerobjekt zerstört werden, die die Quelle den Handler angefügt. Diese Situation kann zu Speicherverlusten führen. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]führt ein Entwurfsmuster, die verwendet werden kann, um dieses Problem zu beheben, stellen Sie eine dedizierte Managerklasse für bestimmte Ereignisse bereit, und Implementieren einer Schnittstelle zum Listener für dieses Ereignis an. Dieses Entwurfsmusters heißt die *schwacher Ereignismuster*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>Gründe für das Implementieren der schwacher Ereignismuster  
 Überwachung der Ereignisse kann zu Speicherverlusten führen. Das typische Verfahren für die Überwachung eines Ereignisses wird die sprachspezifische Syntax verwenden, die einen Handler an ein Ereignis in der Quelle angefügt wird. Beispielsweise ist in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], dass die Syntax lautet: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Diese Technik wird einen starken Verweis von der Ereignisquelle um der Ereignislistener erstellt. Normalerweise führt dazu, dass einen Ereignishandler für einen Listener anfügen den Listener eine Lebensdauer eines Objekts haben, die von der Lebensdauer eines Objekts in der Quelle beeinflusst wird, (es sei denn, die der Ereignishandler explizit entfernt ist). Allerdings in bestimmten Fällen sollten Sie die Lebensdauer eines Objekts in den Listener durch andere Faktoren gesteuert werden, z. B., ob es derzeit der visuellen Struktur der Anwendung und nicht von der Lebensdauer der Quelle gehört. Sobald die Objektlebensdauer Quelle über die Lebensdauer des Listeners hinausgeht, führt das normale Ereignismuster zu einem Speicherverlust: der Listener wird aufrechterhalten länger als vorgesehen.  
  
 Das schwacher Ereignismuster dient zum Lösen dieses Problems der Arbeitsspeicher von Speicherverlusten. Das schwacher Ereignismuster kann verwendet werden, wenn ein Listener für ein Ereignis registrieren muss, der Listener ist jedoch nicht explizit bekannt beim Aufheben der Registrierung. Das schwacher Ereignismuster kann auch verwendet werden, wenn die Lebensdauer eines Objekts in der Quelle nützlich Objektlebensdauer des Listeners überschreitet. (In diesem Fall *nützlich* wird von Ihnen bestimmt.) Das schwacher Ereignismuster ermöglicht dem Listener zum Registrieren für und ohne Auswirkungen auf die Merkmale des Listeners in keiner Weise Objektlebensdauer das Ereignis empfangen. Aktiviert ist, der implizite Verweis aus der Quelle nicht bestimmt werden, ob der Listener für die Garbagecollection geeignet sind. Der Verweis ist, einen schwachen Verweis, und somit die Benennung von der schwacher Ereignismuster und die zugehörigen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Der Listener kann werden vom Garbage Collector erfasst, oder andernfalls zerstört und die Quelle kann weiterhin ohne Beibehaltung Handlerverweise mit einem Objekt jetzt zerstört.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>Wer soll das schwacher Ereignismuster implementieren?  
 Implementieren des Musters schwache Ereignis ist in erster Linie für Autoren interessant. Als Autor eines Steuerelements sind Sie größtenteils verantwortlich für das Verhalten und die Kapselung der Ihrer Kontrolle und die Auswirkungen auf Anwendungen, die ihm in der er eingefügt wird. Dies schließt das Lebensdauer-Verhalten des Steuerelements ein, insbesondere die Behandlung des Speicherverlustproblems beschriebene Speicher.  
  
 Bestimmte Szenarien eignen sich grundsätzlich auf die Anwendung das schwacher Ereignismuster. Ein solches Szenario ist die Datenbindung. Bei einer Datenbindung wird häufig für das Quellobjekt, das als Ziel einer Bindung wird vollständig unabhängig von der Listener-Objekt sein. Viele Aspekte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereits zum Binden von Daten der schwachen-Ereignismuster in der Implementierung der Ereignisse angewendet haben.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Gewusst wie: Implementieren der schwacher Ereignismuster  
 Es gibt drei Möglichkeiten zum Implementieren schwacher Ereignismuster. In der folgenden Tabelle werden die drei Ansätze aufgeführt und enthält hilfreiche Informationen für die Verwendung jedes sollten.  
  
|Ansatz|Implementieren von|  
|--------------|-----------------------|  
|Verwenden einer vorhandenen schwache Ereignis-Manager-Klasse|Wenn das Ereignis, die Sie abonnieren möchten ein entsprechendes hat <xref:System.Windows.WeakEventManager>, verwenden Sie den vorhandenen schwache Ereignis-Manager. Eine Liste der schwache Ereignis-Manager, die in WPF enthalten sind, finden Sie in die Vererbungshierarchie der <xref:System.Windows.WeakEventManager> Klasse. Beachten Sie jedoch, dass es relativ wenige schwache Ereignis-Manager, die mit WPF, enthalten sind gibt, so Sie wahrscheinlich eine der anderen Methoden auswählen müssen.|  
|Verwenden einer generischen schwachen Ereignis-Manager-Klasse|Verwenden Sie eine generische <xref:System.Windows.WeakEventManager%602> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar ist, Sie möchten eine einfache Möglichkeit zum Implementieren und Sie sind nicht besorgt Effizienz. Die generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als eine vorhandene oder benutzerdefinierte schwache Ereignis-Manager. Beispielsweise ist die generische Klasse mehrere Reflektion, um das Ereignis angegebenen Ereignisnamens zu ermitteln. Außerdem wird im Code auf das Ereignis zu registrieren, indem Sie mithilfe der allgemeinen <xref:System.Windows.WeakEventManager%602> ist mehr als die Verwendung einer vorhandenen ausführliche oder benutzerdefinierte <xref:System.Windows.WeakEventManager>.|  
|Erstellen Sie eine benutzerdefinierte schwache Ereignis-Manager-Klasse|Erstellen eines benutzerdefinierten <xref:System.Windows.WeakEventManager> Wenn Sie eine vorhandene <xref:System.Windows.WeakEventManager> ist nicht verfügbar, und Sie möchten die optimale Effizienz. Mithilfe einer benutzerdefinierten <xref:System.Windows.WeakEventManager> zum Abonnieren ein Ereignisses wird effizienter sein, aber führen Sie die Kosten für das Schreiben von weiteren Code am Anfang anfallen.|  
  
 In den folgenden Abschnitten wird beschrieben, wie das schwacher Ereignismuster implementieren.  Für den Rahmen dieser Erläuterung weist folgende Merkmale auf das Ereignis abonnieren.  
  
-   Der Ereignisname wird `SomeEvent`.  
  
-   Das Ereignis wird ausgelöst, durch die `EventSource` Klasse.  
  
-   Der Ereignishandler weist den Typ: `SomeEventEventHandler` (oder `EventHandler<SomeEventEventArgs>`).  
  
-   Das Ereignis übergibt einen Parameter vom Typ `SomeEventEventArgs` an die Ereignishandler.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Verwenden einer vorhandenen schwache Ereignis-Manager-Klasse  
  
1.  Suchen Sie nach einer vorhandenen schwache Ereignis Manager.  
  
     Eine Liste der schwache Ereignis-Manager, die in WPF enthalten sind, finden Sie in die Vererbungshierarchie der <xref:System.Windows.WeakEventManager> Klasse.  
  
2.  Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.  
  
     Angenommen, Ihr Code das folgenden Muster zum Abonnieren eines Ereignisses verwendet:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie sie an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Auf ähnliche Weise, wenn im Code des folgenden Musters verwendet, um ein Ereignis zu kündigen:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie sie an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Mithilfe der generischen schwachen Ereignis-Manager-Klasse  
  
1.  Die generische <xref:System.Windows.WeakEventManager%602> Klasse anstelle der normalen ereigniseinbindung.  
  
     Bei Verwendung von <xref:System.Windows.WeakEventManager%602> um Ereignislistener zu registrieren, geben Sie die Ereignisquelle und <xref:System.EventArgs> Typ wie der Typparameter der Klasse und der Aufruf <xref:System.Windows.WeakEventManager%602.AddHandler%2A> wie im folgenden Code gezeigt:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Erstellen einer benutzerdefinierten schwache Ereignis-Manager-Klasse  
  
1.  Kopieren Sie die folgenden Klassenvorlage in Ihr Projekt.  
  
     Diese Klasse erbt von der <xref:System.Windows.WeakEventManager> Klasse.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  Ersetzen Sie die `SomeEventWeakEventManager` durch den Namen Ihres eigenen Namen.  
  
3.  Ersetzen Sie die drei Namen, die zuvor beschriebenen mit den entsprechenden Namen für Ihr Ereignis. (`SomeEvent`, `EventSource`, und `SomeEventEventArgs`)  
  
4.  Legen Sie die Sichtbarkeit (öffentlich / privaten / internen) der schwachen Ereignisklasse Manager, um die gleiche Sichtbarkeit wie die von ihm verwalteten Ereignis.  
  
5.  Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.  
  
     Angenommen, Ihr Code das folgenden Muster zum Abonnieren eines Ereignisses verwendet:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie sie an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Auf ähnliche Weise, wenn im Code des folgenden Musters verwendet, um ein Ereignis zu kündigen:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie sie an, in dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)
