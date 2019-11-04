---
title: 'Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „Parallel.Invoke“'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 665490601cad9ccd7881042aed576b95bbc07115
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139728"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="dc108-102">Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „Parallel.Invoke“</span><span class="sxs-lookup"><span data-stu-id="dc108-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="dc108-103">In diesem Beispiel wird veranschaulicht, wie Vorgänge parallelisiert werden können, indem <xref:System.Threading.Tasks.Parallel.Invoke%2A> in der Task Parallel Library verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc108-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="dc108-104">Es werden drei Vorgänge für eine freigegebene Datenquelle ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc108-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="dc108-105">Da die Quelle durch keinen der Vorgänge geändert wird, können diese auf einfache Weise parallel ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dc108-105">Because none of the operations modifies the source, they can be executed in parallel in a straightforward manner.</span></span>

> [!NOTE]
> <span data-ttu-id="dc108-106">Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambdaausdrücken.</span><span class="sxs-lookup"><span data-stu-id="dc108-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="dc108-107">Falls Sie mit der Verwendung von Lambdaausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="dc108-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="dc108-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc108-108">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="dc108-109">Beachten Sie, dass Sie mit <xref:System.Threading.Tasks.Parallel.Invoke%2A> nur angeben, welche Aktionen gleichzeitig ausgeführt werden sollen. Alle Details der Threadplanung, einschließlich automatischem Skalieren entsprechend der Anzahl von Kernen auf dem Hostcomputer, werden von der Common Language Runtime verwaltet.</span><span class="sxs-lookup"><span data-stu-id="dc108-109">Note that with <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="dc108-110">In diesem Beispiel werden die Vorgänge, nicht die Daten parallelisiert.</span><span class="sxs-lookup"><span data-stu-id="dc108-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="dc108-111">Eine alternative Vorgehensweise besteht darin, die LINQ-Abfragen mithilfe von PLINQ zu parallelisieren und die Abfragen sequenziell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc108-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="dc108-112">Sie könnten die Daten aber auch parallelisieren, indem Sie PLINQ verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc108-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="dc108-113">Eine weitere Möglichkeit ist, sowohl die Abfragen als auch die Aufgaben zu parallelisieren.</span><span class="sxs-lookup"><span data-stu-id="dc108-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="dc108-114">Durch den resultierenden Mehraufwand kann zwar die Leistung auf Hostcomputern mit relativ wenigen Prozessoren beeinträchtigt werden, die Skalierung auf Computern mit vielen Prozessoren ist jedoch deutlich besser.</span><span class="sxs-lookup"><span data-stu-id="dc108-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it would scale much better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="dc108-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="dc108-115">Compile the Code</span></span>

<span data-ttu-id="dc108-116">Kopieren Sie das gesamte Beispiel, fügen Sie es in ein Microsoft Visual Studio-Projekt ein, und drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="dc108-116">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc108-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc108-117">See also</span></span>

- [<span data-ttu-id="dc108-118">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="dc108-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="dc108-119">Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente</span><span class="sxs-lookup"><span data-stu-id="dc108-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="dc108-120">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="dc108-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
