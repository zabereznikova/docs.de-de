---
title: "How to: Synchronize Concurrent Operations with a Barrier | Microsoft Docs"
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
  - "Barrier, how to use"
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Synchronize Concurrent Operations with a Barrier
Im folgenden Beispiel wird das Synchronisieren paralleler Aufgaben mit einer <xref:System.Threading.Barrier> veranschaulicht.  
  
## Beispiel  
 Das folgende Programm zählt, wie viele Iterationen \(oder Phasen\) erforderlich sind, bis zwei Threads mit einem Zufallsalgorithmus zum erneuten Mischen der Wörter ihre Hälfte der Projektmappe in der gleichen Phase finden.  Nachdem jeder Thread seine Wörter gemischt hat, werden die beiden Ergebnisse im Vorgang nach der Phase für die Barriere verglichen, um festzustellen, ob der vollständige Satz in der richtigen Wortfolge gerendert wurde.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Eine <xref:System.Threading.Barrier> ist ein Objekt, das verhindert, dass einzelne Aufgaben in einem Parallelvorgang fortgesetzt werden, bevor alle Aufgaben die Barriere erreichen.  Dies ist nützlich, wenn ein Parallelvorgang in Phasen auftritt und jede Phase eine Synchronisierung der Aufgaben erfordert.  In diesem Beispiel umfasst der Vorgang zwei Phasen.  In der ersten Phase füllt jede Aufgabe ihren Abschnitt des Puffers mit Daten auf.  Wenn die einzelnen Aufgabe das Auffüllen der Abschnitte beendet haben, signalisiert die Aufgabe der Barriere, dass sie fortgesetzt werden kann und wartet anschließend.  Wenn alle Aufgaben der Barriere das entsprechende Signal gesendet haben, wird die Sperre für sie aufgehoben, und die zweiten Phase beginnt.  Die Barriere ist erforderlich, da in der zweiten Phase jede Aufgabe Zugriff auf alle Daten benötigt, die bis zu diesem Punkt generiert wurden.  Ohne die Barriere könnten die zuerst abgeschlossenen Aufgaben versuchen, in Puffern zu lesen, die noch nicht von anderen Aufgaben aufgefüllt wurden.  Sie können auf diese Weise eine beliebige Anzahl von Phasen synchronisieren.  
  
## Siehe auch  
 [Data Structures for Parallel Programming](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)