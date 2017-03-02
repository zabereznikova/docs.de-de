---
title: Latenzmodi
description: Latenzmodi
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 810bd8be-5a48-42c6-b080-3afdb31fc61b
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 1d99ac95527cae80b74c96f5a2e6be81b94176c5
ms.lasthandoff: 03/02/2017

---

# <a name="latency-modes"></a>Latenzmodi

Zum Freigeben von Objekten muss der Garbage Collector alle ausgeführten Threads einer Anwendung beenden. In einigen Situationen, z. B. wenn eine Anwendung Daten abruft oder Inhalte anzeigt, kann eine vollständige Garbage Collection zu einem kritischen Zeitpunkt erfolgen und die Leistung beeinträchtigen. Sie können das Ausmaß der Garbage Collection anpassen, indem Sie die [GCSettings.LatencyMode](xref:System.Runtime.GCSettings.LatencyMode)-Eigenschaft auf einen der [System.Runtime.GCLatencyMode](xref:System.Runtime.GCLatencyMode)-Werte festlegen. 

Der Begriff Latenz bezieht sich auf die Zeit, während der der Garbage Collector in die Anwendung eingreift. In Zeiten mit geringer Latenz verhält sich der Garbage Collector bei der Freigabe von Objekten zurückhaltender und weniger intrusiv. Die [System.Runtime.GCLatencyMode](xref:System.Runtime.GCLatencyMode)-Enumeration bietet zwei Einstellungen für geringe Latenz:

* [LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) unterdrückt Sammlungen der Generation 2 und führt nur Sammlungen der Generationen 0 und 1 aus. Diese Einstellung kann nur für kurze Zeiträume verwendet werden. Über längere Zeiträume (und wenn auf dem System nicht genügend Arbeitsspeicher vorhanden ist) löst der Garbage Collector eine Auflistung aus, die die Anwendung kurz anhalten und einen zeitkritischen Vorgang unterbrechen kann. Diese Einstellung ist nur für die Garbage Collection auf Arbeitsstationen verfügbar. 

* [SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) unterdrückt Sammlungen der Generation 2 im Vordergrund und führt nur Sammlungen der Generationen 0 und 1 sowie Sammlungen der Generation 2 im Hintergrund aus. Diese Einstellung kann für längere Zeiträume verwendet werden und ist für die Garbage Collection für die Arbeitsstation und für die Garbage Collection auf dem Server verfügbar. Diese Einstellung kann nicht verwendet werden, wenn die [gleichzeitige Garbage Collection](https://msdn.microsoft.com/library/yhwwzef8.aspx) deaktiviert ist.

In Zeiten mit geringer Latenz werden Garbage Collections der Generation 2 unterdrückt, außer wenn Folgendes geschieht:

* Das System erhält vom Betriebssystem eine Benachrichtigung über unzureichenden Arbeitsspeicher.

* Der Anwendungscode initiiert eine Sammlung, indem die [GC.Collect](xref:System.GC.Collect(System.Int32))-Methode aufgerufen und für den Generationsparameter der Wert „2“ angegeben wird.

In der folgenden Tabelle werden die Anwendungsszenarios für die Verwendung der [GCLatencyMode](xref:System.Runtime.GCLatencyMode)-Werte aufgeführt.

Latenzmodus | Anwendungsszenarien
------------ | --------------------- 
[Batch](xref:System.Runtime.GCLatencyMode.Batch) | Für Anwendungen ohne Benutzeroberfläche oder serverseitige Vorgänge. Dies ist der Standardmodus, wenn die [gleichzeitige Garbage Collection](https://msdn.microsoft.com/library/yhwwzef8.aspx) deaktiviert ist.
[Interactive](xref:System.Runtime.GCLatencyMode.Interactive) | Für die meisten Anwendungen, die über eine Benutzeroberfläche verfügen. Für Anwendungen ohne Benutzeroberfläche oder serverseitige Vorgänge. Dies ist der Standardmodus, wenn die [gleichzeitige Garbage Collection](https://msdn.microsoft.com/library/yhwwzef8.aspx) aktiviert ist.
[LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) | Für Anwendungen mit kurzen, zeitkritischen Vorgängen, bei denen Unterbrechungen durch den Garbage Collector störend sein könnten. Hierzu gehören beispielsweise Anwendungen, die Animationsrendering- oder Datenerfassungsfunktionen ausführen.
[SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) | Für Anwendungen mit zeitkritischen Vorgängen über einen möglicherweise längeren Zeitraum, bei denen Unterbrechungen durch den Garbage Collector störend sein könnten. Hierzu gehören beispielsweise Anwendungen, die schnelle Antwortzeiten bei Marktdatenänderungen während der Geschäftszeit erfordern.   Dieser Modus führt im Vergleich zu anderen Modi zu einem größeren verwalteten Heap. Da der verwaltete Heap nicht komprimiert wird, ist eine stärkere Fragmentierung möglich. Stellen Sie sicher, dass genügend Arbeitsspeicher verfügbar ist.
 
## <a name="guidelines-for-using-low-latency"></a>Richtlinien für die Verwendung von geringer Latenz

Beachten Sie beim Verwenden des [LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency)-Modus die folgenden Richtlinien:

* Halten Sie die Zeiten mit geringer Latenz möglichst kurz.

* Vermeiden Sie es, in Zeiten mit geringer Latenz große Speichermengen zu belegen. Benachrichtigungen über unzureichenden Arbeitsspeicher können ausgegeben werden, wenn die Garbage Collection weniger Objekte freigibt. 

* Minimieren Sie im Modus für geringe Latenz die Anzahl der Zuordnungen, insbesondere Zuordnungen für den großen Objektheap und fixierte Objekte. 

* Achten Sie auf potenziell zuordnende Threads. Weil die Einstellung der [LatencyMode](xref:System.Runtime.GCSettings.LatencyMode)-Eigenschaft prozessweit gültig ist, könnten Sie für jeden potenziell zuordnenden Thread eine [OutOfMemoryException](xref:System.OutOfMemoryException) generieren. 

* Sie können Sammlungen der Generation 2 in Zeiten mit geringer Latenz erzwingen, indem Sie die Methode [GC.Collect(Int32, GCCollectionMode)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode)) aufrufen.

## <a name="see-also"></a>Siehe auch

[System.GC](xref:System.GC)

[Induzierte Sammlungen](induced.md)

[Garbage Collection in .NET](index.md)

