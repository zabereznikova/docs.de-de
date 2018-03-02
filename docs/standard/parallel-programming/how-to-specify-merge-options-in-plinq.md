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
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59ffff3019f10874bd2df977b80d46e903d13613
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>Gewusst wie: Angeben von Mergeoptionen in PLINQ
Dieses Beispiel zeigt, wie Mergeoptionen angegeben werden, die für alle nachfolgenden Operatoren in einer PLINQ-Abfrage angewendet werden. Sie müssen nicht explizit Mergeoptionen festlegen, aber dies könnte die Leistung verbessert. Weitere Informationen zu Mergeoptionen finden Sie unter [Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Verhalten von Mergeoptionen in einem einfachen Szenario, das eine ungeordnete Quelle aufweist und wo eine aufwändige Funktion auf jedes Element angewendet wird.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 In Fällen, in denen die <xref:System.Linq.ParallelMergeOptions.AutoBuffered>-Option eine unerwünschte Latenzzeit verursacht, bevor das erste Element ausgegeben wird, probieren Sie aus, ob mit der <xref:System.Linq.ParallelMergeOptions.NotBuffered>-Option Ergebniselemente schneller und reibungsloser bereitgestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelMergeOptions>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
