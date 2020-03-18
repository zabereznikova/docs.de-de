---
title: Latenzmodi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, intrusiveness
- garbage collection, latency modes
ms.assetid: 96278bb7-6eab-4612-8594-ceebfc887d81
ms.openlocfilehash: a8eaf0c80aa32978eead80c51a905cbcd66a537b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74283596"
---
# <a name="latency-modes"></a>Latenzmodi

Zum Freigeben von Objekten muss der Garbage Collector (GC) alle ausgeführten Threads einer Anwendung beenden. Der Zeitraum, in dem der Garbage Collector aktiv ist, wird als dessen *Latenz* bezeichnet.

In einigen Situationen, z. B. wenn eine Anwendung Daten abruft oder Inhalte anzeigt, kann eine vollständige Garbage Collection zu einem kritischen Zeitpunkt erfolgen und die Leistung beeinträchtigen. Sie können das Ausmaß der Garbage Collection anpassen, indem Sie die <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=nameWithType>-Eigenschaft auf einen der <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>-Werte festlegen.

## <a name="low-latency-settings"></a>Einstellungen mit geringer Latenz

Die Verwendung einer Einstellung mit "geringer" Latenz bedeutet, dass der Garbage Collector weniger in Ihre Anwendung eindringt. Die Garbage Collection ist bei der Freigabe von Arbeitsspeicher eher konservativ.

Die <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>-Enumeration bietet zwei Einstellungen mit geringer Latenz:

- [GCLatencyMode.LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) unterdrückt Garbage Collections der 2. Generation und führt nur Garbage Collctions der Generationen 0 und 1 durch. Diese Einstellung kann nur für kurze Zeiträume verwendet werden. Über längere Zeiträume (und wenn auf dem System nicht genügend Arbeitsspeicher vorhanden ist) löst der Garbage Collector eine Auflistung aus, die die Anwendung kurz anhalten und einen zeitkritischen Vorgang unterbrechen kann. Diese Einstellung ist nur für die Garbage Collection auf Arbeitsstationen verfügbar.

- [GCLatencyMode.SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) unterdrückt Garbage Collections der 2. Generation im Vordergrund und führt nur Garbage Collections der Generationen 0 und 1 sowie Collections der Generation 2 im Hintergrund aus. Diese Einstellung kann für längere Zeiträume verwendet werden und ist für die Garbage Collection für die Arbeitsstation und für die Garbage Collection auf dem Server verfügbar. Diese Einstellung kann nicht verwendet werden, wenn die Garbage Collection im Hintergrund deaktiviert ist.

In Zeiten mit geringer Latenz werden Garbage Collections der Generation 2 unterdrückt, außer wenn Folgendes geschieht:

- Das System erhält vom Betriebssystem eine Benachrichtigung über unzureichenden Arbeitsspeicher.

- Der Anwendungscode initiiert eine Garbage Collection, indem die <xref:System.GC.Collect%2A?displayProperty=nameWithType>-Methode aufgerufen und für den `generation`-Parameter der Wert "2" angegeben wird.

## <a name="scenarios"></a>Szenarien

In der folgenden Tabelle werden die Anwendungsszenarien für die Verwendung der <xref:System.Runtime.GCLatencyMode>-Werte aufgeführt:

|Latenzmodus|Anwendungsszenarien|
|------------------|---------------------------|
|<xref:System.Runtime.GCLatencyMode.Batch>|Für Anwendungen ohne Benutzeroberfläche (UI) oder serverseitige Vorgänge.<br /><br />Wenn Garbage Collection im Hintergrund deaktiviert ist, ist dies der Standardmodus für die Garbage Collection auf Arbeitsstationen und Servern. Der <xref:System.Runtime.GCLatencyMode.Batch>-Modus setzt außerdem die [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)-Einstellung außer Kraft, d.h., er verhindert parallele oder im Hintergrund ausgeführte Garbage Collection.|
|<xref:System.Runtime.GCLatencyMode.Interactive>|Für die meisten Anwendungen, die über eine Benutzeroberfläche verfügen.<br /><br />Dies ist der Standardmodus für die Garbage Collection auf Arbeitsstationen und Servern. Wenn jedoch eine App gehostet ist, haben die Einstellungen des Hostprozesses für die Garbage Collection Vorrang.|
|<xref:System.Runtime.GCLatencyMode.LowLatency>|Für Anwendungen mit kurzen, zeitkritischen Vorgängen, bei denen Unterbrechungen durch den Garbage Collector störend sein könnten. Hierzu gehören beispielsweise Anwendungen, die Animationsrendering oder Datenerfassungsfunktionen ausführen.|
|<xref:System.Runtime.GCLatencyMode.SustainedLowLatency>|Für Anwendungen mit zeitkritischen Vorgängen über einen möglicherweise längeren Zeitraum, bei denen Unterbrechungen durch den Garbage Collector störend sein könnten. Hierzu gehören beispielsweise Anwendungen, die schnelle Antwortzeiten bei Marktdatenänderungen während der Geschäftszeit erfordern.<br /><br />Dieser Modus führt im Vergleich zu anderen Modi zu einem größeren verwalteten Heap. Da der verwaltete Heap nicht komprimiert wird, ist eine stärkere Fragmentierung möglich. Stellen Sie sicher, dass genügend Arbeitsspeicher verfügbar ist.|

## <a name="guidelines-for-using-low-latency"></a>Richtlinien für die Verwendung von geringer Latenz

Beachten Sie beim Verwenden des [GCLatencyMode.LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency)-Modus die folgenden Richtlinien:

- Halten Sie die Zeiten mit geringer Latenz möglichst kurz.

- Vermeiden Sie es, in Zeiten mit geringer Latenz große Speichermengen zu belegen. Benachrichtigungen über unzureichenden Arbeitsspeicher können ausgegeben werden, wenn die Garbage Collection weniger Objekte freigibt.

- Minimieren Sie im Modus für geringe Latenz die Anzahl neuer Zuordnungen, insbesondere Zuordnungen für den großen Objektheap und fixierte Objekte.

- Achten Sie auf potenziell zuordnende Threads. Weil die Einstellung der <xref:System.Runtime.GCSettings.LatencyMode%2A>-Eigenschaft prozessweit gültig ist, können in jedem zuordnenden Thread <xref:System.OutOfMemoryException>-Ausnahmen generiert werden.

- Umschließen (wrappen) Sie den Code für geringe Latenz in eingeschränkten Ausführungsbereichen. Weitere Informationen finden Sie unter [Eingeschränkte Ausführungsbereiche](../../../docs/framework/performance/constrained-execution-regions.md).

- Sie können Garbage Collections der Generation 2 in Zeiten mit geringer Latenz erzwingen, indem Sie die <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=nameWithType>-Methode aufrufen.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.GC?displayProperty=nameWithType>
- [Induzierte Sammlungen](../../../docs/standard/garbage-collection/induced.md)
- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
