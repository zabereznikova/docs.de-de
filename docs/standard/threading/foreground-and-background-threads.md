---
title: Vordergrund- und Hintergrundthreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a>Vordergrund- und Hintergrundthreads
Ein verwalteter Thread ist ein Hintergrundthread oder ein Vordergrundthread. Hintergrundthreads sind identisch mit Vordergrundthreads mit einer Ausnahme: ein Hintergrundthread ist nicht möglich, die verwaltete ausführungsumgebung ausgeführt wird. Sobald alle Vordergrundthreads, in einem verwalteten Prozess (wobei die .exe-Datei für eine verwaltete Assembly ist) beendet wurde, wird das System beendet alle Hintergrundthreads ausgeführt und beendet wird.  
  
> [!NOTE]
>  Wenn die Common Language Runtime einen Hintergrundthread beendet wird, da der Prozess heruntergefahren wird, wird keine Ausnahme im Thread ausgelöst. Allerdings der Wenn-Threads beendet werden, da die <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> Methode entladen die Anwendungsdomäne eine <xref:System.Threading.ThreadAbortException> im Vordergrund-und Hintergrundthreads ausgelöst wird.  
  
 Verwenden der <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> Eigenschaft, um zu bestimmen, ob ein Thread einen Hintergrund oder ein Vordergrundthread ist, oder auf deren Status zu ändern. Ein Thread kann geändert werden in einen Hintergrundthread jederzeit durch Festlegen seiner <xref:System.Threading.Thread.IsBackground%2A> Eigenschaft `true`.  
  
> [!IMPORTANT]
>  Der Status Vorder- oder Hintergrund für einen Thread, wirkt sich nicht auf das Ergebnis einer nicht behandelten Ausnahme im Thread aus. In .NET Framework, Version 2.0 führt eine nicht behandelte Ausnahme im Vorder- oder Hintergrund Threads bei Beendigung der Anwendung. Finden Sie unter [Ausnahmen in verwalteten Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Threads, die auf dem verwalteten Threadpool gehört (d. h., threads, deren <xref:System.Threading.Thread.IsThreadPoolThread%2A> Eigenschaft `true`) sind Hintergrundthreads. Alle Threads, die die verwaltete ausführungsumgebung von nicht verwaltetem Code eingeben, werden als Hintergrundthreads markiert. Alle Threads, die durch Erstellen und Starten eines neuen generiert <xref:System.Threading.Thread> Objekt sind standardmäßig Vordergrundthreads.  
  
 Festlegen, wenn Sie einen Thread verwenden, um eine Aktivität, z. B. eine Socketverbindung überwachen seine <xref:System.Threading.Thread.IsBackground%2A> Eigenschaft `true` so, dass der Thread verhindert nicht, den Prozess beendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
