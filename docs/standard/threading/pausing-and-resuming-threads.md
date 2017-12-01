---
title: Anhalten und Fortsetzen von Threads
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
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a>Anhalten und Fortsetzen von Threads
Die gängigsten Verfahren zum Synchronisieren der Aktivitäten von Threads bestehen darin, Threads zu blockieren und freizugeben bzw. Objekte oder Codebereiche zu sperren. Weitere Informationen zu diesen Sperr- und Blockierungsmechanismen finden Sie unter [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Sie können auch vorsehen, dass Threads sich selbst deaktivieren (in den Standbymodus versetzen). Wenn Threads blockiert oder deaktiviert sind, können Sie sie mit einer <xref:System.Threading.ThreadInterruptedException> wieder aus ihrem Wartezustand holen.  
  
## <a name="the-threadsleep-method"></a>Die "Thread.Sleep"-Methode  
 Aufrufen der <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> Methode bewirkt, dass der aktuelle Thread blockiert werden sofort für die Anzahl der Millisekunden oder das Zeitintervall, das Sie an die Methode übergeben, und liefert den Rest der Zeitscheibe an einen anderen Thread. Nachdem dieses Intervall abgelaufen ist, setzt der pausierte Thread die Ausführung fort.  
  
 Ein Thread kann <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> nicht für einen anderen Thread aufrufen.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>ist eine statische Methode, die immer den aktuellen Thread, in den Energiesparmodus führt.  
  
 Aufrufen von <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> mit einem Wert von <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> bewirkt, dass einen Thread, bis er von einem anderen Thread unterbrochen wird, die Aufrufe in den Energiesparmodus der <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> Methode für den inaktiven Thread, oder bis zur Beendigung durch einen Aufruf von seiner <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> Methode.  Im folgenden Beispiel werden beide Methoden zum Unterbrechen des Standbymodus eines Threads veranschaulicht.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Unterbrechen von Threads  
 Sie können einen wartenden Thread unterbrechen, durch den Aufruf der <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> Methode für den blockierten Thread ausgelöst werden soll eine <xref:System.Threading.ThreadInterruptedException>, die den Thread aus dem blockierenden Aufruf unterbrochen. Der Thread sollte die <xref:System.Threading.ThreadInterruptedException> abfangen und die angemessenen Aktionen zum Fortsetzen der Arbeit ausführen. Wenn der Thread die Ausnahme ignoriert, wird diese von der Laufzeit abgefangen, und der Thread wird beendet.  
  
> [!NOTE]
>  Wenn der Zielthread beim Aufrufen von <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nicht blockiert ist, muss er zuerst blockiert werden, bevor er unterbrochen werden kann. Wenn der Thread nie blockiert wird, kann er ohne jegliche Unterbrechung abgeschlossen werden.  
  
 Wenn sich ein Thread in einem verwalteten Wartezustand befindet, kann er durch <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>  sofort aktiviert werden. Wenn es sich bei ein Wartevorgang auf einem nicht verwalteten Wartezustand ist (z. B. einem Plattformaufruf der Win32- [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) Funktion), weder <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> noch <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> Steuerung des Threads übernehmen, bis es verwaltetem Code zurückkehrt oder verwalteten Code aufruft. In verwaltetem Code sieht das Verhalten wie folgt aus:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> aktiviert einen Thread aus jedem Wartezustand heraus und veranlasst, dass eine <xref:System.Threading.ThreadInterruptedException> im Zielthread ausgelöst wird.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>aktiviert einen Thread aus jedem Wartezustand heraus und löst eine <xref:System.Threading.ThreadAbortException> für den Thread ausgelöst wird. Ausführliche Informationen finden Sie unter [Zerstören von Threads](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
