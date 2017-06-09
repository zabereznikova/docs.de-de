---
title: "Vorgehensweise: Konfigurieren der Nachverfolgung mit WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Vorgehensweise: Konfigurieren der Nachverfolgung mit WorkflowServiceHost
In diesem Thema wird erläutert, wie Sie die Nachverfolgung für einen unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]\-Workflow konfigurieren.  Es wird mithilfe einer Web.config\-Datei konfiguriert, indem ein Dienstverhalten angegeben wird.  
  
### Konfigurieren der Nachverfolgung in einer Konfigurationsdatei  
  
1.  Fügen Sie <xref:System.Activities.Tracking.EtwTrackingParticipant> hinzu, indem Sie in einer Konfigurationsdatei das \<`behavior`\>\-Element verwenden. Dies wird im folgenden Beispiel veranschaulicht.  
  
    ```  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
  
    ```  
  
    > [!NOTE]
    >  Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Im vorangehenden Konfigurationsbeispiel wird ein <xref:System.Activities.Tracking.EtwTrackingParticipant>\-Objekt hinzugefügt und ein Nachverfolgungsprofilname angegeben.  Nachverfolgungsprofile werden in einem \<`trackingProfile`\>\-Element innerhalb eines \<`tracking`\>\-Elements erstellt.  Das Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.  Im folgenden Beispiel wird das Erstellen eines Nachverfolgungsprofils veranschaulicht.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Nachverfolgungsprofilen finden Sie unter [Überwachungsprofile](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Nachverfolgung im Allgemeinen finden Sie unter [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  
  
### Konfigurieren der Nachverfolgung in Code  
  
1.  Fügen Sie den <xref:System.Activities.Tracking.EtwTrackingParticipant> mit dem <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>\-Verhalten in Code hinzu, wie im folgenden Beispiel gezeigt.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     Im vorangehenden Codebeispiel wird ein <xref:System.Activities.Tracking.EtwTrackingParticipant>\-Objekt hinzugefügt und ein Nachverfolgungsprofilname angegeben.  Nachverfolgungsprofile werden in einem \<`trackingProfile`\>\-Element innerhalb eines \<`tracking`\>\-Elements erstellt, wie im vorherigen Abschnitt gezeigt.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Nachverfolgungsprofilen finden Sie unter [Überwachungsprofile](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Nachverfolgung im Allgemeinen finden Sie unter [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  Ein Beispiel für das programmgesteuerte Konfigurieren der Nachverfolgung finden Sie unter [Konfigurieren der Nachverfolgung für einen Workflow](../../../../docs/framework/windows-workflow-foundation//configuring-tracking-for-a-workflow.md).  
  
## Siehe auch  
 [Vereinfachte Konfiguration für WCF\-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)   
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Überwachungsprofile](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)