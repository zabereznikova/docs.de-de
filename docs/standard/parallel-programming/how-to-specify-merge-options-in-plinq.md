---
title: 'Gewusst wie: Angeben von Mergeoptionen in PLINQ'
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Gewusst wie: Angeben von Mergeoptionen in PLINQ
Dieses Beispiel zeigt, wie die Mergeoptionen angeben, die für alle nachfolgenden Operatoren in einer PLINQ-Abfrage angewendet wird. Sie müssen nicht explizit festlegen von Zusammenführungsoptionen, aber dies daher kann die Leistung verbessert. Weitere Informationen zu Mergeoptionen finden Sie unter [Zusammenführungsoptionen in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Verhalten von Zusammenführungsoptionen in einem einfachen Szenario, das eine ungeordnete Quelle aufweist und eine teure-Funktion auf jedes Element angewendet wird.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 In Fällen, in denen die <xref:System.Linq.ParallelMergeOptions.AutoBuffered> Option verursacht einer unerwünschten Latenzzeit, bevor das erste Element ausgegeben wird, und versuchen Sie die <xref:System.Linq.ParallelMergeOptions.NotBuffered> Option aus, um die Ergebniselemente schneller und gleichmäßiger ergeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelMergeOptions>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
