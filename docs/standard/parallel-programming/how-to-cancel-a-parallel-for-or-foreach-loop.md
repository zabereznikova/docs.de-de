---
title: 'Vorgehensweise: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife'
description: Brechen Sie eine Parallel.For- oder Parallel.ForEach-Schleife in .NET ab, indem Sie ein Abbruchtokenobjekt für die Methode im ParallelOptions-Parameter bereitstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: d5deeeab6c332d29f3fa667d6211e8fb4b0eae50
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817314"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Vorgehensweise: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife
Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>- und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode unterstützen den Abbruch durch die Verwendung von Abbruchtoken. Weitere Informationen über Abbrüche im Allgemeinen finden Sie unter [Abbruch in verwalteten Threads](../threading/cancellation-in-managed-threads.md). Übergeben Sie in einer parallelen Schleife das <xref:System.Threading.CancellationToken> mit dem <xref:System.Threading.Tasks.ParallelOptions>-Parameter an die Methode, und schließen Sie den parallelen Aufruf in einen Try-Catch-Block ein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Abbruch des Aufrufs einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode veranschaulicht. Sie können den gleichen Ansatz auf einen <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Aufruf anwenden.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Wenn das Token, das den Abbruch signalisiert, mit dem in der <xref:System.Threading.Tasks.ParallelOptions>-Instanz angegebenen identisch ist, löst die parallele Schleife beim Abbruch eine einzelne <xref:System.OperationCanceledException> aus. Wenn ein anderes Token den Abbruch verursacht, löst die Schleife eine <xref:System.AggregateException> mit einer <xref:System.OperationCanceledException> als InnerException aus.  
  
## <a name="see-also"></a>Siehe auch

- [Datenparallelität](data-parallelism-task-parallel-library.md)
- [Lambdaausdrücke in PLINQ und TPL](lambda-expressions-in-plinq-and-tpl.md)
