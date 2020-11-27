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
# <a name="state-machine-activities-in-wf"></a>Zustandsautomatenaktivitäten in WF

.NET Framework 4,5 bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitäts Designer zum Erstellen von Zustands Automaten Workflows.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.|  
|<xref:System.Activities.Statements.State>|Stellt einen Status in einem Zustandsautomaten dar.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Stellt einen beendenden Zustand in einem Zustandsautomaten dar. <xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als beendender Zustand vorkonfiguriert ist. Weitere Informationen finden Sie unter [FinalState-Aktivitäts Designer](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Stellt den Übergang zwischen zwei Zuständen dar. Es ist kein **Toolbox** Element für vorhanden <xref:System.Activities.Statements.Transition> . Übergänge werden im Workflow-Designer erstellt, indem eine Linie zwischen zwei Zuständen gezogen und abgelegt wird, oder indem ein Zustand auf den Dreiecken abgelegt wird, die angezeigt werden, wenn ein Zustand über einen anderen Zustand bewegt wird. Weitere Informationen finden Sie unter [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Weitere Informationen

- [Lernprogramm 'Erste Schritte'](getting-started-tutorial.md)
