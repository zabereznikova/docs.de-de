---
title: 'Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 3881d1af21dcc0c211c6738162360e522648d949
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593593"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="7f49f-102">Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="7f49f-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="7f49f-103">Das <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist ein Verhalten, über das Sie die Aktion angeben können, die ausgeführt wird, wenn eine nicht behandelte Ausnahme innerhalb eines unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflows auftritt.</span><span class="sxs-lookup"><span data-stu-id="7f49f-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="7f49f-104">In diesem Thema wird erläutert, wie Sie dieses Verhalten in einer Konfigurationsdatei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7f49f-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="7f49f-105">So konfigurieren Sie WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="7f49f-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="7f49f-106">Fügen Sie ein <`workflowUnhandledException`>-Element in einem <`behavior`> Element innerhalb eines <>-Elements hinzu. verwenden Sie dabei `serviceBehaviors` das-Attribut, `action` um die Aktion anzugeben, die ausgeführt werden soll, wenn eine nicht behandelte Ausnahme auftritt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f49f-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    > <span data-ttu-id="7f49f-107">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f49f-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="7f49f-108">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7f49f-108">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="7f49f-109">Dieses Verhalten kann im Code konfiguriert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f49f-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="7f49f-110">Das- `action` Attribut des <`workflowUnhandledException`>-Elements kann auf einen der folgenden Werte festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="7f49f-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="7f49f-111">**heit**</span><span class="sxs-lookup"><span data-stu-id="7f49f-111">**abandon**</span></span>  
     <span data-ttu-id="7f49f-112">Bricht die Instanz im Arbeitsspeicher ab, ohne den beibehaltenen Instanzzustand (also Rollback zum letzten Beibehaltungspunkt) zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7f49f-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="7f49f-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="7f49f-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="7f49f-114">Bricht die Instanz im Arbeitsspeicher ab und aktualisiert die beibehaltene Instanz, die angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f49f-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="7f49f-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="7f49f-115">**cancel**</span></span>  
     <span data-ttu-id="7f49f-116">Ruft Abbruchhandler für die Instanz auf und schließt dann die Instanz im Arbeitsspeicher ab, wobei diese ggf. auch aus dem Instanzspeicher entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="7f49f-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="7f49f-117">**aufzu**</span><span class="sxs-lookup"><span data-stu-id="7f49f-117">**terminate**</span></span>  
     <span data-ttu-id="7f49f-118">Schließt die Instanz im Arbeitsspeicher ab und entfernt diese aus dem Instanzspeicher.</span><span class="sxs-lookup"><span data-stu-id="7f49f-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="7f49f-119">Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> finden Sie unter [Erweiterbarkeit des Workflow Dienst Hosts](workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="7f49f-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f49f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f49f-120">See also</span></span>

- [<span data-ttu-id="7f49f-121">Erweiterbarkeit des Workflowdiensthosts</span><span class="sxs-lookup"><span data-stu-id="7f49f-121">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)
- [<span data-ttu-id="7f49f-122">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="7f49f-122">Workflow Services</span></span>](workflow-services.md)
