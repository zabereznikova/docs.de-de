---
title: Verfahrensworkflows
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: d1edd73b2276d0a3918b61c8da2d04769d09e7c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956115"
---
# <a name="procedural-workflows"></a><span data-ttu-id="525d0-102">Verfahrensworkflows</span><span class="sxs-lookup"><span data-stu-id="525d0-102">Procedural Workflows</span></span>
<span data-ttu-id="525d0-103">Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="525d0-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="525d0-104">Hierzu zählen u. a. `While` und `If`.</span><span class="sxs-lookup"><span data-stu-id="525d0-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="525d0-105">Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="525d0-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="525d0-106">Steuern des Ausführungsflusses</span><span class="sxs-lookup"><span data-stu-id="525d0-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="525d0-107">Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="525d0-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="525d0-108">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="525d0-108">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="525d0-109">Wenn Sie Fluss Steuerungsaktivitäten verwenden möchten, ziehen Sie diese per Drag & amp; Drop aus der **Aktivitäts** Toolbox in eine zusammengesetzte Aktivität innerhalb des Designer Fensters.</span><span class="sxs-lookup"><span data-stu-id="525d0-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="525d0-110">Wenn die Hostingfunktionen von Windows Server AppFabric zum Hosten von Workflows in einer Webfarm verwendet werden, verschiebt AppFabric Instanzen zwischen verschiedenen AppFabric-Servern.</span><span class="sxs-lookup"><span data-stu-id="525d0-110">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="525d0-111">Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="525d0-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="525d0-112">Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="525d0-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="525d0-113">Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="525d0-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="525d0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="525d0-114">See also</span></span>

- [<span data-ttu-id="525d0-115">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="525d0-115">Flowchart Workflows</span></span>](flowchart-workflows.md)
