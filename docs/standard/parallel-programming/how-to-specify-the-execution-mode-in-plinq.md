---
title: "Gewusst wie: Angeben des Ausführungsmodus in PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Gewusst wie: Angeben des Ausführungsmodus in PLINQ
Dieses Beispiel zeigt, wie PLINQ seine Standardheuristik zu umgehen und die Parallelisierung einer Abfrage unabhängig von der Form der Abfrage zu erzwingen.  
  
> [!WARNING]
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ wurde entwickelt, um Verkaufschancen für die Parallelisierung auszunutzen. Nicht alle Abfragen werden jedoch von der parallelen Ausführung profitieren. Wenn eine Abfrage einen einzelnen Benutzerdelegaten, der sehr geringem Aufwand ist enthält, wird beispielsweise die Abfrage, in der Regel schneller sequenziell ausgeführt. Dies ist, da der Aufwand bei der Aktivierung der parallelen Ausführung teurer als die Beschleunigung ist, abgerufen wird. PLINQ daher nicht automatisch auf jede Abfrage parallelisieren. Zunächst wird die Form der Abfrage und die verschiedenen Operatoren, die es bilden untersucht. Auf Grundlage dieser Analyse kann PLINQ in der Standardmodus für die Ausführung entscheiden, einige oder alle der Abfrage sequenziell ausführen. In einigen Fällen können Sie mehr über die Abfrage wissen jedoch als PLINQ in der Analyse ermitteln kann. Beispielsweise können Sie wissen, dass ein Delegat sehr kostspielig ist und die Abfrage definitiv von einer Parallelisierung profitieren. In solchen Fällen können Sie die <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> Methode, und geben Sie die <xref:System.Linq.ParallelExecutionMode.ForceParallelism> Wert PLINQ anweisen, stets die Abfrage Parallel ausgeführt.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ausschneiden und Einfügen dieser Code in der [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) und rufen Sie die Methode aus `Main`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
