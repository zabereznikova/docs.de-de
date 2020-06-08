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
ms.openlocfilehash: 144d004d697b84a011cedafc7d07b679ef8852c3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288146"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="c2793-102">Gewusst wie: Zurückgeben eines Werts aus einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="c2793-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="c2793-103">In diesem Beispiel wird gezeigt, wie Sie mit dem <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Typ einen Wert aus der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c2793-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="c2793-104">Für das Beispiel ist es erforderlich, dass das Verzeichnis "C:\Users\Public\Pictures\Sample Pictures\" vorhanden ist und Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="c2793-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2793-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2793-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="c2793-106">Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft sperrt den aufrufenden Thread, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c2793-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="c2793-107">Um zu erfahren, wie das Ergebnis eines <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> an eine Fortsetzungsaufgabe übergeben wird, lesen Sie [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="c2793-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2793-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2793-108">See also</span></span>

- [<span data-ttu-id="c2793-109">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="c2793-109">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="c2793-110">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="c2793-110">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
