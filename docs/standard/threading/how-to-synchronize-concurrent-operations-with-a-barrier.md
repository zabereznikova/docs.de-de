---
title: 'Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
ms.openlocfilehash: 33098878764c2f8a8c1f83a122028da40b984243
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137976"
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere
Das folgende Beispiel zeigt das Synchronisieren gleichzeitiger Aufgaben mit einer <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Beispiel  
 Zweck des folgenden Programms ist, zu zählen, wie viele Iterationen (oder Phasen) erforderlich sind, damit zwei Threads ihre jeweilige Hälfte der Lösung mithilfe eines Zufallsalgorithmus zum erneuten Mischen der Wörter in der gleichen Phase finden. Nachdem jeder Thread seine Wörter gemischt hat, vergleicht der Barrierennachphasen-Vorgang die beiden Ergebnisse, um festzustellen, ob der vollständige Satz in der richtigen Reihenfolge gerendert wurde.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Eine <xref:System.Threading.Barrier> ist ein Objekt, das verhindert, dass einzelne Aufgaben in einem parallelen Vorgang fortgesetzt werden, bevor alle Aufgaben die Barriere erreichen. Das ist nützlich, wenn ein parallel ausgeführter Vorgang in Phasen erfolgt, und jede Phase eine Synchronisierung zwischen Aufgaben erfordert. In diesem Beispiel besteht der Vorgang aus zwei Phasen. In der ersten Phase füllt jede Aufgabe ihren Abschnitt des Puffers mit Daten. Wenn eine Aufgabe ihren Abschnitt gefüllt hat, signalisiert die Aufgabe der Barriere, das sie zum Fortfahren bereit ist, und wartet. Wenn alle Aufgaben ihr Signal an die Barriere gesendet haben, werden sie entsperrt, und die zweite Phase startet. Die Barriere ist erforderlich, da die zweite Phase voraussetzt, dass jede Aufgabe Zugriff auf alle Daten hat, die bis zu diesem Punkt generiert wurden. Ohne die Barriere könnten die Aufgaben, die zuerst ihre Abschnitte gefüllt haben, versuchen, aus Puffern zu lesen, die noch nicht von anderen Aufgaben gefüllt wurden. Sie können eine beliebige Anzahl von Phasen auf diese Weise synchronisieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenstrukturen für die parallele Programmierung](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
