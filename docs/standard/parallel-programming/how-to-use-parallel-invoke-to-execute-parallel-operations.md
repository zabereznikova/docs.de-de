---
title: 'Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „Parallel.Invoke“'
description: Erfahren Sie, wie Sie die Methode Parallel.Invoke aus der Task Parallel Library (TPL) verwenden, die parallele Vorgänge für eine gemeinsame Datenquelle in .NET ausführt.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 084ade48b1406d23a11eb311739525f35ac973df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596344"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="ab30d-103">Vorgehensweise: Ausführen von parallelen Vorgängen mithilfe von „Parallel.Invoke“</span><span class="sxs-lookup"><span data-stu-id="ab30d-103">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="ab30d-104">In diesem Beispiel wird veranschaulicht, wie Vorgänge parallelisiert werden können, indem <xref:System.Threading.Tasks.Parallel.Invoke%2A> in der Task Parallel Library verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab30d-104">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="ab30d-105">Es werden drei Vorgänge für eine freigegebene Datenquelle ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ab30d-105">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="ab30d-106">Die Vorgänge können auf einfache Weise parallel ausgeführt werden, da die Quelle durch keinen von ihnen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ab30d-106">The operations can be executed in parallel in a straightforward manner, because none of them modifies the source.</span></span>

> [!NOTE]
> <span data-ttu-id="ab30d-107">Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambdaausdrücken.</span><span class="sxs-lookup"><span data-stu-id="ab30d-107">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="ab30d-108">Falls Sie mit Lambdaausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambdaausdrücke in PLINQ und TPL](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="ab30d-108">If you aren't familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="ab30d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab30d-109">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="ab30d-110">Mit <xref:System.Threading.Tasks.Parallel.Invoke%2A> geben Sie nur an, welche Aktionen gleichzeitig ausgeführt werden sollen. Alle Details der Threadplanung, einschließlich automatischem Skalieren entsprechend der Anzahl von Kernen auf dem Hostcomputer, werden von der Common Language Runtime verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ab30d-110">With <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="ab30d-111">In diesem Beispiel werden die Vorgänge, nicht die Daten parallelisiert.</span><span class="sxs-lookup"><span data-stu-id="ab30d-111">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="ab30d-112">Eine alternative Vorgehensweise besteht darin, die LINQ-Abfragen mithilfe von PLINQ zu parallelisieren und die Abfragen sequenziell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ab30d-112">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="ab30d-113">Sie könnten die Daten aber auch parallelisieren, indem Sie PLINQ verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab30d-113">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="ab30d-114">Eine weitere Möglichkeit ist, sowohl die Abfragen als auch die Aufgaben zu parallelisieren.</span><span class="sxs-lookup"><span data-stu-id="ab30d-114">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="ab30d-115">Durch den resultierenden Mehraufwand kann zwar die Leistung auf Hostcomputern mit relativ wenigen Prozessoren beeinträchtigt werden, die Skalierung auf Computern mit vielen Prozessoren ist jedoch besser.</span><span class="sxs-lookup"><span data-stu-id="ab30d-115">Although the resulting overhead might degrade performance on host computers with relatively few processors, it scales better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="ab30d-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ab30d-116">Compile the Code</span></span>

<span data-ttu-id="ab30d-117">Kopieren Sie das gesamte Beispiel, fügen Sie es in ein Microsoft Visual Studio-Projekt ein, und drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="ab30d-117">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab30d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab30d-118">See also</span></span>

- [<span data-ttu-id="ab30d-119">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="ab30d-119">Parallel Programming</span></span>](index.md)
- [<span data-ttu-id="ab30d-120">How to: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente</span><span class="sxs-lookup"><span data-stu-id="ab30d-120">How to: Cancel a Task and Its Children</span></span>](how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="ab30d-121">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="ab30d-121">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
