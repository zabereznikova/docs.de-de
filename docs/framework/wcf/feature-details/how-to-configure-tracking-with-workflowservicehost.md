---
title: 'Vorgehensweise: Konfigurieren der Nachverfolgung mit WorkflowServiceHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b9bba3c589ca0232171bab58c26b19c7312a313
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>Vorgehensweise: Konfigurieren der Nachverfolgung mit WorkflowServiceHost
In diesem Thema wird erläutert, wie Sie die Nachverfolgung für einen unter [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehosteten <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Workflow konfigurieren. Es wird mithilfe einer Web.config-Datei konfiguriert, indem ein Dienstverhalten angegeben wird.  
  
### <a name="configure-tracking-in-configuration"></a>Konfigurieren der Nachverfolgung in einer Konfigurationsdatei  
  
1.  Fügen Sie <xref:System.Activities.Tracking.EtwTrackingParticipant> hinzu, indem Sie in einer Konfigurationsdatei das <`behavior`>-Element verwenden. Dies wird im folgenden Beispiel veranschaulicht.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Im vorangehenden Konfigurationsbeispiel wird ein <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt hinzugefügt und ein Nachverfolgungsprofilname angegeben. Nachverfolgungsprofile werden in einem <`trackingProfile`>-Element innerhalb eines <`tracking`>-Elements erstellt. Das Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert. Im folgenden Beispiel wird das Erstellen eines Nachverfolgungsprofils veranschaulicht.  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Verfolgen von Profilen finden Sie unter [Nachverfolgungsprofile](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]im Allgemeinen Tracking finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).  
  
### <a name="configure-tracking-in-code"></a>Konfigurieren der Nachverfolgung in Code  
  
1.  Fügen Sie den <xref:System.Activities.Tracking.EtwTrackingParticipant> mit dem <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>-Verhalten in Code hinzu, wie im folgenden Beispiel gezeigt.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     Im vorangehenden Codebeispiel wird ein <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt hinzugefügt und ein Nachverfolgungsprofilname angegeben. Nachverfolgungsprofile werden in einem <`trackingProfile`>-Element innerhalb eines <`tracking`>-Elements erstellt, wie im vorherigen Abschnitt gezeigt.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Verfolgen von Profilen finden Sie unter [Nachverfolgungsprofile](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]im Allgemeinen Tracking finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md). Ein Beispiel für das Konfigurieren der nachverfolgung programmgesteuert finden Sie unter [Konfigurieren der nachverfolgung für einen Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vereinfachte Konfiguration für WCF-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Überwachungsprofile](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
