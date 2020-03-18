---
title: 'Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 495f68114bfe960b8182be4ab76b72043b2d0cc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141671"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="aaa2a-102">Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="aaa2a-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="aaa2a-103">In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ einen Wert aus der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="aaa2a-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="aaa2a-104">Für das Beispiel ist es erforderlich, dass das Verzeichnis "C:\Users\Public\Pictures\Sample Pictures\" vorhanden ist und Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="aaa2a-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa2a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aaa2a-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="aaa2a-106">Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft sperrt den aufrufenden Thread, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="aaa2a-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="aaa2a-107">Um zu erfahren, wie das Ergebnis eines <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> an eine Fortsetzungsaufgabe übergeben wird, lesen Sie [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="aaa2a-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa2a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aaa2a-108">See also</span></span>

- [<span data-ttu-id="aaa2a-109">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="aaa2a-109">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [<span data-ttu-id="aaa2a-110">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="aaa2a-110">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
