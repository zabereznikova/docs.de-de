---
title: 'Gewusst wie: Angeben von Zusammenführungsoptionen in PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
ms.openlocfilehash: 91c5ac91538942368b66399bf0bc0132a15bf667
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825597"
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Gewusst wie: Angeben von Zusammenführungsoptionen in PLINQ
Dieses Beispiel zeigt, wie Mergeoptionen angegeben werden, die für alle nachfolgenden Operatoren in einer PLINQ-Abfrage angewendet werden. Sie müssen nicht explizit Mergeoptionen festlegen, aber dies könnte die Leistung verbessert. Weitere Informationen zu Mergeoptionen finden Sie unter [Mergeoptionen in PLINQ](merge-options-in-plinq.md).  
  
> [!WARNING]
> Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Verhalten von Mergeoptionen in einem einfachen Szenario, das eine ungeordnete Quelle aufweist und wo eine aufwändige Funktion auf jedes Element angewendet wird.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 In Fällen, in denen die <xref:System.Linq.ParallelMergeOptions.AutoBuffered>-Option eine unerwünschte Latenzzeit verursacht, bevor das erste Element ausgegeben wird, probieren Sie aus, ob mit der <xref:System.Linq.ParallelMergeOptions.NotBuffered>-Option Ergebniselemente schneller und reibungsloser bereitgestellt werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq.ParallelMergeOptions>
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
