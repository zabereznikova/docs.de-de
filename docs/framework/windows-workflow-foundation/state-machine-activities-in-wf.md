---
title: Zustandsautomatenaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004600"
---
# <a name="state-machine-activities-in-wf"></a>Zustandsautomatenaktivitäten in WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitätsdesigner zum Erstellen von Zustandsautomatenworkflows.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatenparadigmas aus.|  
|<xref:System.Activities.Statements.State>|Stellt einen Status in einem Zustandsautomaten dar.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Stellt einen beendenden Zustand in einem Zustandsautomaten dar. <xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als beendender Zustand vorkonfiguriert ist. Weitere Informationen finden Sie unter [FinalState-Aktivitäts-Designer](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Stellt den Übergang zwischen zwei Zuständen dar. Es gibt keine **Toolbox** Element für <xref:System.Activities.Statements.Transition>; Übergänge werden erstellt, die Workflow-Designer durch Ziehen und Ablegen einer Zeile zwischen zwei Zuständen, oder indem ein Zustand auf den Dreiecken ablegt, die angezeigt, wenn ein Zustand über einen anderen bewegt wird . Weitere Informationen finden Sie unter [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Siehe auch

- [Tutorial mit ersten Schritten](getting-started-tutorial.md)
