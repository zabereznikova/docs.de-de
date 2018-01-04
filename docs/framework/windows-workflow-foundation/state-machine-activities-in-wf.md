---
title: "Zustandsautomatenaktivitäten in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62a211b51f37b306ffcc6b3b9a1ac65ccadd9db5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="db21a-102">Zustandsautomatenaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="db21a-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="db21a-103"> bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitätsdesigner zum Erstellen von Zustandsautomatenworkflows.</span><span class="sxs-lookup"><span data-stu-id="db21a-103"> provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="db21a-104">Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.</span><span class="sxs-lookup"><span data-stu-id="db21a-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="db21a-105">Stellt einen Status in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="db21a-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="db21a-106">Stellt einen beendenden Zustand in einem Zustandsautomaten dar.</span><span class="sxs-lookup"><span data-stu-id="db21a-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="db21a-107"><xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als beendender Zustand vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="db21a-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="db21a-108">Weitere Informationen finden Sie unter [FinalState-Aktivitäts-Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="db21a-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="db21a-109">Stellt den Übergang zwischen zwei Zuständen dar.</span><span class="sxs-lookup"><span data-stu-id="db21a-109">Represents the transition between two states.</span></span> <span data-ttu-id="db21a-110">Es ist keine **Toolbox** Element für <xref:System.Activities.Statements.Transition>; Übergänge werden im Workflow-Designer erstellt, per Drag & Drop eine Linie zwischen zwei Zuständen, oder indem ein Zustand auf den Dreiecken ablegt, das angezeigt, wenn ein Zustand über einen anderen bewegt wird .</span><span class="sxs-lookup"><span data-stu-id="db21a-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="db21a-111">Weitere Informationen finden Sie unter [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="db21a-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db21a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db21a-112">See Also</span></span>  
 [<span data-ttu-id="db21a-113">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="db21a-113">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
