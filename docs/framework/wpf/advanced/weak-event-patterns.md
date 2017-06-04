---
title: "Schwache Ereignismuster | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ereignishandler, Schwaches Ereignismuster"
  - "IWeakEventListener-Schnittstelle"
  - "Implementierung von schwachen Ereignismustern"
  - "WeakEventManager-Klasse"
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Schwache Ereignismuster
In Anwendungen ist es möglich, dass an Ereignisquellen angehängte Handler in Abstimmung mit dem Listenerobjekt, das den Handler an die Quelle angehängt hat, nicht zerstört werden.  Diese Situation kann zu Speicherverlusten führen.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] führt ein bestimmtes Entwurfsmuster ein, das zum Behandeln dieses Problems eingesetzt werden kann. Hierbei wird eine dedizierte Managerklasse für bestimmte Ereignisse bereitgestellt und eine Schnittstelle auf dem Listener für dieses Ereignis implementiert.  Dieses Entwurfsmuster wird als *schwaches Ereignismuster* bezeichnet.  
  
## Gründe zum Implementieren schwacher Ereignismuster  
 Das Überwachen von Ereignissen kann zu Speicherverlusten führen.  Die normalerweise verwendete Methode zum Überwachen eines Ereignisses besteht in der Verwendung der sprachspezifischen Syntax, mit der ein Handler an ein Ereignis in einer Quelle angehängt wird.  In [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] lautet diese Syntax beispielsweise: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Mit dieser Methode wird ein starker Verweis von der Ereignisquelle zum Ereignislistener erstellt.  Normalerweise führt das Anfügen eines Ereignishandlers für einen Listener dazu, dass der Listener eine Objektlebensdauer aufweist, die von der Objektlebensdauer der Quelle beeinflusst wird \(es sei denn, der Ereignishandler wird explizit entfernt\).  In bestimmten Situationen jedoch soll die Objektlebensdauer des Listeners möglicherweise von anderen Faktoren bestimmt werden, wie zum Beispiel der Tatsache, ob er zurzeit zur visuellen Struktur der Anwendung gehört, und nicht von der Lebensdauer der Quelle.  Immer dann, wenn die Objektlebensdauer der Quelle die Objektlebensdauer des Listeners überschreitet, führt das normale Ereignismuster zu einem Speicherverlust: Der Listener behält seine Gültigkeit länger als vorgesehen.  
  
 Das schwache Ereignismuster ist darauf ausgerichtet, dieses Speicherverlustproblem zu lösen.  Das schwache Ereignismuster kann immer dann verwendet werden, wenn sich ein Listener für ein Ereignis registrieren muss. Wann die Registrierung aufzuheben ist wird vom Listener allerdings nicht explizit erkannt.  Das schwache Ereignismuster kann auch verwendet werden, wenn die Objektlebensdauer der Quelle die nutzbare Objektlebensdauer des Listeners überschreitet.  \(In diesem Fall wird *nutzbar* von Ihnen bestimmt.\) Das schwache Ereignismuster ermöglicht dem Listener, sich für das Ereignis zu registrieren und es zu empfangen, ohne dass sich dies auf die Merkmale der Objektlebensdauer des Listeners auswirkt.  Der implizite Verweis der Quelle legt nicht fest, ob der Listener für die Garbage Collection freigegeben wird.  Der Verweis ist ein schwacher Verweis, woher die Bezeichnung schwaches Ereignismuster und die verwandten [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] rühren.  Für den Listener kann eine Garbage Collection durchgeführt werden, oder er kann auf andere Weise zerstört werden, wobei die Quelle weiterhin bestehen bleiben kann, ohne dass Handlerverweise, die nicht aufgelistet werden können, auf das jetzt zerstörte Objekt beibehalten werden.  
  
## Wer sollte das schwache Ereignismuster implementieren?  
 Das Implementieren des schwachen Ereignismusters ist in erster Linie für Autoren von Steuerelementen interessant.  Der Steuerelementautor ist im Großen und Ganzen für das Verhalten und die Kapselung des Steuerelements sowie für die Auswirkungen verantwortlich, die das Element auf die Anwendung hat, in die es eingefügt wird.  Dies schließt das Objektlebensdauer\-Verhalten des Steuerelements ein, insbesondere die Behandlung des beschriebenen Speicherverlustproblems.  
  
 Bestimmte Szenarien sind grundsätzlich zur Anwendung des schwachen Ereignismusters sehr gut geeignet.  Ein solches Szenario ist z. B. die Datenbindung.  Bei der Datenbindung ist das Quellobjekt im Allgemein vollkommen unabhängig vom Listenerobjekt, das ein Ziel einer Bindung ist.  In zahlreichen Aspekten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Datenbindung wird das schwache Ereignismuster bereits durch die Implementierung der Ereignisse angewendet.  
  
## So implementieren Sie das schwache Ereignismuster  
 Es gibt drei Möglichkeiten, schwaches Ereignismuster implementieren.  In der folgenden Tabelle werden die drei Ansätze für einige und stellt Anleitungen für bereit, wenn Sie jedes verwenden sollten.  
  
