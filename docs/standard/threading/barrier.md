---
title: Barriere
ms.date: 09/14/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 5aa34f7f39f4b9b626bea29372cf984f3cefb361
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138150"
---
# <a name="barrier"></a>Barriere

Eine <xref:System.Threading.Barrier?displayProperty=nameWithType> ist eine Synchronisierungsprimitive, die es mehreren (als *Teilnehmer* bezeichneten) Threads ermöglicht, in Phasen gleichzeitig an einem Algorithmus zu arbeiten. Jeder Teilnehmer wird ausgeführt, bis er den Barrierepunkt im Code erreicht hat. Die Barriere stellt das Ende einer Arbeitsphase dar. Wenn ein Teilnehmer die Barriere erreicht hat, wird er blockiert, bis alle Teilnehmer dieselbe Barriere erreicht haben. Nachdem alle Teilnehmer die Barriere erreicht haben, können Sie eine Nachphasenaktion aufrufen. Diese Nachphasenaktion kann verwendet werden, um Aktionen über einen einzelnen Thread auszuführen, während alle anderen Threads weiterhin blockiert sind. Nachdem die Aktion ausgeführt wurde, wird die Blockierung aller Teilnehmer aufgehoben.  
  
 Der folgende Codeausschnitt zeigt ein grundlegendes Barrieremuster.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 Ein vollständiges Beispiel finden Sie unter [Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere](how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="adding-and-removing-participants"></a>Hinzufügen und Entfernen von Teilnehmern

 Wenn Sie eine <xref:System.Threading.Barrier>-Instanz erstellen, geben Sie die Anzahl von Teilnehmern an. Sie können auch jederzeit Teilnehmer dynamisch hinzufügen oder entfernen. Wenn ein Teilnehmer z.B. seinen Teil des Problems gelöst hat, können Sie das Ergebnis speichern, die Ausführung auf diesem Thread beenden und <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> aufrufen, um die Anzahl von Teilnehmern in der Barriere zu verringern. Wenn Sie einen Teilnehmer hinzufügen, indem Sie <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType> aufrufen, gibt der Rückgabewert die aktuelle Phasennummer an, die möglicherweise nützlich ist, um die Arbeit des neuen Teilnehmers zu initialisieren.  
  
## <a name="broken-barriers"></a>Fehlerhafte Barrieren

 Deadlocks können auftreten, wenn ein Teilnehmer die Barriere nicht erreicht. Um diese Deadlocks zu vermeiden, verwenden Sie die Überladungen der <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType>-Methode, um ein Timeout und ein Abbruchtoken anzugeben. Diese Überladungen geben einen booleschen Wert zurück, den jeder Teilnehmer überprüfen kann, bevor er zur nächsten Phase springt.  
  
## <a name="post-phase-exceptions"></a>Nachphasenausnahmen

 Wenn der Nachphasendelegat eine Ausnahme auslöst, wird diese in ein <xref:System.Threading.BarrierPostPhaseException>-Objekt eingeschlossen, das dann an alle Teilnehmer verteilt wird.  
  
## <a name="barrier-versus-continuewhenall"></a>Barriere und ContinueWhenAll

 Barrieren sind besonders nützlich, wenn die Threads mehrere Phasen in Schleifen ausführen. Wenn Ihr Code nur eine oder zwei Arbeitsphasen erfordert, sollten Sie in Betracht ziehen, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekte mit einer beliebigen Art von implizitem Join zu verwenden, einschließlich:  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 Weitere Informationen finden Sie unter [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Siehe auch

- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
- [Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere](how-to-synchronize-concurrent-operations-with-a-barrier.md)
