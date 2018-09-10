---
title: 'Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fd67d5f0cb5af33dc2b79f86148557a0dca6ec4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190279"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen
Dieses Beispiel zeigt die Verwendung der <xref:System.Linq.ParallelEnumerable.AsSequential%2A>-Methode, um PLINQ anzuweisen, alle nachfolgenden Operatoren in der Abfrage sequenziell zu verarbeiten. Sequenzielle Verarbeitung ist zwar in der Regel langsamer als parallele, doch manchmal ist sie erforderlich, um richtige Ergebnisse zu erzielen.  
  
> [!WARNING]
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Szenario, in dem <xref:System.Linq.ParallelEnumerable.AsSequential%2A> erforderlich ist, um die Reihenfolge in einer vorherigen Klausel der Abfrage beizubehalten.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um diesen Code zu kompilieren und auszuführen, fügen Sie ihn in das [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md)-Projekt ein, fügen Sie eine Zeile für den Methodenaufruf aus `Main` hinzu, und drücken Sie F5.  
  
## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
