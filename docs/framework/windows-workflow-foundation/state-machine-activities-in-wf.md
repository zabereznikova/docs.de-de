---
title: "Zustandsautomatenaktivit&#228;ten in WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Zustandsautomatenaktivit&#228;ten in WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bietet mehrere vom System bereitgestellte Aktivitäten und Aktivitätsdesigner zum Erstellen von Zustandsautomatworkflows.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Führt enthaltene Aktivitäten mithilfe des vertrauten Zustandsautomatparadigmas aus.|  
|<xref:System.Activities.Statements.State>|Stellt einen Zustand in einem Zustandsautomat dar.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Stellt einen endenden Zustand in einem Zustandsautomat dar.<xref:System.Activities.Core.Presentation.FinalState> ist ein Aktivitätsdesigner, bei dessen Verwendung ein <xref:System.Activities.Statements.State> erstellt wird, der als endender Zustand vorkonfiguriert ist.Weitere Informationen finden Sie unter [FinalState\-Aktivitäts\-Designer](../Topic/FinalState%20Activity%20Designer.md).|  
|<xref:System.Activities.Statements.Transition>|Stellt den Übergang zwischen zwei Zuständen dar.Die **Toolbox** enthält kein Element für <xref:System.Activities.Statements.Transition>. Übergänge werden im Workflow\-Designer erstellt, indem eine Linie zwischen zwei Zuständen gezogen und abgelegt wird, oder indem ein Zustand auf den Dreiecken ablegt wird, die angezeigt werden, wenn ein Zustand über einen anderen bewegt wird.Weitere Informationen finden Sie unter [Übergangsaktivitäts\-Designer](../Topic/Transition%20Activity%20Designer.md).|  
  
## Siehe auch  
 [Lernprogramm 'Erste Schritte'](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)