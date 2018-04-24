---
title: Ereignisbasiertes asynchrones Muster (EAP)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 20
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fecd71355d53f1e3937d3724569b10fa0c8e50da
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="event-based-asynchronous-pattern-eap"></a>Ereignisbasiertes asynchrones Muster (EAP)
Es gibt verschiedene Möglichkeiten, asynchrone Funktionen für Clientcode verfügbar zu machen. Das ereignisbasierte asynchrone Muster gibt Klassen ein Verfahren zum Präsentieren von asynchronem Verhalten vor.  
  
> [!NOTE]
>  Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellt die Task Parallel Library ein neues Modell für die asynchrone und parallele Programmierung bereit. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../../../docs/standard/parallel-programming/index.md).  
  
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
  
## <a name="reference"></a>Referenz  
 <xref:System.ComponentModel.AsyncOperation>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperation>-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Beschreibt die <xref:System.ComponentModel.BackgroundWorker>-Komponente und enthält Links zu allen Membern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Beschreibt ein Programmiermodell für asynchrone und parallele Vorgänge.  
  
 [Threading](../../../docs/standard/threading/index.md)  
 Beschreibt Multithreadingfunktionen in .NET Framework.  
  
 [Threading](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 Beschreibt Multithreading-Funktionen in den Programmiersprachen C# und Visual Basic.  
  
## <a name="see-also"></a>Siehe auch  
 [Empfohlene Vorgehensweise für das verwaltete Threading](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Ereignisse](../../../docs/standard/events/index.md)  
 [Multithreading in Komponenten](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [Asynchronous Programming Design Patterns (Entwurfsmuster für die asynchrone Programmierung)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
