---
title: 'Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen'
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen
Dieses Beispiel zeigt, wie die <xref:System.Linq.ParallelEnumerable.AsSequential%2A> Methode PLINQ anweisen, alle nachfolgende Operatoren in der Abfrage sequenziell zu verarbeiten. Obwohl sequenzielle Verarbeitung i. a. langsamer als die parallele ist, ist es manchmal erforderlich, um richtige Ergebnisse zu erzielen.  
  
> [!WARNING]
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Szenario, in dem <xref:System.Linq.ParallelEnumerable.AsSequential%2A> erforderlich ist, d. h. um die Reihenfolge, die in einer vorherigen-Klausel der Abfrage eingerichtet wurde beibehalten.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Zum Kompilieren und führen Sie diesen Code, fügen Sie ihn in die [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) Projekt, fügen Sie eine Zeile für den Methodenaufruf aus `Main`, und drücken Sie F5.  
  
## <a name="see-also"></a>Siehe auch  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
