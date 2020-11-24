---
title: Indizierte Auflistungen
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
ms.openlocfilehash: 637ba9b3b73d685ee2263315a08f982d862efb35
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827723"
---
# <a name="induced-collections"></a>Indizierte Auflistungen
In den meisten Fällen können Sie es dem Garbage Collector überlassen, den am besten geeigneten Zeitpunkt für eine Collection zu bestimmen. In seltenen Fällen kann das Erzwingen einer Auflistung jedoch die Leistung der Anwendung erhöhen. In diesen Fällen können Sie die Garbage Collection auslösen, indem Sie die <xref:System.GC.Collect%2A?displayProperty=nameWithType>-Methode zum Erzwingen einer Garbage Collection wählen.  
  
 Verwenden Sie die <xref:System.GC.Collect%2A?displayProperty=nameWithType>-Methode, wenn es zu einem bestimmten Zeitpunkt während der Ausführung des Anwendungscodes zu einer erheblichen Reduzierung des verwendeten Arbeitsspeichers kommt. Wenn die Anwendung zum Beispiel ein kompliziertes Dialogfeld mit mehreren Steuerelementen verwendet, kann der Aufruf von <xref:System.GC.Collect%2A> beim Schließen des Dialogfelds die Leistung erhöhen, indem der vom Dialogfeld verwendete Speicher sofort freigegeben wird. Stellen Sie sicher, dass die Anwendung nicht zu häufig eine Garbage Collection durchführt, das sich dies negativ auf die Leistung auswirken kann, wenn der Garbage Collector vergeblich versucht, Objekte zu ungünstigen Zeitpunkten freizugeben. Sie können einen <xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType>-Enumerationswert an die <xref:System.GC.Collect%2A>-Methode liefern, um nur zu sammeln, wenn die Auflistung produktiv ist, wie im nächsten Abschnitt erläutert wird.  
  
## <a name="gc-collection-mode"></a>Der GC-Sammlungsmodus  
 Sie können eine der <xref:System.GC.Collect%2A?displayProperty=nameWithType>-Methodenüberladungen verwenden, die einen <xref:System.GCCollectionMode>-Wert enthält, um das Verhalten einer erzwungenen Auflistung wie folgt zu bestimmen.  
  
|`GCCollectionMode` -Wert|Beschreibung|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|Verwendet die standardmäßige Garbage Collection-Einstellung für die ausgeführte .NET-Version.|  
|<xref:System.GCCollectionMode.Forced>|Erzwingt die sofortige Durchführung der Garbage Collection. Dies entspricht dem Aufruf der <xref:System.GC.Collect?displayProperty=nameWithType>-Überladung. Dies führt zu einer vollständigen blockierenden Auflistung aller Generationen.<br /><br /> Sie können auch das große Objektheap komprimieren, indem Sie die <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>-Eigenschaft auf <xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType> festlegen, bevor Sie eine unmittelbare vollständige blockierende Garbage Collection erzwingen.|  
|<xref:System.GCCollectionMode.Optimized>|Ermöglicht dem Garbage Collector zu bestimmten, oder der aktuelle Zeitpunkt zum Freigeben von Objekten optimal ist.<br /><br /> Der Garbage Collector kann ermitteln, dass eine Auflistung nicht produktiv genug wäre. In diesem Fall kehrt er zurück, ohne Objekte freizugeben.|  
  
## <a name="background-or-blocking-collections"></a>Hintergrund oder blockierende Auflistungen  
 Sie können die <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType>-Methodenüberladung aufrufen, um anzugeben, ob eine ausgelöste Auflistung blockiert wird oder nicht. Der Typ der ausgeführten Auflistung hängt von einer Kombination der `mode` und `blocking`-Parameter der Methode ab. Der Wert `mode` ist ein Member der <xref:System.GCCollectionMode>-Enumeration und `blocking` ist ein <xref:System.Boolean>-Wert. In der folgenden Tabelle wird die Interaktion der Argumente `mode` und `blocking` zusammengefasst.  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> oder <xref:System.GCCollectionMode.Default>|Eine blockierende Auflistung wird so schnell wie möglich ausgeführt. Wenn eine Hintergrundauflistung ausgeführt wird und die Generation 0 oder 1 ist, löst die <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29>-Methode sofort eine blockierende Auflistung aus und wird zurückgegeben, wenn die Auflistung abgeschlossen ist. Wenn eine Hintergrundauflistung ausgeführt wird und der `generation`-Parameter 2 ist, wartet die Methode, bis die Hintergrundauflistung beendet ist, löst eine blockierende Auflistung der Generation 2 aus und gibt dann zurück.|Eine Auflistung wird so schnell wie möglich ausgeführt. Die <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29>-Methode fordert eine Hintergrundauflistung, ist jedoch nicht garantiert. Je nach den Umständen wird eine blockierende Auflistung möglicherweise weiterhin ausgeführt. Wenn eine Hintergrundauflistung bereits ausgeführt wird, gibt die Methode sofort zurück.|  
|<xref:System.GCCollectionMode.Optimized>|Eine blockierende Auflistung kann ausgeführt werden, je nach Zustand des Garbage Collectors und des `generation`-Parameters. Der Garbage Collector versucht, eine optimale Leistung bereitzustellen.|Eine Auflistung kann ausgeführt werden, je nach Zustand des Garbage Collectors. Die <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29>-Methode fordert eine Hintergrundauflistung, ist jedoch nicht garantiert. Je nach den Umständen wird eine blockierende Auflistung möglicherweise weiterhin ausgeführt. Der Garbage Collector versucht, eine optimale Leistung bereitzustellen. Wenn eine Hintergrundauflistung bereits ausgeführt wird, gibt die Methode sofort zurück.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Latenzmodi](latency.md)
- [Garbage Collection](index.md)
