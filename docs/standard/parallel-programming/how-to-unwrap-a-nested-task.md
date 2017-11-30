---
title: 'Gewusst wie: Entpacken einer geschachtelten Aufgabe'
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="7c1f8-102">Gewusst wie: Entpacken einer geschachtelten Aufgabe</span><span class="sxs-lookup"><span data-stu-id="7c1f8-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="7c1f8-103">Sie können eine Aufgabe zurückgeben, von einer Methode und anschließend gewartet werden soll oder aus dieser Vorgang fortgesetzt werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7c1f8-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="7c1f8-104">Im vorherigen Beispiel der <xref:System.Threading.Tasks.Task%601.Result%2A> -Eigenschaft ist vom Typ `string` (`String` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="7c1f8-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="7c1f8-105">Allerdings kann in einigen Szenarien möchten eine Aufgabe innerhalb einer anderen Aufgabe erstellt, und klicken Sie dann die geschachtelte Aufgabe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="7c1f8-106">In diesem Fall die `TResult` der übergeordneten Aufgabe ist selbst eine Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="7c1f8-107">Im folgenden Beispiel wird die Eigenschaft eine `Task<Task<string>>` in c# oder `Task(Of Task(Of String))` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="7c1f8-108">Obwohl es möglich, Schreiben Code zum Entpacken der äußeren Aufgabe und die ursprüngliche Aufgabe abrufen und die zugehörige <xref:System.Threading.Tasks.Task%601.Result%2A> Eigenschaft solcher Code ist nicht einfach zu schreiben, da Ausnahmen und auch auf abbruchanforderungen behandelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="7c1f8-109">In diesem Fall wird empfohlen, dass Sie eine der verwenden die <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Erweiterungsmethoden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="7c1f8-110">Die <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Methoden können verwendet werden, um eine Transformation `Task<Task>` oder `Task<Task<TResult>>` (`Task(Of Task)` oder `Task(Of Task(Of TResult))` in Visual Basic), eine `Task` oder `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="7c1f8-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="7c1f8-111">Die neue Aufgabe stellt die geschachtelte innere Aufgabe vollständig und enthält Abbruch sowie alle Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c1f8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c1f8-112">Example</span></span>  
 <span data-ttu-id="7c1f8-113">Im folgenden Beispiel wird veranschaulicht, wie die <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="7c1f8-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="7c1f8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c1f8-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="7c1f8-115">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="7c1f8-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
