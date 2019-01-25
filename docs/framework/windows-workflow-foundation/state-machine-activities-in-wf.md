---
title: Zustandsautomatenaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 3086348d1c4f29e3f446e9525a12a9c207efb328
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618999"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="59ca5-102">Zustandsautomatenaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="59ca5-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="59ca5-103">bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitätsdesigner zum Erstellen von Zustandsautomatenworkflows.</span><span class="sxs-lookup"><span data-stu-id="59ca5-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="59ca5-104">Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.</span><span class="sxs-lookup"><span data-stu-id="59ca5-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="59ca5-105">Stellt einen Status in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="59ca5-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="59ca5-106">Stellt einen beendenden Zustand in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="59ca5-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="59ca5-107"><xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als beendender Zustand vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="59ca5-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="59ca5-108">Weitere Informationen finden Sie unter [FinalState-Aktivitäts-Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="59ca5-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="59ca5-109">Stellt den Übergang zwischen zwei Zuständen dar.</span><span class="sxs-lookup"><span data-stu-id="59ca5-109">Represents the transition between two states.</span></span> <span data-ttu-id="59ca5-110">Es gibt keine **Toolbox** Element für <xref:System.Activities.Statements.Transition>; Übergänge werden erstellt, die Workflow-Designer durch Ziehen und Ablegen einer Zeile zwischen zwei Zuständen, oder indem ein Zustand auf den Dreiecken ablegt, die angezeigt, wenn ein Zustand über einen anderen bewegt wird .</span><span class="sxs-lookup"><span data-stu-id="59ca5-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="59ca5-111">Weitere Informationen finden Sie unter [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="59ca5-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59ca5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59ca5-112">See also</span></span>
- [<span data-ttu-id="59ca5-113">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="59ca5-113">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
