---
title: Zustandsautomatenaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 78727bab0102909e9f1e479210cf4b42801aa3ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="state-machine-activities-in-wf"></a>Zustandsautomatenaktivitäten in WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitätsdesigner zum Erstellen von Zustandsautomatenworkflows.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.|  
|<xref:System.Activities.Statements.State>|Stellt einen Status in einem Zustandsautomaten dar.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Stellt einen beendenden Zustand in einem Zustandsautomaten dar. <xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als beendender Zustand vorkonfiguriert ist. Weitere Informationen finden Sie unter [FinalState-Aktivitäts-Designer](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Stellt den Übergang zwischen zwei Zuständen dar. Es ist keine **Toolbox** Element für <xref:System.Activities.Statements.Transition>; Übergänge werden im Workflow-Designer erstellt, per Drag & Drop eine Linie zwischen zwei Zuständen, oder indem ein Zustand auf den Dreiecken ablegt, das angezeigt, wenn ein Zustand über einen anderen bewegt wird . Weitere Informationen finden Sie unter [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Siehe auch  
 [Tutorial mit ersten Schritten](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
