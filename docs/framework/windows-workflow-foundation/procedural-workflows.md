---
title: Verfahrensworkflows
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 5cd97c8ccaae74e4275f809502ac0a4d3c2f042a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515228"
---
# <a name="procedural-workflows"></a><span data-ttu-id="336ba-102">Verfahrensworkflows</span><span class="sxs-lookup"><span data-stu-id="336ba-102">Procedural Workflows</span></span>
<span data-ttu-id="336ba-103">Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="336ba-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="336ba-104">Hierzu zählen u. a. `While` und `If`.</span><span class="sxs-lookup"><span data-stu-id="336ba-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="336ba-105">Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="336ba-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="336ba-106">Steuern des Ausführungsflusses</span><span class="sxs-lookup"><span data-stu-id="336ba-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="336ba-107">Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="336ba-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="336ba-108">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="336ba-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="336ba-109">Um Flusssteuerungsaktivitäten zu verwenden, Drag & drop aus der **Aktivität** Toolbox in eine zusammengesetzte Aktivität im Fenster Designers.</span><span class="sxs-lookup"><span data-stu-id="336ba-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="336ba-110">Wenn [!INCLUDE[dublin](../../../includes/dublin-md.md)] zum Hosten von Workflows in einer Webfarm verwendet wird, verschiebt AppFabric Instanzen zwischen unterschiedlichen AppFabric-Servern.</span><span class="sxs-lookup"><span data-stu-id="336ba-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="336ba-111">Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="336ba-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="336ba-112">Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="336ba-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="336ba-113">Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="336ba-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="336ba-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="336ba-114">See Also</span></span>  
 [<span data-ttu-id="336ba-115">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="336ba-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
