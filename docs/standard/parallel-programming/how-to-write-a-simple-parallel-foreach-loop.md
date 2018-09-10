---
title: 'Gewusst wie: Schreiben einer einfachen Parallel.ForEach-Schleife'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03aaae7cd0faa7e7628da2e2e8f622f0967102cf
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205006"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="1d6c2-102">Gewusst wie: Schreiben einer einfachen Parallel.ForEach-Schleife</span><span class="sxs-lookup"><span data-stu-id="1d6c2-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="1d6c2-103">Dieses Beispiel zeigt die Verwendung einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife, um alle <xref:System.Collections.IEnumerable?displayProperty=nameWithType>- oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Datenquellen übergreifende Datenparallelität zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d6c2-104">In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="1d6c2-105">Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="1d6c2-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d6c2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d6c2-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="1d6c2-107">Eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife funktioniert wie eine <xref:System.Threading.Tasks.Parallel.For%2A>-Schleife.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="1d6c2-108">Die Quellsammlung ist partitioniert, und für die Arbeit sind basierend auf der Systemumgebung mehrere Threads eingeplant.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="1d6c2-109">Je mehr Prozessoren das System aufweist, desto schneller wird die parallele Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="1d6c2-110">Bei manchen Quellsammlungen wird eine sequenzielle Schleife je nach Größe der Quelle und Art der Arbeit vielleicht schneller ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="1d6c2-111">Weitere Informationen zur Leistung finden Sie unter [Potenzielle Fehler bei Daten- und Aufgabenparallelität](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="1d6c2-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="1d6c2-112">Weitere Informationen zu parallelen Schleifen finden Sie unter [Gewusst wie: Schreiben einer einfachen Parallel.For-Schleife](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="1d6c2-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="1d6c2-113">Um <xref:System.Threading.Tasks.Parallel.ForEach%2A> mit einer nicht generischen Sammlung zu verwenden, können Sie die Sammlung mithilfe der <xref:System.Linq.Enumerable.Cast%2A>-Erweiterungsmethode in eine generische Sammlung umwandeln, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d6c2-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="1d6c2-114">Sie können auch Parallel LINQ (PLINQ) verwenden, um die Verarbeitung von <xref:System.Collections.Generic.IEnumerable%601>-Datenquellen zu parallelisieren.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="1d6c2-115">Mit PLINQ können Sie deklarative Abfragesyntax verwenden, um das Schleifenverhalten auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="1d6c2-116">Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="1d6c2-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d6c2-117">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1d6c2-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1d6c2-118">Kopieren Sie diesen Code, und fügen Sie ihn in ein Visual Studio 2010-Konsolenanwendungsprojekt ein.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-118">Copy and paste this code into a Visual Studio 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="1d6c2-119">Fügen Sie einen Verweis auf „System.Drawing.dll“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="1d6c2-120">Drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="1d6c2-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6c2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d6c2-121">See also</span></span>

- [<span data-ttu-id="1d6c2-122">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="1d6c2-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
- [<span data-ttu-id="1d6c2-123">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="1d6c2-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
- [<span data-ttu-id="1d6c2-124">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="1d6c2-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
