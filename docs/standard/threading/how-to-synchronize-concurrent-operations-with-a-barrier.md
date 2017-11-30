---
title: "Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere"
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere
Das folgende Beispiel zeigt die Vorgehensweise beim Synchronisieren gleichzeitiger Vorgänge mit einer <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Programm dient gezählt, wie viele Iterationen (oder Phasen) sind für zwei Threads finden ihre Hälfte der Projektmappe auf der gleichen Phase erforderlich mithilfe einer Zufallsalgorithmus zu die Wörtern Zuordnung. Nach jeder Thread seine Wörter gemischt hat, vergleicht der Barriere Nachphasenaktion Vorgang die beiden Ergebnisse, um festzustellen, ob der vollständige Satz in der richtigen Reihenfolge gerendert wurde.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Ein <xref:System.Threading.Barrier> ist ein Objekt, das verhindert, einzelne Aufgaben in einem parallelen Vorgang dass fortgesetzt, bis alle Aufgaben die Barriere nicht erreicht. Das ist nützlich, wenn Sie ein parallel ausgeführten Vorgang erfolgt in Phasen und jede Phase eine Synchronisierung zwischen Aufgaben erforderlich. In diesem Beispiel wird in zwei Phasen des Vorgangs. In der ersten Phase füllt jede Aufgabe aus seinem Abschnitt, der den Puffer mit Daten. Beim Abschließen jeder Aufgabe Füllen von einem Abschnitt signalisiert die Aufgabe, die Grenze, die sie zum Fortfahren ist, und klicken Sie dann wartet. Wenn alle Aufgaben die Barriere signalisiert haben, sind entsperrt, und die zweite Phase gestartet wird. Die Barriere ist erforderlich, da die zweite Phase erfordert, dass jede Aufgabe den Zugriff auf alle Daten verfügen, die zum angegebenen Zeitpunkt generiert wurde. Ohne die Grenze der ersten Aufgaben abgeschlossen versucht möglicherweise, zu aus dem Puffer zu lesen, die nicht noch von anderen Aufgaben ausgefüllt wurden. Sie können eine beliebige Anzahl von Phasen auf diese Weise synchronisieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenstrukturen für die parallele Programmierung](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
