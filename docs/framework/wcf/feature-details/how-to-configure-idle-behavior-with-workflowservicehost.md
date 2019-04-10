---
title: 'Vorgehensweise: Konfigurieren des Leerlaufverhaltens mit WorkflowServiceHost'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: a676f03b4e6f9dd210b843a6f3bf00c735889500
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330154"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="b84dc-102">Vorgehensweise: Konfigurieren des Leerlaufverhaltens mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="b84dc-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="b84dc-103">Workflows wechseln in den Leerlaufzustand, sobald sie auf ein Lesezeichen treffen, das zum Fortsetzen einen externen Anstoß erfordert, z. B. wenn die Workflowinstanz per <xref:System.ServiceModel.Activities.Receive> auf die Übermittlung einer Nachricht wartet.</span><span class="sxs-lookup"><span data-stu-id="b84dc-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> <span data-ttu-id="b84dc-104">ist ein Verhalten, mit dem Sie den Zeitraum zwischen, wenn eine Dienstinstanz im Leerlauf wechselt und bei der Beibehaltung oder Entladung die Instanz angeben.</span><span class="sxs-lookup"><span data-stu-id="b84dc-104">is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="b84dc-105">Es enthält zwei Eigenschaften, mit denen Sie diese Zeitspannen festlegen können.</span><span class="sxs-lookup"><span data-stu-id="b84dc-105">It contains two properties that enable you to set these time spans.</span></span> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> <span data-ttu-id="b84dc-106">Gibt die Zeitspanne zwischen dem Eintritt eine Workflowdienstinstanz Leerlauf und der Beibehaltung der Workflowdienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="b84dc-106">specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> <span data-ttu-id="b84dc-107">Gibt die Zeitspanne zwischen bei einer Workflowdienstinstanz in den Leerlauf übergeht, und wenn die Workflowdienstinstanz entladen wird, in dem Entladen bedeutet, dass die Instanz im Instanzspeicher beibehalten und aus dem Arbeitsspeicher entfernen.</span><span class="sxs-lookup"><span data-stu-id="b84dc-107">specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="b84dc-108">In diesem Thema wird erklärt, wie Sie das <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> -Verhalten in einer Konfigurationsdatei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b84dc-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="b84dc-109">So konfigurieren Sie WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="b84dc-109">To configure WorkflowIdleBehavior</span></span>  
  
1. <span data-ttu-id="b84dc-110">Hinzufügen einer <`workflowIdle`>-Element der <`behavior`> Element innerhalb der <`serviceBehaviors`>-Element wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b84dc-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="b84dc-111">Das `timeToUnload` -Attribut gibt den Zeitraum zwischen dem Eintritt einer Workflowdienstinstanz in den Leerlauf und der Entladung des Workflowdiensts an.</span><span class="sxs-lookup"><span data-stu-id="b84dc-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="b84dc-112">Das `timeToPersist` -Attribut gibt den Zeitraum zwischen dem Eintritt einer Workflowdienstinstanz in den Leerlauf und der Beibehaltung der Workflowdienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="b84dc-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="b84dc-113">Der Standardwert für `timeToUnload` beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="b84dc-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="b84dc-114">Der Standardwert für `timeToPersist` lautet <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="b84dc-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="b84dc-115">Wenn im Leerlauf befindliche Instanzen im Arbeitsspeicher, aber aus Gründen der Stabilität beibehalten werden sollen, legen Sie die Werte so fest, dass Folgendes zutrifft: `timeToPersist` < `timeToUnload`.</span><span class="sxs-lookup"><span data-stu-id="b84dc-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="b84dc-116">Um zu verhindern, dass im Leerlauf befindliche Instanzen entladen werden, legen Sie `timeToUnload` auf <xref:System.TimeSpan.MaxValue>fest.</span><span class="sxs-lookup"><span data-stu-id="b84dc-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="b84dc-117">Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, finden Sie unter [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="b84dc-117">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b84dc-118">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="b84dc-118">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="b84dc-119">Weitere Informationen finden Sie unter [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="b84dc-119">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="b84dc-120">So ändern Sie Leerlaufverhalten in Code</span><span class="sxs-lookup"><span data-stu-id="b84dc-120">To change idle behavior in code</span></span>  
  
-   <span data-ttu-id="b84dc-121">Im folgenden Beispiel wird die Wartezeit bis zum programmgesteuerten Beibehalten und Entladen geändert.</span><span class="sxs-lookup"><span data-stu-id="b84dc-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b84dc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b84dc-122">See also</span></span>

- [<span data-ttu-id="b84dc-123">Erweiterbarkeit des Workflowdiensthosts</span><span class="sxs-lookup"><span data-stu-id="b84dc-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="b84dc-124">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b84dc-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="b84dc-125">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="b84dc-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
