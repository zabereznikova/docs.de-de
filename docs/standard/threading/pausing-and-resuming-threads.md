---
title: Anhalten und Unterbrechen von Threads
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interrupting threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
ms.openlocfilehash: 369631603791d90c51244c1dc9907b9d8ec17364
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291161"
---
# <a name="pausing-and-interrupting-threads"></a>Anhalten und Unterbrechen von Threads

Die gängigsten Verfahren zum Synchronisieren der Aktivitäten von Threads bestehen darin, Threads zu blockieren und freizugeben bzw. Objekte oder Codebereiche zu sperren. Weitere Informationen zu diesen Sperr- und Blockierungsmechanismen finden Sie unter [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).  
  
 Sie können auch vorsehen, dass Threads sich selbst deaktivieren (in den Standbymodus versetzen). Wenn Threads blockiert oder deaktiviert sind, können Sie sie mit einer <xref:System.Threading.ThreadInterruptedException> wieder aus ihrem Wartezustand holen.  
  
## <a name="the-threadsleep-method"></a>Die „Thread.Sleep“-Methode

 Durch Aufrufen der <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>-Methode wird der aktuelle Thread sofort für die in Millisekunden angegebene Dauer oder das Zeitintervall, das Sie an die Methode übergeben, blockiert, wobei das restliche Zeitsegment dieses Threads einem anderen Thread zur Verfügung gestellt wird. Nachdem dieses Intervall abgelaufen ist, setzt der pausierte Thread die Ausführung fort.  
  
 Ein Thread kann <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> nicht für einen anderen Thread aufrufen.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> ist eine statische Methode, die immer den aktuellen Thread in den Standbymodus versetzt.  
  
 Durch den Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> mit einem Wert von <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> bleibt ein Thread so lange deaktiviert (im Standbymodus), bis er von einem anderen Thread unterbrochen wird, der die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>-Methode in dem im Standbymodus befindlichen Thread aufruft, oder bis er durch einen Aufruf seiner <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode beendet wird.  Im folgenden Beispiel werden beide Methoden zum Unterbrechen des Standbymodus eines Threads veranschaulicht.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Unterbrechen von Threads

 Sie können einen wartenden Thread unterbrechen, indem Sie die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>-Methode für den blockierten Thread aufrufen, um eine <xref:System.Threading.ThreadInterruptedException> auszulösen, durch die der Thread aus dem blockierenden Aufruf gelöst wird. Der Thread sollte die <xref:System.Threading.ThreadInterruptedException> abfangen und die angemessenen Aktionen zum Fortsetzen der Arbeit ausführen. Wenn der Thread die Ausnahme ignoriert, wird diese von der Laufzeit abgefangen, und der Thread wird beendet.  
  
> [!NOTE]
> Wenn der Zielthread beim Aufrufen von <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nicht blockiert ist, muss er zuerst blockiert werden, bevor er unterbrochen werden kann. Wenn der Thread nie blockiert wird, kann er ohne jegliche Unterbrechung abgeschlossen werden.  
  
 Wenn sich ein Thread in einem verwalteten Wartezustand befindet, kann er durch <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>  sofort aktiviert werden. Bei einem nicht verwalteten Wartezustand (beispielsweise bei einem Plattformaufruf der Win32-[WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject)-Funktion) können <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> die Steuerung des Threads erst übernehmen, wenn der Thread zu verwaltetem Code zurückkehrt oder einen Aufruf in verwaltetem Code ausführt. In verwaltetem Code sieht das Verhalten wie folgt aus:  
  
- <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> aktiviert einen Thread aus jedem Wartezustand heraus und veranlasst, dass eine <xref:System.Threading.ThreadInterruptedException> im Zielthread ausgelöst wird.  
  
- <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aktiviert einen Thread aus jedem Wartezustand heraus und veranlasst, dass eine <xref:System.Threading.ThreadAbortException> im Thread ausgelöst wird. Ausführliche Informationen finden Sie unter [Zerstören von Threads](destroying-threads.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadInterruptedException>
- <xref:System.Threading.ThreadAbortException>
- [Threading](index.md)
- [Verwenden von Threads und Threading](using-threads-and-threading.md)
- [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md)
