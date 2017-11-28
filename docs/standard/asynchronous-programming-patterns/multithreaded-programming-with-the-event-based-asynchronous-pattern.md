---
title: Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster
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
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a26f6750f68609b40e6917fc5b257e43d95c3c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a>Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster
Es gibt verschiedene Möglichkeiten, asynchrone Funktionen für Clientcode verfügbar zu machen. Das ereignisbasierte asynchrone Muster gibt Klassen das empfohlene Verfahren zum Präsentieren von asynchronem Verhalten vor.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Beschreibt, wie das ereignisbasierte asynchrone Muster die Vorteile von Multithreadanwendungen bietet und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.  
  
 [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Beschreibt das standardisierte Verfahren zum Verpacken einer Klasse, die über asynchrone Funktionen verfügt.  
  
 [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Beschreibt die Anforderungen, die zum Verfügbarmachen asynchroner Funktionen nach dem ereignisbasierten asynchronen Muster erfüllt sein müssen.  
  
 [Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Beschreibt, wie Sie ermitteln, ob Sie das ereignisbasierte asynchrone Muster anstelle des <xref:System.IAsyncResult>-Musters implementieren sollen.  
  
 [Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern (Exemplarische Vorgehensweise: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt)](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Veranschaulicht das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert. Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet.  
  
 [How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Beschreibt die Verwendung einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt.  
  
## <a name="reference"></a>Verweis  
 <xref:System.ComponentModel.AsyncOperation>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperation>-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Beschreibt die <xref:System.ComponentModel.BackgroundWorker>-Komponente und enthält Links zu allen Membern.  
  
## <a name="see-also"></a>Siehe auch  
 [Empfohlene Vorgehensweise für das verwaltete Threading](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Ereignisse](../../../docs/standard/events/index.md)  
 [Multithreading in Komponenten](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
