---
title: 'Gewusst wie: Schreiben einer einfachen Parallel.ForEach-Schleife'
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Gewusst wie: Schreiben einer einfachen Parallel.ForEach-Schleife
Dieses Beispiel zeigt, wie eine <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> Schleife zum Aktivieren von Datenparallelität über alle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> -Datenquelle.  
  
> [!NOTE]
>  In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Ein <xref:System.Threading.Tasks.Parallel.ForEach%2A> Schleife funktioniert wie ein <xref:System.Threading.Tasks.Parallel.For%2A> Schleife. Die quellauflistung partitioniert ist, und die Arbeit auf mehrere Threads, die basierend auf den Systemumgebungsvariablen geplant ist. Die weitere Prozessoren auf dem System ausgeführt wird, desto schnellere parallele-Methode. Bei einigen Auflistungen Quelle möglicherweise eine sequenzielle Schleife schneller, je nach Größe der Quelle und die Art der ausgeführten Arbeit. Weitere Informationen zur Leistung finden Sie unter [potenzielle Fehler bei Daten- und Aufgabenparallelität](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Weitere Informationen zu parallelen Schleifen finden Sie unter [wie: Schreiben einer einfachen Parallel.For-Schleife](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Mit <xref:System.Threading.Tasks.Parallel.ForEach%2A> mit eine nicht generische Auflistung können Sie mithilfe der <xref:System.Linq.Enumerable.Cast%2A> Erweiterungsmethode, um die Auflistung in eine generische Auflistung umzuwandeln, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Sie können auch Parallel LINQ (PLINQ) verwenden, um Verarbeitung zu parallelisieren <xref:System.Collections.Generic.IEnumerable%601> Datenquellen. PLINQ können Sie deklarative Abfragesyntax zu verwenden, um das Schleifenverhalten auszudrücken. Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Kopieren Sie diesen Code in eine [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010-Konsolenanwendungsprojekt.  
  
-   Hinzufügen eines Verweises auf System.Drawing.dll  
  
-   Drücken Sie F5  
  
## <a name="see-also"></a>Siehe auch  
 [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
