---
title: Ereignisbasiertes asynchrones Muster (EAP)
description: Links zu Artikeln zu ereignisbasierten asynchronen Mustern (Event-based Asynchronous Pattern, EAP) in .NET, z. B. zur Implementierung, zu bewährten Methoden und zur Implementierung eines EAP-Clients
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 16aabeb55a56c63449a865d00044c463657de740
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888840"
---
# <a name="event-based-asynchronous-pattern-eap"></a>Ereignisbasiertes asynchrones Muster (EAP)

Es gibt verschiedene Möglichkeiten, asynchrone Funktionen für Clientcode verfügbar zu machen. Das ereignisbasierte asynchrone Muster gibt Klassen ein Verfahren zum Präsentieren von asynchronem Verhalten vor.  
  
> [!NOTE]
> Ab .NET Framework 4 stellt die Task Parallel Library ein neues Modell für die asynchrone und parallele Programmierung bereit. Weitere Informationen finden Sie unter [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) und [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster)](task-based-asynchronous-pattern-tap.md).
  
## <a name="in-this-section"></a>In diesem Abschnitt

 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](event-based-asynchronous-pattern-overview.md)  
 Beschreibt, wie das ereignisbasierte asynchrone Muster die Vorteile von Multithreadanwendungen bietet und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.  
  
 [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](implementing-the-event-based-asynchronous-pattern.md)  
 Beschreibt das standardisierte Verfahren zum Verpacken einer Klasse, die über asynchrone Funktionen verfügt.  
  
 [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Beschreibt die Anforderungen, die zum Verfügbarmachen asynchroner Funktionen nach dem ereignisbasierten asynchronen Muster erfüllt sein müssen.  
  
 [Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Beschreibt, wie Sie ermitteln, ob Sie das ereignisbasierte asynchrone Muster anstelle des <xref:System.IAsyncResult>-Musters implementieren sollen, das vom [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell)](asynchronous-programming-model-apm.md) dargestellt wird
  
 [How to: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen](component-that-supports-the-event-based-asynchronous-pattern.md)  
 Beschreibt das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert. Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet.  

 [How to: Implementieren eines Clients des ereignisbasierten asynchronen Musters](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 Beschreibt das Erstellen eines Clients, der das ereignisbasierte asynchrone Muster implementiert.
  
 [How to: How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Beschreibt die Verwendung einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt.  
  
## <a name="reference"></a>Referenz

 <xref:System.ComponentModel.AsyncOperation>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperation>-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>-Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Beschreibt die <xref:System.ComponentModel.BackgroundWorker>-Komponente und enthält Links zu allen Membern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte

 [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)  
 Beschreibt ein Programmiermodell für asynchrone und parallele Vorgänge.  
  
 [Threading](../threading/index.md)  
 Beschreibt Multithreadingfunktionen in .NET.  
  
## <a name="see-also"></a>Siehe auch

- [Empfohlene Vorgehensweise für das verwaltete Threading](../threading/managed-threading-best-practices.md)
- [Ereignisse](../events/index.md)
- [Asynchronous Programming Design Patterns (Entwurfsmuster für die asynchrone Programmierung)](index.md)
