---
title: 'Gewusst wie: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion'
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Gewusst wie: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion
Dieses Beispiel zeigt, wie die <xref:System.Linq.ParallelEnumerable.Aggregate%2A> Methode, um eine benutzerdefinierte Aggregatfunktion auf eine Quellsequenz anzuwenden.  
  
> [!WARNING]
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel berechnet die Standardabweichung einer Sequenz von ganzen Zahlen.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 In diesem Beispiel verwendet eine Überladung des Operators standard Aggregatabfrage für PLINQ eindeutig ist. Diese Überladung lässt eine zusätzliche <xref:System.Func%603?displayProperty=nameWithType> als dritten Eingabeparameter. Dieser Delegat kombiniert die Ergebnisse von allen Threads, bevor er die abschließende Berechnung der aggregierten Ergebnissen führt. In diesem Beispiel fügen wir die Summen gemeinsam von allen Threads.  
  
 Beachten Sie, dass bei einem einzelnen Ausdruck, der Rückgabewert der Textkörper eines Lambda-Ausdrucks besteht aus den <xref:System.Func%602?displayProperty=nameWithType> Delegaten ist der Wert des Ausdrucks.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
