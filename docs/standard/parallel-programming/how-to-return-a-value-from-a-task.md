---
title: 'Vorgehensweise: Zurückgeben eines Werts aus einer Aufgabe'
description: Informationen zur Verwendung des Typs „System.Threading.Tasks.Task<TResult>“, um einen Wert aus der Ergebniseigenschaft in .NET zurückzugeben
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 60ab4a92fed4838934a2d544bea844a5810d4f5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701184"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="70c57-103">Vorgehensweise: Zurückgeben eines Werts aus einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="70c57-103">How to: Return a Value from a Task</span></span>

<span data-ttu-id="70c57-104">In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ einen Wert aus der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="70c57-104">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="70c57-105">Für das Beispiel ist es erforderlich, dass das Verzeichnis "C:\Users\Public\Pictures\Sample Pictures\" vorhanden ist und Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="70c57-105">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70c57-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70c57-106">Example</span></span>  

 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="70c57-107">Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft sperrt den aufrufenden Thread, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="70c57-107">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="70c57-108">Um zu erfahren, wie das Ergebnis eines <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> an eine Fortsetzungsaufgabe übergeben wird, lesen Sie [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="70c57-108">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c57-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70c57-109">See also</span></span>

- [<span data-ttu-id="70c57-110">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="70c57-110">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="70c57-111">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="70c57-111">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
