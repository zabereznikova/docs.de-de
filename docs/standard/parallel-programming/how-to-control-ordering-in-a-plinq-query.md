---
title: 'Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
ms.openlocfilehash: 88f19092b06e4dece202e880287bdb95e04d2f2d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817106"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage
Diese Beispiele zeigen die Steuerung der Reihenfolge in einer PLINQ-Abfrage mithilfe der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Erweiterungsmethode.  
  
> [!WARNING]
> Diese Beispiele sollen primär die Nutzung darstellen und werden möglicherweise nicht schneller ausgeführt als die entsprechenden sequenziellen LINQ to Objects-Abfragen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Reihenfolge der Quellsequenz beibehalten. Dies ist manchmal notwendig. Beispielsweise erfordern einige Abfrageoperatoren eine geordnete Quellsequenz, um richtige Ergebnisse zu erzielen.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einige Abfrageoperatoren, bei denen wahrscheinlich eine sortierte Quellsequenz zu erwarten ist. Diese Operatoren funktionieren bei ungeordneten Sequenzen, aber sie können zu unerwarteten Ergebnissen führen.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Um diese Methode auszuführen, fügen Sie sie im [PLINQ-Datenbeispiel](plinq-data-sample.md)-Projekt in die PLINQDataSample-Klasse ein, und drücken Sie F5.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden das Beibehalten der Reihenfolge für den ersten Teil einer Abfrage, dann das Entfernen der Reihenfolge zur Steigerung der Leistung einer Join-Klausel sowie das erneute Anwenden der Reihenfolge für die endgültige Ergebnissequenz gezeigt.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Um diese Methode auszuführen, fügen Sie sie im [PLINQ-Datenbeispiel](plinq-data-sample.md)-Projekt in die PLINQDataSample-Klasse ein, und drücken Sie F5.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
