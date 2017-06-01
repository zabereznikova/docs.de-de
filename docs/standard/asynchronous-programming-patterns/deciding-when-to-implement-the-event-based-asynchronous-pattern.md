---
title: "Deciding When to Implement the Event-based Asynchronous Pattern | Microsoft Docs"
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
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "AsyncOperation class"
  - "AsyncCompletedEventArgs class"
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Deciding When to Implement the Event-based Asynchronous Pattern
Das ereignisbasierte asynchrone Muster stellt ein Muster bereit, mit dem das asynchrone Verhalten einer Klasse verfügbar gemacht werden kann.  Mit diesem Muster definiert [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zwei Muster zum Verfügmachen des asynchronen Verhaltens: das auf der <xref:System.IAsyncResult?displayProperty=fullName>\-Schnittstelle beruhende asynchrone Muster und das ereignisbasierte Muster.  In diesem Thema werden Gründe für die Implementierung beider Muster erläutert.  
  
 Weitere Informationen über asynchrone Programmierung mit der <xref:System.IAsyncResult>\-Schnittstelle finden Sie unter [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## Allgemeine Prinzipien  
 Asynchrone Features sollten nach Möglichkeit mit dem ereignisbasierten asynchronen Muster verfügbar gemacht werden.  Das ereignisbasierte Muster kann einige Anforderungen jedoch nicht erfüllen.  In diesen Fällen müssen Sie möglicherweise neben dem ereignisbasierten Muster auch das <xref:System.IAsyncResult>\-Muster implementieren.  
  
> [!NOTE]
>  Das <xref:System.IAsyncResult>\-Muster wird nur selten ohne das ereignisbasierte Muster implementiert.  
  
## Richtlinien  
 In der folgenden Liste werden Richtlinien für die Implementierung des ereignisbasierten asynchronen Musters beschrieben:  
  
-   Verwenden Sie das ereignisbasierte Muster als Standard\-API, um asynchrones Verhalten für die Klasse verfügbar zu machen.  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster nicht verfügbar, wenn die Klasse in erster Linie in einer Clientanwendung wie Windows Forms verwendet wird.  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster nur verfügbar, wenn es im Rahmen ihrer Arbeit notwendig ist.  So müssen Sie das <xref:System.IAsyncResult>\-Muster möglicherweise aus Gründen der Kompatibilität mit einer vorhandenen API verfügbar machen.  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster nur zusammen mit dem ereignisbasierten Muster verfügbar.  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster, wenn es verfügbar gemacht werden muss, als erweiterte Option verfügbar.  Wenn Sie z. B. ein Proxyobjekt generieren, generieren Sie standardmäßig das ereignisbasierte Muster mit der Option, das <xref:System.IAsyncResult>\-Muster zu generieren.  
  
-   Erstellen Sie die Implementierung des ereignisbasierten Musters auf der Grundlage der Implementierung des <xref:System.IAsyncResult> Musters.  
  
-   Machen Sie das ereignisbasierte Muster und das <xref:System.IAsyncResult>\-Muster nach Möglichkeit nicht für die gleiche Klasse verfügbar.  Machen Sie das ereignisbasierte Muster für Klassen auf "höherer Ebene" und das <xref:System.IAsyncResult>\-Muster für Klassen auf "niedrigerer Ebene" verfügbar.  Vergleichen Sie z. B. das ereignisbasierte Muster für die <xref:System.Net.WebClient>\-Komponente mit dem <xref:System.IAsyncResult>\-Muster für die <xref:System.Web.HttpRequest>\-Klasse.  
  
    -   Machen Sie das ereignisbasierte Muster und das <xref:System.IAsyncResult>\-Muster für die gleiche Klasse verfügbar, wenn dies aus Gründen der Kompatibilität erforderlich ist.  Wenn Sie z. B. eine API freigegeben haben, die das <xref:System.IAsyncResult>\-Muster verwendet, müssten Sie das <xref:System.IAsyncResult>\-Muster aus Gründen der Abwärtskompatibilität beibehalten.  
  
    -   Machen Sie das ereignisbasierte Muster und das <xref:System.IAsyncResult>\-Muster für die gleiche Klasse verfügbar, wenn das resultierende komplexe Objektmodell die Vorteile getrennter Implementierungen überwiegt.  Es ist besser, beide Muster für die gleiche Klasse verfügbar zu machen, als das ereignisbasierte Muster nicht verfügbar zu machen.  
  
    -   Wenn Sie sowohl das ereignisbasierte als auch das <xref:System.IAsyncResult>\-Muster für die gleiche Klasse verfügbar machen müssen, kennzeichnen Sie die Implementierung des <xref:System.IAsyncResult>\-Musters mit dem auf <xref:System.ComponentModel.EditorBrowsableState> festgelegte <xref:System.ComponentModel.EditorBrowsableAttribute> als erweitertes Feature.  In der Entwurfsumgebung, z. B. in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, werden dann die Eigenschaften und Methoden von <xref:System.IAsyncResult> nicht angezeigt.  Diese Eigenschaften und Methoden können weiterhin vollständig eingesetzt ein, lassen Entwickler, die mit IntelliSense arbeiten, die API jedoch deutlicher erkennen.  
  
## Kriterien für das Verfügbarmachen des IAsyncResult\-Musters als Ergänzung des ereignisbasierten Musters  
 Das ereignisbasierte asynchrone Muster bietet in den besprochenen Situationen viele Vorteile. Es geht jedoch auch mit einigen Nachteilen einher, die Ihnen bekannt sein sollten, wenn Sie großen Wert auf Leistung legen.  
  
 Es gibt drei Situationen, in denen sich das ereignisbasierte Muster weniger gut als das <xref:System.IAsyncResult> eignet:  
  
-   Blockieren des Wartevorgang für ein <xref:System.IAsyncResult>  
  
-   Blockieren des Wartevorgang für mehrere <xref:System.IAsyncResult>\-Objekte  
  
-   Abrufen der Beendigung des <xref:System.IAsyncResult>  
  
 Sie können das ereignisbasierte Muster in diesen Fällen zwar einsetzen, es ist jedoch umständlicher als das <xref:System.IAsyncResult>\-Muster.  
  
 Entwickler verwenden das <xref:System.IAsyncResult>\-Muster häufig für Dienste mit besonders hohen Leistungsanforderungen.  Das Abrufen der Beendigung ist beispielsweise ein äußerst leistungsintensiver Vorgang auf dem Server.  
  
 Das ereignisbasierte Muster ist zudem nicht so effektiv wie das <xref:System.IAsyncResult>\-Muster, da es mehr Objekte \(insbesondere <xref:System.EventArgs>\) erstellt und threadübergreifend synchronisiert.  
  
 In der folgenden Liste sind einige Empfehlungen aufgeführt, die Sie bei der Verwendung des <xref:System.IAsyncResult>\-Musters einhalten sollten:  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster nur verfügbar, wenn Sie ausdrücklich Unterstützung für <xref:System.Threading.WaitHandle>\-Objekte oder <xref:System.IAsyncResult>\-Objekte benötigen.  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster nur verfügbar, wenn Sie über eine API verfügen, die das <xref:System.IAsyncResult>\-Muster verwendet.  
  
-   Wenn Sie über eine auf dem <xref:System.IAsyncResult>\-Muster basierende API verfügen, empfiehlt es sich, in der nächsten Version auch das ereignisbasierte Muster verfügbar zu machen.  
  
-   Machen Sie das <xref:System.IAsyncResult>\-Muster nur verfügbar, wenn hohe Leistungsanforderungen bestehen, die Sie sich nachgewiesenermaßen nicht mit dem ereignisbasierten Muster, jedoch mit dem <xref:System.IAsyncResult>\-Muster erfüllen lassen.  
  
## Siehe auch  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)   
 [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)