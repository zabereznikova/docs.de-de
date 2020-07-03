---
title: 'Vorgehensweise: Zurückgeben eines Werts aus einer Aufgabe'
description: Informationen zur Verwendung des Typs „System.Threading.Tasks.Task<TResult>“, um einen Wert aus der Ergebniseigenschaft in .NET zurückzugeben
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 051cef7cac654e4369ec1486884876004370ba0b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767974"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="e3757-103">Vorgehensweise: Zurückgeben eines Werts aus einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e3757-103">How to: Return a Value from a Task</span></span>
<span data-ttu-id="e3757-104">In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ einen Wert aus der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e3757-104">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="e3757-105">Für das Beispiel ist es erforderlich, dass das Verzeichnis "C:\Users\Public\Pictures\Sample Pictures\" vorhanden ist und Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="e3757-105">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3757-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3757-106">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="e3757-107">Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft sperrt den aufrufenden Thread, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e3757-107">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="e3757-108">Um zu erfahren, wie das Ergebnis eines <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> an eine Fortsetzungsaufgabe übergeben wird, lesen Sie [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="e3757-108">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3757-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3757-109">See also</span></span>

- [<span data-ttu-id="e3757-110">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="e3757-110">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="e3757-111">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="e3757-111">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
