---
title: Verfahrensworkflows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10cf83264fbdc2ed3dc088c11865c630c0b8f4f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="procedural-workflows"></a><span data-ttu-id="ae5b1-102">Verfahrensworkflows</span><span class="sxs-lookup"><span data-stu-id="ae5b1-102">Procedural Workflows</span></span>
<span data-ttu-id="ae5b1-103">Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="ae5b1-104">Hierzu zählen u. a. `While` und `If`.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="ae5b1-105">Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="ae5b1-106">Steuern des Ausführungsflusses</span><span class="sxs-lookup"><span data-stu-id="ae5b1-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="ae5b1-107">Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="ae5b1-108">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="ae5b1-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="ae5b1-109">Um Flusssteuerungsaktivitäten zu verwenden, Drag & drop aus der **Aktivität** Toolbox in eine zusammengesetzte Aktivität im Fenster Designers.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae5b1-110">Wenn [!INCLUDE[dublin](../../../includes/dublin-md.md)] zum Hosten von Workflows in einer Webfarm verwendet wird, verschiebt AppFabric Instanzen zwischen unterschiedlichen AppFabric-Servern.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="ae5b1-111">Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="ae5b1-112">Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="ae5b1-113">Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="ae5b1-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5b1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae5b1-114">See Also</span></span>  
 [<span data-ttu-id="ae5b1-115">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="ae5b1-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
