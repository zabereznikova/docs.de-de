---
title: 'Gewusst wie: Beschleunigen von kurzen Schleifenkörpern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 2597e37ed5901d704c94ff960bcb4b2c97633392
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722391"
---
# <a name="how-to-speed-up-small-loop-bodies"></a>Gewusst wie: Beschleunigen von kurzen Schleifenkörpern

Wenn eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Schleife nur wenig Text enthält, wird sie möglicherweise langsamer ausgeführt als die entsprechende sequenzielle Schleife, wie die [For](../../csharp/language-reference/keywords/for.md)-Schleife in C# und die [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90))-Schleife in Visual Basic. Der Leistungsverlust wird von dem Aufwand verursacht, der mit dem Partitionieren der Daten einhergeht, und von den Kosten des Aufrufs eines Delegaten bei jeder Schleifeniteration. Für solche Szenarien stellt die <xref:System.Collections.Concurrent.Partitioner>-Klasse die <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>-Methode bereit, die es Ihnen ermöglicht, eine sequenzielle Schleife für den Delegattext einzurichten, damit der Delegat nur einmal pro Partition und nicht einmal bei jeder Iteration aufgerufen wird. Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="example"></a>Beispiel  

 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Der in diesem Beispiel gezeigte Ansatz ist hilfreich, wenn die Schleife nur eine minimale Menge an Arbeit ausführt. Wenn die Arbeit berechnungsintensiver wird, erhalten Sie wahrscheinlich die gleiche oder eine bessere Leistung, wenn Sie eine <xref:System.Threading.Tasks.Parallel.For%2A>- oder <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife in Verbindung mit dem Standardpartitionierer verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Datenparallelität](data-parallelism-task-parallel-library.md)
- [Benutzerdefinierte Partitionierer für PLINQ und TPL](custom-partitioners-for-plinq-and-tpl.md)
- [Iteratoren (C#)](../../csharp/programming-guide/concepts/iterators.md)
- [Iteratoren (Visual Basic)](../../visual-basic/programming-guide/concepts/iterators.md)
- [Lambdaausdrücke in PLINQ und TPL](lambda-expressions-in-plinq-and-tpl.md)
