---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a>SpinLock
Die <xref:System.Threading.SpinLock> Struktur ist eine auf niedriger Ebene, die gegenseitigen Ausschluss Synchronisierungsprimitive, die stößt, während er darauf wartet, eine Sperre abzurufen. Auf Mehrkerncomputern Wartezeiten kurz, und wenn Konflikte minimal, ist zu erwarten sind <xref:System.Threading.SpinLock> bieten eine bessere Leistung als andere Arten von Sperren. Wir empfehlen jedoch die Verwendung <xref:System.Threading.SpinLock> nur wenn Sie bestimmen, indem die profilerstellung, die die <xref:System.Threading.Monitor?displayProperty=nameWithType> Methode oder die <xref:System.Threading.Interlocked> Methoden sind erheblich verlangsamt die Leistung des Programms.  
  
 <xref:System.Threading.SpinLock>die Zeitscheibe des Threads kann erhalten, selbst wenn er noch nicht auf die Sperre abgerufen wurde. Dies geschieht Threadpriorität zu vermeiden und die Garbage collection Fortschritte zu aktivieren. Bei Verwendung einer <xref:System.Threading.SpinLock>, stellen Sie sicher, dass kein Thread die Sperre für mehr als einen sehr kurzen Zeitraum aufnehmen kann, und kein Thread blockieren kann, während er die Sperre besitzt.  
  
 Da SpinLock ein Werttyp ist, müssen Sie explizit übergeben als Verweis, wenn Sie, die beiden Kopien zum Verweisen auf die gleiche Sperre beabsichtigen.  
  
 Weitere Informationen zur Verwendung dieses Typs finden Sie unter <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Ein Beispiel finden Sie unter [wie: Verwenden von SpinLock für die Synchronisierung auf niedriger Ebene](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock>unterstützt eine *Thread*-*nachverfolgen* Modus, in dem Sie verfolgen, den Thread, der die Sperre zu einem bestimmten Zeitpunkt während der Entwicklungsphase verwenden können. Modus zum Nachverfolgen von Threads ist sehr nützlich für das Debuggen, aber es wird empfohlen, dass Sie in der Releaseversion des Programms deaktivieren, da es die Leistung beeinträchtigen kann. Weitere Informationen finden Sie unter [How to: Enable Thread-Tracking-Modus in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
