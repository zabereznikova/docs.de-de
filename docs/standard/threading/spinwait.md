---
title: SpinWait
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
ms.openlocfilehash: fb70697fd14f9f8734ca1a7896fc06c6bca5a71d
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188925"
---
# <a name="spinwait"></a>SpinWait

<xref:System.Threading.SpinWait?displayProperty=nameWithType> ist ein einfacher Synchronisierungstyp, den Sie in Szenarien auf niedriger Ebene verwenden können, um die aufwändigen Kontextwechsel und Kernelübergänge zu vermeiden, die für Kernelereignisse erforderlich sind. Wenn bei Computern mit mehreren Kernen nicht erwartet wird, dass eine Ressource für längere Zeit beibehalten wird, kann es effizienter sein, wenn ein wartender Thread für ein paar Dutzend oder Hundert Zyklen im Benutzermodus rotiert und dann versucht wird, die Ressource zu erlangen. Wenn die Ressource nach den Spinvorgängen verfügbar ist, haben Sie mehrere Tausend Zyklen gespeichert. Wenn die Ressource immer noch nicht verfügbar ist, haben Sie nur wenige Zyklen verbraucht und können weiterhin in einen kernelbasierten Wartevorgang eintreten. Diese Kombination aus Spin- und Wartevorgang wird manchmal als *zweiphasiger Wartevorgang* bezeichnet.  
  
 <xref:System.Threading.SpinWait> soll in Verbindung mit .NET-Typen verwendet werden, die Kernelereignisse wie <xref:System.Threading.ManualResetEvent> umschließen. <xref:System.Threading.SpinWait> kann auch eigenständig für grundlegende Spinfunktionalität in nur einem Programm verwendet werden.  
  
 <xref:System.Threading.SpinWait> ist mehr als nur eine leere Schleife. Es ist sorgfältig implementiert, um das richtige Spinverhalten für den Allgemeinfall bereitzustellen, und initiiert selbst Kontextwechsel, wenn es ausreichend lange rotiert hat (ungefähr der für einen Kernelübergang erforderliche Zeitraum). Auf Einzelkerncomputern erzeugt <xref:System.Threading.SpinWait> z.B. sofort das Zeitsegment des Threads, da sich drehende Blöcke den Status an alle Threads weiterleiten. <xref:System.Threading.SpinWait> erzeugt sie ebenfalls, sogar auf Computern mit mehreren Kernen, um zu verhindern, dass der wartende Thread Threads mit höherer Priorität oder den Garbage Collector blockiert. Aus diesem Grund sollten Sie bei Verwendung von <xref:System.Threading.SpinWait> in einem zweiphasigen Wartevorgang die Kernelwartezeit aufrufen, bevor <xref:System.Threading.SpinWait> selbst einen Kontextwechsel initiiert. <xref:System.Threading.SpinWait> stellt die <xref:System.Threading.SpinWait.NextSpinWillYield%2A>-Eigenschaft bereit, die Sie vor jedem Aufruf von <xref:System.Threading.SpinWait.SpinOnce%2A> überprüfen können. Wenn die Eigenschaft `true` zurückgibt, initiieren Sie Ihren eigenen Wartevorgang. Ein Beispiel finden Sie unter [Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait](how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Wenn Sie keinen zweiphasigen Wartevorgang ausführen, sondern einfach Schleifendurchläufe, bis eine Bedingung wahr ist, können Sie <xref:System.Threading.SpinWait> aktivieren, um dessen Kontextwechsel auszuführen, damit es ein „guter Bürger“ in der Windows-Betriebssystemumgebung ist. Das folgende grundlegende Beispiel zeigt ein <xref:System.Threading.SpinWait> in einem sperrenfreien Stapel. Wenn Sie einen threadsicheren Stapel mit hoher Leistung benötigen, ziehen Sie <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType> in Betracht.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Thread.SpinWait%2A>
- [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)
