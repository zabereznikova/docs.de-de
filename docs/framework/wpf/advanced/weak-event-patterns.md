---
title: Schwache Ereignismuster
description: Erfahren Sie mehr über das Windows Presentation Foundation schwache Ereignis Muster, das das Problem von Handlern behandelt, die nicht zerstört werden, und damit Speicher Verluste vermeiden.
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 75c6888c8ac20c41d13e3787005377c75248c5d9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168263"
---
# <a name="weak-event-patterns"></a>Schwache Ereignismuster
In-Anwendungen ist es möglich, dass an Ereignis Quellen angefügte Handler nicht in Abstimmung mit dem Listenerobjekt zerstört werden, das den Handler an die Quelle angefügt hat. Diese Situation kann zu Speicher Verlusten führen. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]führt ein Entwurfsmuster ein, das verwendet werden kann, um dieses Problem zu beheben, indem eine dedizierte Manager-Klasse für bestimmte Ereignisse bereitgestellt und eine Schnittstelle für Listener für dieses Ereignis implementiert wird. Dieses Entwurfsmuster wird als *schwaches Ereignis Muster*bezeichnet.  
  
## <a name="why-implement-the-weak-event-pattern"></a>Gründe für die Implementierung des schwachen Ereignis Musters  
 Das Lauschen auf Ereignisse kann zu Speicher Verlusten führen. Die typische Vorgehensweise zum lauschen auf ein Ereignis besteht darin, die sprachspezifische Syntax zu verwenden, die einen Handler an ein Ereignis in einer Quelle anfügt. In c# lautet die Syntax z. b.: `source.SomeEvent += new SomeEventHandler(MyEventHandler)` .  
  
 Diese Technik erstellt einen starken Verweis von der Ereignis Quelle auf den Ereignislistener. Normalerweise bewirkt das Anfügen eines Ereignis Handlers für einen Listener, dass der Listener eine Objekt Lebensdauer hat, die von der Objekt Lebensdauer der Quelle beeinflusst wird (es sei denn, der Ereignishandler wird explizit entfernt). Unter bestimmten Umständen möchten Sie jedoch möglicherweise, dass die Objekt Lebensdauer des Listener von anderen Faktoren gesteuert wird, z. b. ob er derzeit zur visuellen Struktur der Anwendung gehört, und nicht nach der Lebensdauer der Quelle. Wenn die Lebensdauer des Quell Objekts über die Objekt Lebensdauer des Listener hinausgeht, führt das normale Ereignis Muster zu einem Speicherleck: der Listener bleibt länger als beabsichtigt.  
  
 Das schwache Ereignis Muster ist so konzipiert, dass dieses Speicherlecks-Problem gelöst wird. Das schwache Ereignis Muster kann immer dann verwendet werden, wenn ein Listener für ein Ereignis registriert werden muss, aber der Listener weiß nicht explizit, wann die Registrierung aufgehoben werden soll. Das schwache Ereignis Muster kann auch verwendet werden, wenn die Objekt Lebensdauer der Quelle die nützliche Objekt Lebensdauer des Listener überschreitet. (In diesem Fall wird *nützlich* von Ihnen bestimmt.) Das schwache Ereignis Muster ermöglicht dem Listener, sich für das Ereignis zu registrieren und das Ereignis zu empfangen, ohne die Eigenschaften der Objekt Lebensdauer in irgendeiner Weise zu beeinträchtigen. Tatsächlich bestimmt der implizierte Verweis aus der Quelle nicht, ob der Listener für Garbage Collection geeignet ist. Der Verweis ist eine schwache Referenz und somit die Benennung des schwachen Ereignis Musters und der zugehörigen APIs. Der Listener kann auf eine Garbage Collection oder anderweitig zerstört werden, und die Quelle kann fortgesetzt werden, ohne dass nicht entladbare Handlerverweise auf ein jetzt zerstörtes Objekt beibehalten werden.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>Wer sollte das schwache Ereignis Muster implementieren?  
 Die Implementierung des schwachen Ereignis Musters ist hauptsächlich für Autoren von Steuerelementen interessant. Als Autor eines Steuer Elements sind Sie größtenteils verantwortlich für das Verhalten und die Kapselung Ihres Steuer Elements und die Auswirkungen, die es auf Anwendungen hat, in die es eingefügt wurde. Dies schließt das Verhalten der Steuerungsobjekt Lebensdauer ein, insbesondere die Behandlung des beschriebenen Speicherlecks Problems.  
  
 Bestimmte Szenarien sind von Natur aus für die Anwendung des schwachen Ereignis Musters geeignet. Ein solches Szenario ist die Datenbindung. Bei der Datenbindung ist es üblich, dass das Quell Objekt vollständig unabhängig vom Listenerobjekt ist, das das Ziel einer Bindung ist. Viele Aspekte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Datenbindung verfügen bereits über das schwache Ereignis Muster, das in der Implementierung der Ereignisse angewendet wird.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>So implementieren Sie das schwache Ereignis Muster  
 Es gibt drei Möglichkeiten, ein schwaches Ereignis Muster zu implementieren. In der folgenden Tabelle werden die drei Ansätze aufgelistet und eine Anleitung für die Verwendung der einzelnen Methoden bereitstellt.  
  
