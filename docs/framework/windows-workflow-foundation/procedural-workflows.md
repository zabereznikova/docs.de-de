---
title: Verfahrensworkflows
description: In Workflow Foundation verwenden prozedurale Workflows Fluss Steuerungsmethoden, die denen in prozeduralen Sprachen ähneln.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 13d1b5e55b84687e2a78db1a94317b8b1e33328c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246029"
---
# <a name="procedural-workflows"></a><span data-ttu-id="c1d5d-103">Verfahrensworkflows</span><span class="sxs-lookup"><span data-stu-id="c1d5d-103">Procedural Workflows</span></span>

<span data-ttu-id="c1d5d-104">Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-104">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="c1d5d-105">Hierzu zählen u. a. `While` und `If`.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-105">These constructs include `While` and `If`.</span></span> <span data-ttu-id="c1d5d-106">Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-106">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="c1d5d-107">Steuern des Ausführungsflusses</span><span class="sxs-lookup"><span data-stu-id="c1d5d-107">Controlling Execution Flow</span></span>  

 <span data-ttu-id="c1d5d-108">Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-108">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="c1d5d-109">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="c1d5d-109">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="c1d5d-110">Wenn Sie Fluss Steuerungsaktivitäten verwenden möchten, ziehen Sie diese per Drag & amp; Drop aus der **Aktivitäts** Toolbox in eine zusammengesetzte Aktivität innerhalb des Designer Fensters.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-110">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1d5d-111">Wenn die Hostingfunktionen von Windows Server AppFabric zum Hosten von Workflows in einer Webfarm verwendet werden, verschiebt AppFabric Instanzen zwischen verschiedenen AppFabric-Servern.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-111">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="c1d5d-112">Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-112">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="c1d5d-113">Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-113">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="c1d5d-114">Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="c1d5d-114">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d5d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1d5d-115">See also</span></span>

- [<span data-ttu-id="c1d5d-116">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="c1d5d-116">Flowchart Workflows</span></span>](flowchart-workflows.md)
