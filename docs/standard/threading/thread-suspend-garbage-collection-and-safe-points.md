---
title: "Thread.Suspend, Garbage Collection und Sicherungspunkte"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, Garbage Collection und Sicherungspunkte
Beim Aufruf <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> in einem Thread im System fest, dass eine Threadunterbrechung wurde angefordert, und dem Thread ermöglicht ausgeführt, bis er einem sicheren Zeitpunkt erreicht hat, vor dem Anhalten des Threads. Einem sicheren Zeitpunkt für einen Thread ist ein Verwaltungspunkt in seiner Ausführung Garbage Collection durchgeführt werden kann.  
  
 Nach einem sicheren Zeitpunkt erreicht wird, garantiert die Common Language Runtime an, dass der unterbrochene Thread in verwaltetem Code nicht weiteren fortgesetzt tätigt. Ein Thread für die Ausführung außerhalb von verwaltetem Code ist sicherer, für die Garbagecollection und dessen Ausführung wird fortgeführt, bis er versucht, die Ausführung von verwaltetem Code fortgesetzt werden.  
  
> [!NOTE]
>  Um eine Garbagecollection auszuführen, muss die Common Language Runtime alle Threads mit Ausnahme des Threads, die mit der Durchführung der Collection angehalten werden. Jeder Thread muss an einem sicheren Zeitpunkt gebracht werden, bevor es angehalten werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Automatische Speicherverwaltung](../../../docs/standard/automatic-memory-management.md)
