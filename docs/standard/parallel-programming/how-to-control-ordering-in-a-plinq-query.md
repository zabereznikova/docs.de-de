---
title: 'Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage'
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage
Diese Beispiele zeigen, wie zur Steuerung der Reihenfolge in einer PLINQ-Abfrage mithilfe der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> -Erweiterungsmethode.  
  
> [!WARNING]
>  Diese Beispiele dienen in erster Linie zur Veranschaulichung der Verwendung "," und können möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfragen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel behält die Reihenfolge der Quellsequenz. Dies ist manchmal notwendig. beispielsweise erfordern einige Abfrageoperatoren eine geordnete Quellsequenz, um richtige Ergebnisse zu erzielen.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einige Abfrageoperatoren, deren Quellsequenz wahrscheinlich erwartet wird, um sortiert zu werden. Diese Operatoren funktionieren für ungeordnete Sequenzen, aber sie können zu unerwarteten Ergebnissen führen.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Um diese Methode ausgeführt wird, fügen Sie ihn in die PLINQDataSample-Klasse die [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) Projekt, und drücken Sie F5.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird die Reihenfolge für den ersten Teil einer Abfrage beibehalten und dann entfernen Sie die Reihenfolge um die Leistung einer Join-Klausel zu erhöhen und die erneute Anwendung für das Endergebnis Sequenzen Sortierung veranschaulicht.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Um diese Methode ausgeführt wird, fügen Sie ihn in die PLINQDataSample-Klasse die [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) Projekt, und drücken Sie F5.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
