---
title: "Barrier (.NET Framework) | Microsoft Docs"
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
  - "synchronization primitives, Barrier"
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Barrier (.NET Framework)
Eine *Barriere* ist eine benutzerdefinierte Synchronisierungsprimitive, die es mehreren Threads \(als *Teilnehmer* bezeichnet\) ermöglicht, in Phasen gleichzeitig an einem Algorithmus zu arbeiten.  Jeder Teilnehmer wird ausgeführt, bis er den Barrierepunkt im Code erreicht hat.  Die Barriere stellt das Ende einer Arbeitsphase dar.  Wenn ein Teilnehmer die Barriere erreicht hat, wird er blockiert, bis alle Teilnehmer dieselbe Barriere erreicht haben.  Nachdem alle Teilnehmer die Barriere erreicht haben, können Sie eine Nachphasenaktion aufrufen.  Diese Nachphasenaktion kann verwendet werden, um Aktionen über einen einzelnen Thread auszuführen, während alle anderen Threads weiterhin blockiert sind.  Nachdem die Aktion ausgeführt wurde, wird die Blockierung aller Teilnehmer aufgehoben.  
  
 Der folgende Codeausschnitt zeigt ein grundlegendes Barrieremuster.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 Ein vollständiges Beispiel finden Sie unter [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## Hinzufügen und Entfernen von Teilnehmern  
 Wenn Sie eine <xref:System.Threading.Barrier>\-Instanz erstellen, geben Sie die Anzahl von Teilnehmern an.  Sie können auch jederzeit Teilnehmer dynamisch hinzufügen oder entfernen.  Wenn ein Teilnehmer z. B. seinen Teil des Problems gelöst hat, können Sie das Ergebnis speichern, die Ausführung auf diesem Thread beenden und <xref:System.Threading.Barrier.RemoveParticipant%2A> aufrufen, um die Anzahl von Teilnehmern in der Barriere zu verringern.  Wenn Sie einen Teilnehmer hinzufügen, indem Sie <xref:System.Threading.Barrier.AddParticipant%2A> aufrufen, gibt der Rückgabewert die aktuelle Phasennummer an, die möglicherweise nützlich ist, um die Arbeit des neuen Teilnehmers zu initialisieren.  
  
## Fehlerhafte Barrieren  
 Deadlocks können auftreten, wenn ein Teilnehmer die Barriere nicht erreicht.  Um diese Deadlocks zu vermeiden, verwenden Sie die Überladungen der <xref:System.Threading.Barrier.SignalAndWait%2A>\-Methode, um ein Timeout und ein Abbruchtoken anzugeben.  Diese Überladungen geben einen booleschen Wert zurück, den jeder Teilnehmer überprüfen kann, bevor er zur nächsten Phase springt.  
  
## Nachphasenausnahmen  
 Wenn der Nachphasendelegat eine Ausnahme auslöst, wird diese in ein <xref:System.Threading.BarrierPostPhaseException>\-Objekt eingeschlossen, das dann an alle Teilnehmer verteilt wird.  
  
## Barriere und ContinueWhenAll  
 Barrieren sind besonders nützlich, wenn die Threads mehrere Phasen in Schleifen ausführen.  Wenn Ihr Code nur eine oder zwei Arbeitsphasen erfordert, sollten Sie in Betracht ziehen, <xref:System.Threading.Tasks.Task?displayProperty=fullName>\-Objekte mit einer beliebigen Art von implizitem Join zu verwenden, einschließlich:  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 Weitere Informationen finden Sie unter [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## Siehe auch  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)