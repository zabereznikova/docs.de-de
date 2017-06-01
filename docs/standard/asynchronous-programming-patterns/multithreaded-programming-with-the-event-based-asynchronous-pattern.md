---
title: "Multithreaded Programming with the Event-based Asynchronous Pattern | Microsoft Docs"
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
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "AsyncCompletedEventArgs class"
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Multithreaded Programming with the Event-based Asynchronous Pattern
Es gibt verschiedene Möglichkeiten, asynchrone Features für Clientcode verfügbar zu machen.  Das ereignisbasierte asynchrone Muster gibt Klassen das empfohlene Verfahren zum Präsentieren von asynchronem Verhalten vor.  
  
## In diesem Abschnitt  
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Beschreibt, wie das ereignisbasierte asynchrone Muster die Vorteile von Multithreadanwendungen bietet und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.  
  
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Beschreibt das standardisierte Verfahren zum Verpacken einer Klasse, die über asynchrone Features verfügt.  
  
 [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Beschreibt die Anforderungen, die zum Verfügbarmachen asynchroner Features nach dem ereignisbasierten asynchronen Muster erfüllt sein müssen.  
  
 [Deciding When to Implement the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Beschreibt, wie Sie ermitteln, ob Sie das ereignisbasierte asynchrone Muster anstelle des <xref:System.IAsyncResult>\-Musters implementieren sollen.  
  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Veranschaulicht das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert.  Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=fullName>\-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet.  
  
 [How to: Use Components That Support the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Beschreibt die Verwendung einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt.  
  
## Referenz  
 <xref:System.ComponentModel.AsyncOperation>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperation>\-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>\-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Beschreibt die <xref:System.ComponentModel.BackgroundWorker>\-Komponente und enthält Links zu allen Membern.  
  
## Siehe auch  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)   
 [Ereignisse](../../../docs/standard/events/index.md)   
 [Multithreading in Components](../Topic/Multithreading%20in%20Components.md)   
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)