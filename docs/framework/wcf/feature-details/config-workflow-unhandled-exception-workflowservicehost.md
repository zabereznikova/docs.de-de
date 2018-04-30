---
title: 'Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b3d42e51ed7a0a57deb392f5728f407909b00
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="785fa-102">Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="785fa-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="785fa-103">Das <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist ein Verhalten, über das Sie die Aktion angeben können, die ausgeführt wird, wenn eine nicht behandelte Ausnahme innerhalb eines unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflows auftritt.</span><span class="sxs-lookup"><span data-stu-id="785fa-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="785fa-104">In diesem Thema wird erläutert, wie Sie dieses Verhalten in einer Konfigurationsdatei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="785fa-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="785fa-105">So konfigurieren Sie WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="785fa-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="785fa-106">Hinzufügen eine <`workflowUnhandledException`> Element in ein <`behavior`> Element innerhalb einer <`serviceBehaviors`>-Element, mit der `action` -Attribut angeben, die Aktion an, wenn eine nicht behandelte Ausnahme auftritt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="785fa-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="785fa-107">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="785fa-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="785fa-108">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="785fa-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="785fa-109">Dieses Verhalten kann im Code konfiguriert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="785fa-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="785fa-110">Die `action` Attribut von der <`workflowUnhandledException`>-Element kann auf einen der folgenden Werte festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="785fa-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="785fa-111">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="785fa-111">**abandon**</span></span>  
     <span data-ttu-id="785fa-112">Bricht die Instanz im Arbeitsspeicher ab, ohne den beibehaltenen Instanzzustand (also Rollback zum letzten Beibehaltungspunkt) zu ändern.</span><span class="sxs-lookup"><span data-stu-id="785fa-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="785fa-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="785fa-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="785fa-114">Bricht die Instanz im Arbeitsspeicher ab und aktualisiert die beibehaltene Instanz, die angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="785fa-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="785fa-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="785fa-115">**cancel**</span></span>  
     <span data-ttu-id="785fa-116">Ruft Abbruchhandler für die Instanz auf und schließt dann die Instanz im Arbeitsspeicher ab, wobei diese ggf. auch aus dem Instanzspeicher entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="785fa-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="785fa-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="785fa-117">**terminate**</span></span>  
     <span data-ttu-id="785fa-118">Schließt die Instanz im Arbeitsspeicher ab und entfernt diese aus dem Instanzspeicher.</span><span class="sxs-lookup"><span data-stu-id="785fa-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="785fa-119">Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, finden Sie unter [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="785fa-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785fa-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="785fa-120">See Also</span></span>  
 [<span data-ttu-id="785fa-121">Erweiterbarkeit des Workflowdiensthosts</span><span class="sxs-lookup"><span data-stu-id="785fa-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="785fa-122">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="785fa-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