|Ansatz|Zeitpunkt der Implementierung|  
|--------------|-----------------------|  
|Vorhandene schwache Ereignis-Manager-Klasse verwenden|Wenn das Ereignis, das Sie abonnieren möchten, über ein entsprechendes Ereignis verfügt <xref:System.Windows.WeakEventManager> , verwenden Sie den vorhandenen schwachen Ereignis-Manager. Eine Liste der in WPF enthaltenen schwachen Ereignis-Manager finden Sie in der Vererbungs Hierarchie in der- <xref:System.Windows.WeakEventManager> Klasse. Da die enthaltenen schwachen Ereignis-Manager eingeschränkt sind, müssen Sie wahrscheinlich einen der anderen Ansätze auswählen.|  
|Verwenden einer generischen Weak EventManager-Klasse|Verwenden Sie einen generischen <xref:System.Windows.WeakEventManager%602> , wenn eine vorhandene <xref:System.Windows.WeakEventManager> nicht verfügbar ist, Sie möchten eine einfache Implementierung durchführen und sich keine Gedanken um die Effizienz machen. Der generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als ein vorhandener oder benutzerdefinierter schwacher Ereignis-Manager. Die generische Klasse führt z. b. mehr Reflektion aus, um das Ereignis anhand des Ereignis namens zu ermitteln. Außerdem ist der Code zum Registrieren des Ereignisses mithilfe der generischen-Methode <xref:System.Windows.WeakEventManager%602> ausführlicher als die Verwendung eines vorhandenen oder benutzerdefinierten <xref:System.Windows.WeakEventManager> .|  
|Erstellen einer benutzerdefinierten Weak EventManager-Klasse|Erstellen Sie eine benutzerdefinierte, <xref:System.Windows.WeakEventManager> Wenn eine vorhandene <xref:System.Windows.WeakEventManager> nicht verfügbar ist und Sie die beste Effizienz erzielen möchten. Die Verwendung eines benutzerdefinierten <xref:System.Windows.WeakEventManager> zum Abonnieren eines Ereignisses ist effizienter, aber Sie verursachen die Kosten für das Schreiben von mehr Code am Anfang.|  
|Verwenden eines schwachen Ereignis-Managers von Drittanbietern|Nuget verfügt über [mehrere schwache Ereignis-Manager](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) , und viele WPF-Frameworks unterstützen auch das-Muster (z.b. [in der Prism-Dokumentation zu locker verknüpften Ereignis Abonnements](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).|

 In den folgenden Abschnitten wird beschrieben, wie das schwache Ereignis Muster implementiert wird.  Im Rahmen dieser Erläuterung weist das Ereignis, das abonniert werden soll, die folgenden Eigenschaften auf.  
  
- Der Ereignis Name ist `SomeEvent` .  
  
- Das-Ereignis wird von der- `EventSource` Klasse ausgelöst.  
  
- Der Ereignishandler weist den Typ auf: `SomeEventEventHandler` (oder `EventHandler<SomeEventEventArgs>` ).  
  
- Das-Ereignis übergibt einen Parameter vom Typ `SomeEventEventArgs` an die Ereignishandler.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Verwenden einer vorhandenen Weak Event Manager-Klasse  
  
1. Suchen Sie einen vorhandenen schwachen Ereignis-Manager.  
  
     Eine Liste der in WPF enthaltenen schwachen Ereignis-Manager finden Sie in der Vererbungs Hierarchie in der- <xref:System.Windows.WeakEventManager> Klasse.  
  
2. Verwenden Sie den neuen schwachen Ereignis-Manager anstelle der normalen Ereignis Einbindung.  
  
     Wenn Ihr Code z. b. das folgende Muster verwendet, um ein Ereignis zu abonnieren:  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie den Wert in das folgende Muster:  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Ebenso, wenn Ihr Code das folgende Muster verwendet, um ein Ereignis abzubestellen:  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie den Wert in das folgende Muster:  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Verwenden der generischen Weak Event Manager-Klasse  
  
1. Verwenden Sie die generische- <xref:System.Windows.WeakEventManager%602> Klasse anstelle der normalen Ereignis Einbindung.  
  
     Wenn Sie <xref:System.Windows.WeakEventManager%602> zum Registrieren von Ereignislistenern verwenden, geben Sie die Ereignis Quelle und den Typ <xref:System.EventArgs> als Typparameter für die Klasse an, und geben Sie an, <xref:System.Windows.WeakEventManager%602.AddHandler%2A> wie im folgenden Code gezeigt:  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Erstellen einer benutzerdefinierten Weak Event Manager-Klasse  
  
1. Kopieren Sie die folgende Klassen Vorlage in Ihr Projekt.  
  
     Diese Klasse erbt von der- <xref:System.Windows.WeakEventManager> Klasse.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. Ersetzen `SomeEventWeakEventManager` Sie den Namen durch ihren eigenen Namen.  
  
3. Ersetzen Sie die drei zuvor beschriebenen Namen durch die entsprechenden Namen für das Ereignis. ( `SomeEvent` , `EventSource` und `SomeEventEventArgs` )  
  
4. Legen Sie die Sichtbarkeit (Public/Internal/private) der Weak EventManager-Klasse auf die gleiche Sichtbarkeit wie das Ereignis fest, das Sie verwaltet.  
  
5. Verwenden Sie den neuen schwachen Ereignis-Manager anstelle der normalen Ereignis Einbindung.  
  
     Wenn Ihr Code z. b. das folgende Muster verwendet, um ein Ereignis zu abonnieren:  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie den Wert in das folgende Muster:  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Ebenso, wenn Ihr Code das folgende Muster verwendet, um ein Ereignis abzubestellen:  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie den Wert in das folgende Muster:  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
