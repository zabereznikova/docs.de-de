---
title: Zustandsautomatenaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120912"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="0f3d9-102">Zustandsautomatenaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="0f3d9-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="0f3d9-103">bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitätsdesigner zum Erstellen der Zustandsautomatworkflows an.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="0f3d9-104">Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="0f3d9-105">Stellt einen Status in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="0f3d9-106">Stellt einen beendenden Zustand in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-106">Represents a terminating state in a state machine.</span></span> <xref:System.Activities.Core.Presentation.FinalState> <span data-ttu-id="0f3d9-107">wird ein Aktivitätsdesigner, die bei verwendet, erstellt eine <xref:System.Activities.Statements.State> der als beendender Zustand vorkonfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-107">is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="0f3d9-108">Weitere Informationen finden Sie unter [FinalState-Aktivitäts-Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="0f3d9-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="0f3d9-109">Stellt den Übergang zwischen zwei Zuständen dar.</span><span class="sxs-lookup"><span data-stu-id="0f3d9-109">Represents the transition between two states.</span></span> <span data-ttu-id="0f3d9-110">Es gibt keine **Toolbox** Element für <xref:System.Activities.Statements.Transition>; Übergänge werden erstellt, die Workflow-Designer durch Ziehen und Ablegen einer Zeile zwischen zwei Zuständen, oder indem ein Zustand auf den Dreiecken ablegt, die angezeigt, wenn ein Zustand über einen anderen bewegt wird .</span><span class="sxs-lookup"><span data-stu-id="0f3d9-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="0f3d9-111">Weitere Informationen finden Sie unter [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="0f3d9-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f3d9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f3d9-112">See also</span></span>

- [<span data-ttu-id="0f3d9-113">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="0f3d9-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
