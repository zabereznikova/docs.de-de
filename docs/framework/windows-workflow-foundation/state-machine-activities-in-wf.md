---
title: Zustandsautomatenaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: dd0bfae1f24ecd9f98c0a2f04265581f880202a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261721"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="06d2a-102">Zustandsautomatenaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="06d2a-102">State Machine Activities in WF</span></span>

<span data-ttu-id="06d2a-103">.NET Framework 4,5 bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitäts Designer zum Erstellen von Zustands Automaten Workflows.</span><span class="sxs-lookup"><span data-stu-id="06d2a-103">.NET Framework 4.5 provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="06d2a-104">Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.</span><span class="sxs-lookup"><span data-stu-id="06d2a-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="06d2a-105">Stellt einen Status in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="06d2a-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="06d2a-106">Stellt einen beendenden Zustand in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="06d2a-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="06d2a-107"><xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als beendender Zustand vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="06d2a-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="06d2a-108">Weitere Informationen finden Sie unter [FinalState-Aktivitäts Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="06d2a-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="06d2a-109">Stellt den Übergang zwischen zwei Zuständen dar.</span><span class="sxs-lookup"><span data-stu-id="06d2a-109">Represents the transition between two states.</span></span> <span data-ttu-id="06d2a-110">Es ist kein **Toolbox** Element für vorhanden <xref:System.Activities.Statements.Transition> . Übergänge werden im Workflow-Designer erstellt, indem eine Linie zwischen zwei Zuständen gezogen und abgelegt wird, oder indem ein Zustand auf den Dreiecken abgelegt wird, die angezeigt werden, wenn ein Zustand über einen anderen Zustand bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="06d2a-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="06d2a-111">Weitere Informationen finden Sie unter [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="06d2a-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06d2a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06d2a-112">See also</span></span>

- [<span data-ttu-id="06d2a-113">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="06d2a-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
