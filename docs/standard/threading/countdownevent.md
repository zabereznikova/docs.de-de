---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>ist eine Synchronisierungsprimitive, die der wartenden Threads Blockierung aufgehoben wird, nachdem es wurde eine bestimmte Anzahl von Malen signalisiert. <xref:System.Threading.CountdownEvent>eignet sich für Szenarien, in denen Sie andernfalls Sie verwenden müssen, eine <xref:System.Threading.ManualResetEvent> oder <xref:System.Threading.ManualResetEventSlim> und manuell eine Variable vor dem Signalisieren des Ereignisses zu verringern. Z. B. in einem Szenario Fork-Join können nur erstellen Sie eine <xref:System.Threading.CountdownEvent> , Signalanzahl von 5 besitzt und dann Start fünf von Arbeitselementen im Thread pool und haben bei jedem Aufruf der Work Item <xref:System.Threading.CountdownEvent.Signal%2A> bei Abschluss. Jeder Aufruf von <xref:System.Threading.CountdownEvent.Signal%2A> das Signal zu zählen, um 1 verringert. Auf der Haupt-Thread, der Aufruf von <xref:System.Threading.CountdownEvent.Wait%2A> blockiert, bis die Signalanzahl 0 (null) ist.  
  
> [!NOTE]
>  Erwägen Sie für Code, der nicht für die Interaktion mit älteren .NET Framework-Synchronisierung-APIs, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> Objekte oder <xref:System.Threading.Tasks.Parallel.Invoke%2A> eine noch einfachere Methode zum Ausdrücken von Parallelität Fork-Join-Methode.  
  
 <xref:System.Threading.CountdownEvent>hat die folgenden zusätzlichen Funktionen:  
  
-   Die "Wait"-Vorgang kann mithilfe von Abbruchtoken abgebrochen werden.  
  
-   Die Signalanzahl kann erhöht werden, nach dem Erstellen der Instanz.  
  
-   Instanzen können wiederverwendet werden, nachdem <xref:System.Threading.CountdownEvent.Wait%2A> hat zurückgegeben, indem die <xref:System.Threading.CountdownEvent.Reset%2A> Methode.  
  
-   Verfügbarmachen von Instanzen eine <xref:System.Threading.WaitHandle> für die Integration mit anderen .NET Framework-Synchronisierung-APIs wie z. B. <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Grundlegende Verwendung  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Threading.CountdownEvent> mit <xref:System.Threading.ThreadPool> Typen von Arbeitsaufgaben.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent mit Abbruch  
 Im folgende Beispiel wird gezeigt, wie für den Wartevorgang abgebrochen <xref:System.Threading.CountdownEvent> durch Verwenden eines Abbruchtokens. Das grundlegende Muster folgt dem Modell für einheitlichen Abbruch, eingeführt in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Beachten Sie, dass der Wartevorgang nicht die Threads abgebrochen, die signalisieren. In der Regel Abbruch wird angewendet, um eine logische Operation und zählen, die warten auf das Ereignis als auch für alle Arbeitsaufgaben, die der Wartevorgang synchronisiert. In diesem Beispiel wird jede Arbeitsaufgabe eine Kopie der gleiche Abbruchtoken übergeben, so, dass er auf die abbruchanforderung reagieren kann.  
  
## <a name="see-also"></a>Siehe auch  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
