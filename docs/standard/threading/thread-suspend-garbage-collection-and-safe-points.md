---
title: Thread.Suspend, Garbage Collection und Sicherungspunkte
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc3af01167fe97b701bdb0c7bc37af02d8e8a77c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004178"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, Garbage Collection und Sicherungspunkte
Beim Aufruf von <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> in einem Thread hält das System fest, dass eine Threadunterbrechung angefordert wurde, und ermöglicht vor dem Unterbrechen des Threads dessen Ausführung bis zu einem sicheren Punkt. Ein sicherer Punkt für einen Thread ist ein Punkt in seiner Ausführung, an dem eine Garbage Collection durchgeführt werden kann.  
  
 Sobald ein sicherer Punkt erreicht ist, garantiert die Runtime, dass der unterbrochene Thread in verwaltetem Code nicht weiter fortgesetzt wird. Ein außerhalb von verwaltetem Code ausgeführter Thread ist stets sicher für die Garbage Collection, und dessen Ausführung wird fortgeführt, bis er versucht, die Ausführung von verwaltetem Code fortzusetzen.  
  
> [!NOTE]
>  Um eine Garbage Collection auszuführen, muss die Runtime alle Threads mit Ausnahme des Threads, der die Collection durchführt, unterbrechen. Jeder Thread muss an einen sicheren Punkt gebracht werden, bevor er unterbrochen werden kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Thread>  
- <xref:System.GC>  
- [Threading](../../../docs/standard/threading/index.md)  
- [Automatische Speicherverwaltung](../../../docs/standard/automatic-memory-management.md)
