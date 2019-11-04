---
title: Latenzmodi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, intrusiveness
- garbage collection, latency modes
ms.assetid: 96278bb7-6eab-4612-8594-ceebfc887d81
ms.openlocfilehash: 8833c88c3221c0a375011eb62dd712340f7e89cd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120905"
---
# <a name="latency-modes"></a>Latenzmodi
Zum Freigeben von Objekten muss der Garbage Collector alle ausgeführten Threads einer Anwendung beenden. In einigen Situationen, z. B. wenn eine Anwendung Daten abruft oder Inhalte anzeigt, kann eine vollständige Garbage Collection zu einem kritischen Zeitpunkt erfolgen und die Leistung beeinträchtigen. Sie können das Ausmaß der Garbage Collection anpassen, indem Sie die <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=nameWithType>-Eigenschaft auf einen der <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>-Werte festlegen.  
  
 Der Begriff Latenz bezieht sich auf die Zeit, während der der Garbage Collector in die Anwendung eingreift. In Zeiten mit geringer Latenz verhält sich der Garbage Collector bei der Freigabe von Objekten zurückhaltender und weniger intrusiv. Die <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>-Enumeration bietet zwei Einstellungen mit geringer Latenz:  
  
- <xref:System.Runtime.GCLatencyMode.LowLatency> unterdrückt Garbage Collections der Generation 2 und führt nur Garbage Collections der Generationen 0 und 1 aus. Diese Einstellung kann nur für kurze Zeiträume verwendet werden. Über längere Zeiträume (und wenn auf dem System nicht genügend Arbeitsspeicher vorhanden ist) löst der Garbage Collector eine Auflistung aus, die die Anwendung kurz anhalten und einen zeitkritischen Vorgang unterbrechen kann. Diese Einstellung ist nur für die Garbage Collection auf Arbeitsstationen verfügbar.  
  
- <xref:System.Runtime.GCLatencyMode.SustainedLowLatency> unterdrückt Garbage Collections der Generation 2 im Vordergrund und führt nur Garbage Collections der Generationen 0 und 1 sowie Garbage Collections der Generation 2 im Hintergrund aus. Diese Einstellung kann für längere Zeiträume verwendet werden und ist für die Garbage Collection für die Arbeitsstation und für die Garbage Collection auf dem Server verfügbar. Diese Einstellung kann nicht verwendet werden, wenn die [gleichzeitige Garbage Collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) deaktiviert ist.  
  
 In Zeiten mit geringer Latenz werden Garbage Collections der Generation 2 unterdrückt, außer wenn Folgendes geschieht:  
  
- Das System erhält vom Betriebssystem eine Benachrichtigung über unzureichenden Arbeitsspeicher.  
  
- Der Anwendungscode initiiert eine Garbage Collection, indem die <xref:System.GC.Collect%2A?displayProperty=nameWithType>-Methode aufgerufen und für den `generation`-Parameter der Wert "2" angegeben wird.  
  
 In der folgenden Tabelle werden die Anwendungsszenarien für die Verwendung der <xref:System.Runtime.GCLatencyMode>-Werte aufgeführt.  
  
|Latenzmodus|Anwendungsszenarien|  
|------------------|---------------------------|  
|<xref:System.Runtime.GCLatencyMode.Batch>|Für Anwendungen ohne Benutzeroberfläche oder serverseitige Vorgänge.<br /><br /> Dies ist der Standardmodus, wenn die [gleichzeitige Garbage Collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) deaktiviert ist.|  
|<xref:System.Runtime.GCLatencyMode.Interactive>|Für die meisten Anwendungen, die über eine Benutzeroberfläche verfügen.<br /><br /> Dies ist der Standardmodus, wenn die [gleichzeitige Garbage Collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) aktiviert ist.|  
|<xref:System.Runtime.GCLatencyMode.LowLatency>|Für Anwendungen mit kurzen, zeitkritischen Vorgängen, bei denen Unterbrechungen durch den Garbage Collector störend sein könnten. Hierzu gehören beispielsweise Anwendungen, die Animationsrendering- oder Datenerfassungsfunktionen ausführen.|  
|<xref:System.Runtime.GCLatencyMode.SustainedLowLatency>|Für Anwendungen mit zeitkritischen Vorgängen über einen möglicherweise längeren Zeitraum, bei denen Unterbrechungen durch den Garbage Collector störend sein könnten. Hierzu gehören beispielsweise Anwendungen, die schnelle Antwortzeiten bei Marktdatenänderungen während der Geschäftszeit erfordern.<br /><br /> Dieser Modus führt im Vergleich zu anderen Modi zu einem größeren verwalteten Heap. Da der verwaltete Heap nicht komprimiert wird, ist eine stärkere Fragmentierung möglich. Stellen Sie sicher, dass genügend Arbeitsspeicher verfügbar ist.|  
  
## <a name="guidelines-for-using-low-latency"></a>Richtlinien für die Verwendung von geringer Latenz  
 Beachten Sie beim Verwenden des <xref:System.Runtime.GCLatencyMode.LowLatency>-Modus die folgenden Richtlinien:  
  
- Halten Sie die Zeiten mit geringer Latenz möglichst kurz.  
  
- Vermeiden Sie es, in Zeiten mit geringer Latenz große Speichermengen zu belegen. Benachrichtigungen über unzureichenden Arbeitsspeicher können ausgegeben werden, wenn die Garbage Collection weniger Objekte freigibt.  
  
- Minimieren Sie im Modus für geringe Latenz die Anzahl der Zuordnungen, insbesondere Zuordnungen für den großen Objektheap und fixierte Objekte.  
  
- Achten Sie auf potenziell zuordnende Threads. Weil die Einstellung der <xref:System.Runtime.GCSettings.LatencyMode%2A>-Eigenschaft prozessweit gültig ist, könnte für jeden potenziell zuordnenden Thread eine <xref:System.OutOfMemoryException> ausgelöst werden.  
  
- Umschließen Sie den Code mit geringer Latenz in eingeschränkten Ausführungsbereichen (weitere Informationen finden Sie unter [Eingeschränkte Ausführungsbereiche](../../../docs/framework/performance/constrained-execution-regions.md)).  
  
- Sie können Garbage Collections der Generation 2 in Zeiten mit geringer Latenz erzwingen, indem Sie die <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=nameWithType>-Methode aufrufen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.GC?displayProperty=nameWithType>
- [Induzierte Sammlungen](../../../docs/standard/garbage-collection/induced.md)
- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
