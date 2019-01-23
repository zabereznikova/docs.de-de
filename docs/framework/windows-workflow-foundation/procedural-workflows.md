---
title: Verfahrensworkflows
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 29fc6f5ebd6bf1984f287c3d407d2564249c65f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500537"
---
# <a name="procedural-workflows"></a><span data-ttu-id="0b02f-102">Verfahrensworkflows</span><span class="sxs-lookup"><span data-stu-id="0b02f-102">Procedural Workflows</span></span>
<span data-ttu-id="0b02f-103">Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b02f-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="0b02f-104">Hierzu zählen u. a. `While` und `If`.</span><span class="sxs-lookup"><span data-stu-id="0b02f-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="0b02f-105">Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="0b02f-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="0b02f-106">Steuern des Ausführungsflusses</span><span class="sxs-lookup"><span data-stu-id="0b02f-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="0b02f-107">Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b02f-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="0b02f-108">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="0b02f-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="0b02f-109">Um Flusssteuerungsaktivitäten zu verwenden, ziehen Sie aus, und legen Sie sie aus der **Aktivität** Toolbox in einer zusammengesetzten Aktivität im Fenster Designers.</span><span class="sxs-lookup"><span data-stu-id="0b02f-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b02f-110">Wenn [!INCLUDE[dublin](../../../includes/dublin-md.md)] zum Hosten von Workflows in einer Webfarm verwendet wird, verschiebt AppFabric Instanzen zwischen unterschiedlichen AppFabric-Servern.</span><span class="sxs-lookup"><span data-stu-id="0b02f-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="0b02f-111">Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="0b02f-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="0b02f-112">Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0b02f-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="0b02f-113">Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="0b02f-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b02f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b02f-114">See also</span></span>
- [<span data-ttu-id="0b02f-115">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="0b02f-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
