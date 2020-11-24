---
title: 'Vorgehensweise: Erstellen und Ausführen einer einfachen PLINQ-Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 67863346046b0c400529b87355c11f97d0c3f01f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827086"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Vorgehensweise: Erstellen und Ausführen einer einfachen PLINQ-Abfrage

Das Beispiel in diesem Artikel zeigt, wie Sie eine einfache Parallel LINQ-Abfrage (Language Integrated Query) erstellen, indem Sie die <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType>-Erweiterungsmethode in der Quellsequenz verwenden und die Abfrage mit der <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType>-Methode ausführen.  
  
> [!NOTE]
> In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 Dieses Beispiel zeigt das grundlegende Muster zum Erstellen und Ausführen einer beliebigen Parallel LINQ-Abfrage, wenn die Sortierung der Ergebnissequenz nicht wichtig ist. Unsortierte Abfragen sind im Allgemeinen schneller als sortierte Abfragen. Die Abfrage partitioniert die Quelle in Aufgaben, die asynchron in mehreren Threads ausgeführt werden. Die Reihenfolge, in der jede Aufgabe abgeschlossen wird, hängt nicht nur von der Menge der mit der Verarbeitung der Elemente in der Partition verbundenen Arbeit, sondern auch von externen Faktoren ab, beispielsweise wie das Betriebssystem jeden Thread plant. Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md). Weitere Informationen zur Beibehaltung der Sortierung von Elementen in einer Abfrage finden Sie unter [Vorgehensweise: Steuern der Reihenfolge in einer PLINQ-Abfrage](how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
