---
title: Garbage Collection für .NET
description: Erfahren Sie mehr über die Garbage Collection in .NET. Der Garbage Collector von .NET verwaltet die Belegung und Freigabe von Arbeitsspeicher für die Anwendung.
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: 39b5bf62935054bd4b9be2d228cc42202aa89144
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063188"
---
# <a name="garbage-collection"></a>Garbage Collection

Der Garbage Collector von .NET verwaltet die Belegung und Freigabe von Arbeitsspeicher für die Anwendung. Bei jedem Erstellen eines neuen Objekts belegt die Common Language Runtime (CLR) Speicher für das Objekt aus dem verwalteten Heap. Solange ein Adressbereich im verwalteten Heap verfügbar ist, reserviert die Laufzeit Arbeitsspeicher für neue Objekte. Arbeitsspeicher ist jedoch nicht unendlich verfügbar. Möglicherweise muss mithilfe der Garbage Collection Arbeitsspeicher freigegeben werden. Die Optimierungs-Engine der Garbage Collection bestimmt den besten Zeitpunkt für das Einsammeln anhand der erfolgten Speicherbelegungen. Beim Einsammeln durch die Garbage Collection wird nach Objekten im verwalteten Heap gesucht, die nicht mehr von der Anwendung verwendet werden. Anschließend werden die für das Freigeben des Arbeitsspeichers erforderlichen Operationen ausgeführt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Grundlagen der Garbage Collection](fundamentals.md)|Beschreibt, wie die Garbage Collection funktioniert, wie Objekte auf dem verwalteten Heap zugeordnet werden und erläutert andere Kernkonzepte.|  
|[Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](workstation-server-gc.md)|Beschreibt die Unterschiede zwischen der Garbage Collection auf der Arbeitsstation für Client-Apps und der Garbage Collection auf dem Server für Server-Apps|
|[Garbage Collection im Hintergrund](background-gc.md)|Beschreibt die Garbage Collection im Hintergrund, bei der es sich um die Bereinigung von Objekten der Generationen 0 und 1 handelt, während die Bereinigung für Generation 2 ausgeführt wird|
|[Der Large-Object-Heap](large-object-heap.md)|Beschreibt den Large-Object-Heap (Large Object Heap, LOH) und die Garbage Collection für Large Objects|
|[Garbage Collection und Leistung](performance.md)|Beschreibt die Leistungsprüfungen, die Sie verwenden können, um Probleme mit der Garbage Collection oder der Leistung zu analysieren.|  
|[Indizierte Auflistungen](induced.md)|Beschreibt, wie eine Garbage Collection initiiert wird.|  
|[Latenzmodi](latency.md)|Beschreibt die Modi, die das Ausmaß der Garbage Collection bestimmen.|  
|[Optimierung für freigegebenes Webhosting](optimization-for-shared-web-hosting.md)|Beschreibt, wie die Garbage Collection auf Servern, die von mehreren kleinen Websites gemeinsam verwendet werden, optimiert werden kann.|  
|[Garbage-Collection-Benachrichtigungen](notifications.md)|Beschreibt, wie festgestellt werden kann, wann eine vollständige Garbage Collection ansteht und wann sie abgeschlossen ist.|  
|[Überwachung von Anwendungsdomänenressourcen](app-domain-resource-monitoring.md)|Beschreibt, wie die durch eine Anwendungsdomäne verursachte CPU- und Speicherauslastung überwacht wird.|  
|[Schwache Verweise](weak-references.md)|Beschreibt Funktionen, die dem Garbage Collector ermöglichen, ein Objekt zu sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann.|  
  
## <a name="reference"></a>Referenz

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Siehe auch

- [Bereinigen von nicht verwalteten Ressourcen](unmanaged.md)
