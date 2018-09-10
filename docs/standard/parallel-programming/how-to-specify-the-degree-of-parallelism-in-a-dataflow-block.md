---
title: 'Gewusst wie: Einen Parallelitätsgrad in einem Datenflussblock angeben'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b597cf93cdf249936a34b2c07b38d000c96333f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44211644"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a><span data-ttu-id="3a4bd-102">Gewusst wie: Einen Parallelitätsgrad in einem Datenflussblock angeben</span><span class="sxs-lookup"><span data-stu-id="3a4bd-102">How to: Specify the Degree of Parallelism in a Dataflow Block</span></span>
<span data-ttu-id="3a4bd-103">In diesem Dokument wird beschrieben, wie die <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType>-Eigenschaft festgelegt wird, damit ein Ausführungsdatenflussblock mehrere Nachrichten gleichzeitig verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-103">This document describes how to set the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> property to enable an execution dataflow block to process more than one message at a time.</span></span> <span data-ttu-id="3a4bd-104">Dies ist hilfreich, wenn ein Datenflussblock vorliegt, der eine lang andauernde Berechnung ausführt, und Sie von der parallelen Verarbeitung von Nachrichten profitieren können.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-104">Doing this is useful when you have a dataflow block that performs a long-running computation and can benefit from processing messages in parallel.</span></span> <span data-ttu-id="3a4bd-105">In diesem Beispiel wird die <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>-Klasse verwendet, um mehrere Datenflussvorgänge gleichzeitig auszuführen. Sie können den maximalen Grad an Parallelität jedoch in jedem der vordefinierten Ausführungsblocktypen angeben, die von der TPL-Datenflussbibliothek bereitgestellt werden: <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-105">This example uses the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> class to perform multiple dataflow operations concurrently; however, you can specify the maximum degree of parallelism in any of the predefined execution block types that the TPL Dataflow Library provides, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="3a4bd-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a4bd-106">Example</span></span>  
 <span data-ttu-id="3a4bd-107">Im folgenden Beispiel werden zwei Datenflussberechnungen ausgeführt und die für jede Berechnung erforderliche verstrichene Zeit ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-107">The following example performs two dataflow computations and prints the elapsed time that is required for each computation.</span></span> <span data-ttu-id="3a4bd-108">Die erste Berechnung gibt für den maximalen Grad an Parallelität den Wert 1 an, wobei es sich um den Standardwert handelt.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-108">The first computation specifies a maximum degree of parallelism of 1, which is the default.</span></span> <span data-ttu-id="3a4bd-109">Der Wert 1 für den maximalen Grad an Parallelität bewirkt, dass Nachrichten vom Datenflussblock seriell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-109">A maximum degree of parallelism of 1 causes the dataflow block to process messages serially.</span></span> <span data-ttu-id="3a4bd-110">Die zweite Berechnung ähnelt der ersten, sie gibt jedoch einen maximalen Grad an Parallelität an, der der Anzahl der verfügbaren Prozessoren entspricht.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-110">The second computation resembles the first, except that it specifies a maximum degree of parallelism that is equal to the number of available processors.</span></span> <span data-ttu-id="3a4bd-111">Dadurch kann der Datenflussblock mehrere Vorgänge parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-111">This enables the dataflow block to perform multiple operations in parallel.</span></span>  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a4bd-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3a4bd-112">Compiling the Code</span></span>  
 <span data-ttu-id="3a4bd-113">Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei namens `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` für Visual Basic) ein, und führen Sie dann den folgenden Befehl in einem Eingabeaufforderungsfenster von Visual Studio aus:</span><span class="sxs-lookup"><span data-stu-id="3a4bd-113">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="3a4bd-114">Visual C#</span><span class="sxs-lookup"><span data-stu-id="3a4bd-114">Visual C#</span></span>  
  
 <span data-ttu-id="3a4bd-115">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span><span class="sxs-lookup"><span data-stu-id="3a4bd-115">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span></span>  
  
 <span data-ttu-id="3a4bd-116">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a4bd-116">Visual Basic</span></span>  
  
 <span data-ttu-id="3a4bd-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span><span class="sxs-lookup"><span data-stu-id="3a4bd-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3a4bd-118">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="3a4bd-118">Robust Programming</span></span>  
 <span data-ttu-id="3a4bd-119">Standardmäßig gibt jeder vordefinierte Datenflussblock die Nachrichten in der Reihenfolge weiter, in der sie empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-119">By default, each predefined dataflow block propagates out messages in the order in which the messages are received.</span></span>  <span data-ttu-id="3a4bd-120">Obwohl mehrere Nachrichten gleichzeitig verarbeitet werden, wenn Sie einen maximalen Grad an Parallelität angeben, der größer als 1 ist, werden die Nachrichten möglicherweise weiterhin in der Reihenfolge weitergegeben, in der sie empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-120">Although multiple messages are processed simultaneously when you specify a maximum degree of parallelism that is greater than 1, they are still propagated out in the order in which they are received.</span></span>  
  
 <span data-ttu-id="3a4bd-121">Da die <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A>-Eigenschaft den maximalen Grad an Parallelität darstellt, wird der Datenflussblock u. U. mit einem geringeren Grad an Parallelität ausgeführt als angegeben.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-121">Because the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> property represents the maximum degree of parallelism, the dataflow block might execute with a lesser degree of parallelism than you specify.</span></span> <span data-ttu-id="3a4bd-122">Der Datenflussblock kann zum Erfüllen seiner Funktionsanforderungen oder aufgrund der Berücksichtigung eines Mangels an verfügbaren Systemressourcen einen geringeren Grad an Parallelität verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-122">The dataflow block can use a lesser degree of parallelism to meet its functional requirements or to account for a lack of available system resources.</span></span> <span data-ttu-id="3a4bd-123">Ein Datenflussblock wird nie mit einem höheren Grad an Parallelität ausgeführt als Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-123">A dataflow block never chooses a greater degree of parallelism than you specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4bd-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a4bd-124">See also</span></span>

- [<span data-ttu-id="3a4bd-125">Dataflow (Datenfluss)</span><span class="sxs-lookup"><span data-stu-id="3a4bd-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
