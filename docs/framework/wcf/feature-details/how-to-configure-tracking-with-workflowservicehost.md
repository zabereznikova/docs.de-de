---
title: 'Vorgehensweise: Konfigurieren der Nachverfolgung mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: cf30ace90f86e282d72c4da5f2c3707905360aeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257352"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="ccfcd-102">Vorgehensweise: Konfigurieren der Nachverfolgung mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="ccfcd-102">How to: Configure Tracking with WorkflowServiceHost</span></span>

<span data-ttu-id="ccfcd-103">In diesem Thema wird erläutert, wie Sie die Nachverfolgung für einen unter [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehosteten <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Workflow konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="ccfcd-104">Es wird mithilfe einer Web.config-Datei konfiguriert, indem ein Dienstverhalten angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="ccfcd-105">Konfigurieren der Nachverfolgung in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ccfcd-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="ccfcd-106">Fügen Sie <xref:System.Activities.Tracking.EtwTrackingParticipant> mithilfe des <`behavior`>-Elements in einer Konfigurationsdatei hinzu, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="ccfcd-107">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="ccfcd-108">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-108">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="ccfcd-109">Im vorangehenden Konfigurationsbeispiel wird ein <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt hinzugefügt und ein Nachverfolgungsprofilname angegeben.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="ccfcd-110">Überwachungs Profile werden in einem <`trackingProfile`>-Element innerhalb eines <`tracking`> Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="ccfcd-111">Das Überwachungsprofil enthält Nachverfolgungsabfragen, mit denen ein Überwachungsteilnehmer Workflowereignisse abonnieren kann. Diese werden ausgegeben, wenn sich der Zustand einer Workflowinstanz zur Laufzeit ändert.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="ccfcd-112">Im folgenden Beispiel wird das Erstellen eines Nachverfolgungsprofils veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-112">The following example shows how to create a tracking profile.</span></span>  
  
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
  
     <span data-ttu-id="ccfcd-113">Weitere Informationen zu Überwachungs Profilen finden Sie unter nach [Verfolgungs profile](../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-113">For more information about tracking profiles, see [Tracking Profiles](../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="ccfcd-114">Weitere Informationen zur Nachverfolgung im Allgemeinen finden Sie unter [Workflow Verfolgung und Ablauf Verfolgung](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="ccfcd-115">Konfigurieren der Nachverfolgung in Code</span><span class="sxs-lookup"><span data-stu-id="ccfcd-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="ccfcd-116">Fügen Sie den <xref:System.Activities.Tracking.EtwTrackingParticipant> mit dem <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>-Verhalten in Code hinzu, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="ccfcd-117">Im vorangehenden Codebeispiel wird ein <xref:System.Activities.Tracking.EtwTrackingParticipant>-Objekt hinzugefügt und ein Nachverfolgungsprofilname angegeben.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="ccfcd-118">Überwachungs Profile werden in einem <`trackingProfile`>-Element innerhalb eines <`tracking`>-Elements erstellt, wie im vorherigen Abschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccfcd-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="ccfcd-119">Weitere Informationen zu Überwachungs Profilen finden Sie unter nach [Verfolgungs profile](../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-119">For more information about tracking profiles, see [Tracking Profiles](../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="ccfcd-120">Weitere Informationen zur Nachverfolgung im Allgemeinen finden Sie unter [Workflow Verfolgung und Ablauf Verfolgung](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="ccfcd-121">Ein Beispiel für die programmgesteuerte Konfiguration der Überwachung finden Sie unter [Konfigurieren der Nachverfolgung für einen Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ccfcd-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfcd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccfcd-122">See also</span></span>

- [<span data-ttu-id="ccfcd-123">Vereinfachte Konfiguration für WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="ccfcd-123">Simplified Configuration for WCF Services</span></span>](../samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="ccfcd-124">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="ccfcd-124">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="ccfcd-125">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="ccfcd-125">Tracking Profiles</span></span>](../../windows-workflow-foundation/tracking-profiles.md)
