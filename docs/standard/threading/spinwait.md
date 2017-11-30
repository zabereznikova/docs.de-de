---
title: SpinWait
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType>ist ein einfacher Synchronisierungstyp, den Sie in der Low-Level-Szenarien verwenden können, um zu vermeiden, die teure Kontextwechsel und Kernelübergänge, die für Kernelereignisse erforderlich sind. Multicore-Computer Wenn eine Ressource nicht erwartungsgemäß für längere Zeit aufrechterhalten werden kann es effizienter sein für einen wartenden Thread im Benutzermodus für ein paar Dutzend oder wenigen Hundert Zyklen zu starten, und wiederholen Sie dann zum Abrufen der Ressourcenanbieters. Wenn die Ressource nach Spinvorgänge verfügbar ist, haben Sie mehrere Tausend Zyklen gespeichert. Wenn die Ressource immer noch nicht verfügbar ist, dann haben nur wenige Zyklen verbracht und weiterhin eine kernelbasierten Wartevorgangs eingeben. Diese Kombination Spinvorgänge dann wartenden wird manchmal als bezeichnet eine *zweiphasigen "Wait"-Vorgang*.  
  
 <xref:System.Threading.SpinWait>Dient in Verbindung mit .NET Framework-Typen verwendet werden, die Kernelereignisse, z. B. umschließen <xref:System.Threading.ManualResetEvent>. <xref:System.Threading.SpinWait>kann auch eigenständig für grundlegende Spinvorgänge-Funktionalität in nur einem Programm verwendet werden.  
  
 <xref:System.Threading.SpinWait>ist mehr als nur eine leere Schleife an. Wird sorgfältig implementiert, um die richtige Spinvorgänge Verhalten für die allgemeine Groß-/Kleinschreibung bereitzustellen, und selbst gestartet Kontextwechsel vorkommen, wenn es einen ausreichend langen Zeitraum stößt (ungefähr die Zeitdauer für einen Kernelübergang erforderlich). Z. B. auf Single-Core-Computer <xref:System.Threading.SpinWait> ergibt die Zeitscheibe des Threads sofort verwendet werden, da sich drehenden Blöcke Status für alle Threads weiterleiten. <xref:System.Threading.SpinWait>sogar auf einem Computer mit mehreren Kernen, um zu verhindern, dass den wartende Thread blockierende Threads mit höherer Priorität oder den Garbage Collector auch ergibt. Aus diesem Grund bei Verwendung einer <xref:System.Threading.SpinWait> in einem Vorgang Wartevorgängen wird empfohlen, dass Sie die Kernel-Wartezeit vor dem Aufrufen der <xref:System.Threading.SpinWait> selbst einen Kontextwechsel initiiert. <xref:System.Threading.SpinWait>Stellt die <xref:System.Threading.SpinWait.NextSpinWillYield%2A> -Eigenschaft, die Sie, bevor jedem Aufruf von überprüfen können <xref:System.Threading.SpinWait.SpinOnce%2A>. Wenn die Eigenschaft zurückgibt `true`, eigene "Wait"-Vorgang zu initiieren. Ein Beispiel finden Sie unter [Vorgehensweise: SpinWait verwenden, um einen zwei-Phasen-Vorgang warten implementieren](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Wenn Sie eine zwei-Phasen "Wait"-Vorgang nicht ausführen, aber einfach drehen sind, bis eine Bedingung wahr ist, können Sie aktivieren <xref:System.Threading.SpinWait> auszuführenden seines Kontexts wechselt, damit es eine gute Bürger in der Windows-Umgebung ist. Das folgende grundlegende Beispiel zeigt eine <xref:System.Threading.SpinWait> in einem Stapel sperrenfreie. Wenn Sie einen hohe Leistung, threadsicheren Stapel benötigen, erwägen Sie <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