|Vorgehensweise|Wann implementiert|  
|--------------------|------------------------|  
|Verwenden Sie eine vorhandene schwache Ereignis\-Manager class|Wenn das Ereignis, durch den Sie abonnieren möchten, entsprechendes <xref:System.Windows.WeakEventManager>, verwenden den vorhandenen schwachen Ereignis\-Manager festgelegt ist.  Eine Liste mit schwachen Ereignis managern, die mit WPF enthalten sind, finden Sie in der Vererbungshierarchie der <xref:System.Windows.WeakEventManager>\-Klasse.  Beachten Sie jedoch, dass er relativ wenige schwache Ereignis\-Manager vorhanden ist, die mit WPF enthalten sind. Daher müssen Sie möglicherweise einen der anderen Ansätze wählen.|  
|Verwenden Sie eine generische Klasse Ereignis\-Manager schwache|Verwenden Sie generisches <xref:System.Windows.WeakEventManager%602> , wenn vorhandenes <xref:System.Windows.WeakEventManager> nicht verfügbar ist, Sie möchten eine einfache Weise zu implementieren, und Sie über die Effizienz sind nicht betroffen.  Generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als eine vorhandene oder ein schwacher benutzerdefinierter Ereignis\-Manager.  Zum Beispiel hat die generische Klasse mehr Reflektion, um das angegebene Ereignis aus der Name des Ereignisses.  Außerdem wird der Code, um das Ereignis, indem er generische <xref:System.Windows.WeakEventManager%602> zu registrieren, ist ausführlicher als mit einem vorhandenen oder benutzerdefinierten <xref:System.Windows.WeakEventManager>.|  
|Erstellen Sie eine benutzerdefinierte schwache Ereignis\-Manager class|Erstellen Sie ein benutzerdefiniertes <xref:System.Windows.WeakEventManager> , wenn Sie vorhandenen <xref:System.Windows.WeakEventManager> nicht verfügbar sind und Sie die optimale Effizienz soll.  Verwenden einer benutzerdefinierten <xref:System.Windows.WeakEventManager> , ein Ereignis abonniert ist jedoch effizienter, führen Sie die Kosten für mehr Code am Anfang schreiben.|  
  
 In den folgenden Abschnitten wird beschrieben, wie das schwache Ereignismuster implementieren.  Damit dieser Diskussion enthält das Ereignis abonniert werden die folgenden Eigenschaften.  
  
-   Der Ereignisname ist `SomeEvent`.  
  
-   Das Ereignis wird von der `EventSource`\-Klasse ausgelöst.  
  
-   Der Ereignishandler Typ: `SomeEventEventHandler` \(oder `EventHandler<SomeEventEventArgs>`\).  
  
-   Das Ereignis führt einen Parameter vom Typ `SomeEventEventArgs` an Ereignishandler.  
  
### Verwenden einer vorhandenen schwachen Ereignis\-Manager\-Klasse  
  
1.  Suchen Sie einen vorhandenen schwachen Ereignis\-Manager.  
  
     Eine Liste mit schwachen Ereignis managern, die mit WPF enthalten sind, finden Sie in der Vererbungshierarchie der <xref:System.Windows.WeakEventManager>\-Klasse.  
  
2.  Verwenden Sie den neuen schwachen Ereignis\-Manager anstelle des normalen Ereignis anschlusses.  
  
     Wenn beispielsweise der Code das folgende Muster verwendet, um ein Ereignis zu abonnieren:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie diese dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Auch wenn der Code das folgende Muster verwendet, um ein Ereignis zu kündigen:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie diese dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### Verwenden von generischen Ereignis\-Manager\-Klasse schwachen  
  
1.  Verwenden Sie die generische <xref:System.Windows.WeakEventManager%602>\-Klasse anstelle des normalen Ereignisanschlusses.  
  
     Wenn Sie <xref:System.Windows.WeakEventManager%602> verwenden, um Ereignislistener zu registrieren, führen Sie die Ereignisquelle und den <xref:System.EventArgs>\-Typ als Typparameter auf die Klasse, und rufen <xref:System.Windows.WeakEventManager%602.AddHandler%2A> wie im folgenden Code gezeigt:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### Eine benutzerdefinierte schwache Ereignis\-Manager\-Klasse erstellen  
  
1.  Kopieren Sie die folgende Vorlage Klasse zum Projekt.  
  
     Diese Klasse erbt von der <xref:System.Windows.WeakEventManager>\-Klasse.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  Ersetzen Sie den `SomeEventWeakEventManager` Namen mit dem eigenen Namen des Ordners.  
  
3.  Ersetzen Sie die drei Namen, die zuvor mit der entsprechenden Namen für das Ereignis beschrieben werden.  \(`SomeEvent`, `EventSource`und `SomeEventEventArgs`\)  
  
4.  Legen Sie die Sichtbarkeit \(öffentlich\/intern\/privat\) der schwachen Ereignis\-Manager Klasse auf die gleiche Sichtbarkeit fest, die Ereignis er verwaltet.  
  
5.  Verwenden Sie den neuen schwachen Ereignis\-Manager anstelle des normalen Ereignis anschlusses.  
  
     Wenn beispielsweise der Code das folgende Muster verwendet, um ein Ereignis zu abonnieren:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Ändern Sie diese dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Auch wenn der Code das folgende Muster verwendet, um ein Ereignis zu kündigen:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Ändern Sie ihn dem folgenden Muster:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## Siehe auch  
 <xref:System.Windows.WeakEventManager>   
 <xref:System.Windows.IWeakEventListener>   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)