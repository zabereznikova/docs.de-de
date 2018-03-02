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
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06d54efe5c8bac58746a1e01a194af55fde901b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="5b901-102">Gewusst wie: Entpacken einer geschachtelten Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5b901-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="5b901-103">Sie können eine Aufgabe aus einer Methode zurückgeben und anschließend warten oder von dieser Aufgabe aus fortfahren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5b901-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="5b901-104">Im vorherigen Beispiel ist die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft vom Typ `string` (in Visual Basic `String`).</span><span class="sxs-lookup"><span data-stu-id="5b901-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="5b901-105">Allerdings könnten Sie in einigen Szenarien eine Aufgabe innerhalb einer anderen Aufgabe erstellen und dann die geschachtelte Aufgabe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5b901-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="5b901-106">In diesem Fall ist `TResult` der einschließenden Aufgabe selbst eine Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="5b901-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="5b901-107">Im folgenden Beispiel ist die Result-Eigenschaft `Task<Task<string>>` in C# oder `Task(Of Task(Of String))` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5b901-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="5b901-108">Es ist zwar möglich, Code zum Enthüllen der äußeren Aufgabe zu schreiben und die ursprüngliche Aufgabe sowie die zugehörige <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft abzurufen, doch solcher Code ist nicht einfach zu schreiben, da Ausnahmen und auch Abbruchanforderungen behandelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5b901-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="5b901-109">In diesem Fall sollten Sie eine der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Erweiterungsmethoden verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b901-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="5b901-110">Mit der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Methode kann eine beliebige `Task<Task>` oder `Task<Task<TResult>>` (in Visual Basic `Task(Of Task)` oder `Task(Of Task(Of TResult))`) in eine `Task` oder `Task<TResult>` (in Visual Basic `Task(Of TResult)`) umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5b901-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="5b901-111">Die neue Aufgabe stellt die geschachtelte innere Aufgabe vollständig dar und enthält den Abbruchstatus sowie alle Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="5b901-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b901-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b901-112">Example</span></span>  
 <span data-ttu-id="5b901-113">Im folgenden Beispiel wird die Verwendung der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Erweiterungsmethoden erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b901-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="5b901-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b901-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="5b901-115">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="5b901-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
