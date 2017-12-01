---
title: "Gründe für das Implementieren des ereignisbasierten asynchronen Musters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Gründe für das Implementieren des ereignisbasierten asynchronen Musters
Das ereignisbasierte asynchrone Muster stellt ein Muster zum Verfügbarmachen von asynchronem Verhalten einer Klasse. Mit der Einführung dieses Muster der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] definiert zwei Muster zum Verfügbarmachen von asynchronem Verhalten: das asynchrone Muster basierend auf der <xref:System.IAsyncResult?displayProperty=nameWithType> Schnittstelle und das ereignisbasierte Muster. In diesem Thema wird beschrieben, wenn für beide Muster implementieren geeignet ist.  
  
 Weitere Informationen zur asynchronen Programmierung mit der <xref:System.IAsyncResult> Benutzeroberfläche, siehe [das ereignisbasierte asynchrone Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## <a name="general-principles"></a>Allgemeine Prinzipien  
 Im Allgemeinen sollten Sie asynchrone Funktionen, die das ereignisbasierte asynchrone Muster nach Möglichkeit verfügbar machen. Es gibt jedoch einige Anforderungen, die das ereignisbasierte Muster nicht erfüllen. In diesen Fällen müssen Sie möglicherweise zum Implementieren der <xref:System.IAsyncResult> Muster zusätzlich zu den ereignisbasierten Muster.  
  
> [!NOTE]
>  Es ist nur in wenigen Fällen die <xref:System.IAsyncResult> Muster implementiert werden, ohne das ereignisbasierte Muster ebenfalls implementiert wird.  
  
## <a name="guidelines"></a>Richtlinien  
 Die folgende Liste beschreibt die Richtlinien für, wenn Sie das ereignisbasierte asynchrone Muster implementieren soll:  
  
-   Verwenden Sie das ereignisbasierte Muster als Standard-API, um asynchrones Verhalten für die Klasse verfügbar zu machen.  
  
-   Machen Sie nicht die <xref:System.IAsyncResult> Muster, wenn die Klasse in einer Clientanwendung, z. B. Windows Forms in erster Linie verwendet wird.  
  
-   Nur verfügbar zu machen die <xref:System.IAsyncResult> Muster bei Bedarf für Ihre Anforderungen erfüllt. Z. B. Kompatibilität mit einer vorhandenen API müssen Sie möglicherweise verfügbar machen die <xref:System.IAsyncResult> Muster.  
  
-   Machen Sie nicht die <xref:System.IAsyncResult> -Muster nur zusammen mit die ereignisbasierten Muster.  
  
-   Wenn Sie verfügbar machen, müssen die <xref:System.IAsyncResult> Muster, holen Sie dies als eine erweiterte Option. Beispielsweise ein Proxyobjekt zu generieren, generieren die ereignisbasierte standardmäßig mit einer Option zum Generieren der <xref:System.IAsyncResult> Muster.  
  
-   Ihre Implementierung ereignisbasierte Muster als Grundlage Ihrer <xref:System.IAsyncResult> Muster-Implementierung.  
  
-   Vermeiden Sie die Muster ereignisbasierten verfügbar zu machen und die <xref:System.IAsyncResult> Muster für die gleiche Klasse. Verfügbar machen das ereignisbasierte Muster für Klassen "höherer Ebene" und die <xref:System.IAsyncResult> Muster Klassen auf "niedrigerer Ebene". Vergleichen Sie das ereignisbasierte Muster z. B. auf die <xref:System.Net.WebClient> Komponente mit dem die <xref:System.IAsyncResult> Muster auf der <xref:System.Web.HttpRequest> Klasse.  
  
    -   Verfügbar machen das ereignisbasierte Muster und die <xref:System.IAsyncResult> Muster in der gleichen Klasse, wenn Kompatibilität erforderlich ist. Wenn Sie bereits eine API freigegeben haben, verwendet z. B. die <xref:System.IAsyncResult> Muster, müssten Sie die beibehalten werden sollen die <xref:System.IAsyncResult> Muster für die Abwärtskompatibilität.  
  
    -   Verfügbar machen das ereignisbasierte Muster und die <xref:System.IAsyncResult> in der gleichen Klasse Muster, wenn das resultierende Objekt Modell Komplexität den Vorteil, dass die Implementierungen trennen überwiegt. Es ist besser, beide Muster für eine einzelne Klasse als zu vermeiden, zu machen das ereignisbasierte Muster verfügbar zu machen.  
  
    -   Wenn Sie sowohl das ereignisbasierte Muster verfügbar machen müssen und <xref:System.IAsyncResult> Muster für eine einzelne Klasse, verwenden <xref:System.ComponentModel.EditorBrowsableAttribute> festgelegt <xref:System.ComponentModel.EditorBrowsableState.Advanced> zum Kennzeichnen der <xref:System.IAsyncResult> Muster Implementierung als erweiterte Funktion. Dies weist darauf hin, entwurfsumgebungen, wie z. B. [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, nicht zum Anzeigen der <xref:System.IAsyncResult> Eigenschaften und Methoden. Diese Eigenschaften und Methoden sind weiterhin voll verwendbar, aber der Entwickler mit IntelliSense arbeiten hat eine genauere Ansicht der API.  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Kriterien für das Verfügbarmachen von IAsyncResult-Muster, zusätzlich zu den ereignisbasierten Muster  
 Während das ereignisbasierte asynchrone Muster in den zuvor erwähnten Szenarios viele Vorteile hat, verfügt diese noch einige Nachteile, über die Sie berücksichtigen sollten, wenn Leistung Ihren Anforderungen am wichtigsten ist.  
  
 Es gibt drei Szenarien, die das ereignisbasierte Muster nicht berücksichtigt wird, sowie die <xref:System.IAsyncResult> Muster:  
  
-   Warten Sie auf einem blockieren<xref:System.IAsyncResult>  
  
-   Blockieren des Wartevorgang für viele <xref:System.IAsyncResult> Objekte  
  
-   Abrufen der Beendigung der<xref:System.IAsyncResult>  
  
 Sie können diese Szenarien unter Verwendung des ereignisbasierten Musters adressieren, aber auf diese Weise ist komplizierter als die Verwendung der <xref:System.IAsyncResult> Muster.  
  
 Entwickler verwenden häufig die <xref:System.IAsyncResult> Muster für Dienste, die in der Regel sehr hohe leistungsanforderungen verfügen. Dem Abruf für Abschluss Szenario ist beispielsweise eine Technik Hochleistungs-Server.  
  
 Darüber hinaus das ereignisbasierte Muster ist weniger effizient als die <xref:System.IAsyncResult> Muster, da mehrere Objekte, insbesondere erstellt <xref:System.EventArgs>, und da threadübergreifend synchronisiert.  
  
 Die folgende Liste enthält einige Empfehlungen ausführen, wenn Sie möchten, verwenden Sie die <xref:System.IAsyncResult> Muster:  
  
-   Nur verfügbar zu machen die <xref:System.IAsyncResult> Muster, wenn Sie ausdrücklich Unterstützung für benötigen <xref:System.Threading.WaitHandle> oder <xref:System.IAsyncResult> Objekte.  
  
-   Nur verfügbar zu machen die <xref:System.IAsyncResult> Muster, wenn Sie eine vorhandene API haben, verwendet die <xref:System.IAsyncResult> Muster.  
  
-   Haben eine vorhandene API basierend auf den <xref:System.IAsyncResult> Muster, sollten Sie auch das ereignisbasierte Muster in der nächsten Version verfügbar zu machen.  
  
-   Nur verfügbar zu machen <xref:System.IAsyncResult> Muster, wenn Sie hohe leistungsanforderungen haben Sie überprüft haben kann nicht mit dem ereignisbasierten Muster erfüllt sein, aber erfüllt werden können, indem die <xref:System.IAsyncResult> Muster.  
  
## <a name="see-also"></a>Siehe auch  
 [Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern (Exemplarische Vorgehensweise: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt)](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
