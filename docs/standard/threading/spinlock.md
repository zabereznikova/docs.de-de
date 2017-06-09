---
title: "SpinLock | Microsoft Docs"
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
  - "synchronization primitives, SpinLock"
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# SpinLock
Die <xref:System.Threading.SpinLock>\-Struktur ist ein Synchronisierungsgrundelement auf niedriger Ebene für den gegenseitigen Ausschluss, das einen Spin\-Vorgang ausführt, während es auf den Erhalt einer Sperre wartet.  Wenn Multicore\-Computer verwendet werden und Wartezeiten normalerweise kurz sind und nur wenige Konflikte auftreten, bietet <xref:System.Threading.SpinLock> eine bessere Leistung als andere Arten von Sperren.  Die Verwendung von <xref:System.Threading.SpinLock> ist jedoch nur zu empfehlen, wenn Sie mithilfe der Profilerstellung ermitteln, dass die <xref:System.Threading.Monitor?displayProperty=fullName>\-Methode oder die <xref:System.Threading.Interlocked>\-Methode die Leistung des Programms erheblich verlangsamt.  
  
 <xref:System.Threading.SpinLock> ergibt möglicherweise den Zeitanteil des Threads, auch wenn die Sperre noch nicht abgerufen wurde.  Auf diese Weise soll die Umkehrung der Threadpriorität verhindert und dem Garbage Collector ermöglicht werden, Fortschritte zu machen.  Stellen Sie beim Verwenden von <xref:System.Threading.SpinLock> sicher, dass kein Thread die Sperre für mehr als einen sehr kurzen Zeitraum besitzen kann und dass kein Thread während des Zeitraums blockieren kann.  
  
 Da SpinLock ein Werttyp ist, müssen Sie diesen explizit als Verweis übergeben, wenn die beiden Kopien auf dieselbe Sperre verweisen sollen.  
  
 Weitere Informationen zur Verwendung dieses Typs finden Sie unter <xref:System.Threading.SpinLock?displayProperty=fullName>.  Ein Beispiel finden Sie unter [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock> unterstützt einen Modus zum *Nachverfolgen von* *Threads*, den Sie während der Entwicklungsphase verwenden können, um den Thread nachzuverfolgen, der die Sperre zum jeweiligen Zeitpunkt besitzt.  Der Modus zum Nachverfolgen von Threads ist sehr hilfreich beim Debugging. Es wird jedoch empfohlen, dass Sie den Modus in der Releaseversion des Programms deaktivieren, weil sich dadurch die Leistung verschlechtern kann.  Weitere Informationen finden Sie unter [How to: Enable Thread\-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## Siehe auch  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)