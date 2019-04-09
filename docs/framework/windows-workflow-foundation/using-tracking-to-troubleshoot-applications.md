---
title: Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 62c46ca36c89c023bfc775eb76ba454c9a4162c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142063"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="ad841-102">Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="ad841-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="ad841-103">Windows Workflow Foundation (WF) ermöglicht Ihnen, workflowbezogene Informationen, um Details zur Ausführung eines Windows Workflow Foundation-Anwendung oder Dienst geben zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ad841-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="ad841-104">Windows Workflow Foundation-Hosts können Workflowereignisse während der Ausführung einer Workflowinstanz erfassen.</span><span class="sxs-lookup"><span data-stu-id="ad841-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="ad841-105">Wenn der Workflow Fehler oder Ausnahmen generiert, können Sie die Windows Workflow Foundation, Nachverfolgen von Details für die Problembehandlung von der Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="ad841-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="ad841-106">Problembehandlung von WF mit der WF-Überwachung</span><span class="sxs-lookup"><span data-stu-id="ad841-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="ad841-107">Um Fehler bei der Verarbeitung einer Windows Workflow Foundation-Aktivität zu erkennen, können Sie Aktivieren der nachverfolgung mit einem Überwachungsprofil, das für Abfragen eine <xref:System.Activities.Tracking.ActivityStateRecord> mit dem Zustand Faulted durchführt.</span><span class="sxs-lookup"><span data-stu-id="ad841-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="ad841-108">Die entsprechende Abfrage ist im folgenden Code angegeben.</span><span class="sxs-lookup"><span data-stu-id="ad841-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="ad841-109">Wenn ein Fehler weitergegeben und in einem Fehlerhandler behandelt wird (z. B. eine <xref:System.Activities.Statements.TryCatch>-Aktivität), kann dies mit einem <xref:System.Activities.Tracking.FaultPropagationRecord> erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad841-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="ad841-110">Der <xref:System.Activities.Tracking.FaultPropagationRecord> zeigt die Quellaktivität des Fehlers und den Namen des Fehlerhandlers an.</span><span class="sxs-lookup"><span data-stu-id="ad841-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="ad841-111">Der <xref:System.Activities.Tracking.FaultPropagationRecord> enthält Fehlerdetails in Form des Ausnahmestapels für den Fehler. Die Abfrage zum Abonnieren eines <xref:System.Activities.Tracking.FaultPropagationRecord> lautet:</span><span class="sxs-lookup"><span data-stu-id="ad841-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="ad841-112">Wenn ein Fehler nicht innerhalb des Workflows behandelt wird, führt er zu einer nicht behandelten Ausnahme der Workflowinstanz, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="ad841-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="ad841-113">Um die Details der nicht behandelten Ausnahme zu verstehen, muss das Überwachungsprofil eine Abfrage des Workflowinstanz-Datensatzes nach `state name="UnhandledException"` ausführen, wie im folgenden Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="ad841-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="ad841-114">Wenn eine Workflowinstanz eine nicht behandelte Ausnahme auftritt, wird eine <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> Objekt wird ausgegeben, wenn die Windows Workflow Foundation-nachverfolgung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="ad841-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="ad841-115">Dieser Überwachungsdatensatz enthält die Fehlerdetails in Form des Ausnahmestapels.</span><span class="sxs-lookup"><span data-stu-id="ad841-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="ad841-116">Er verfügt über die Details der Quelle des Fehlers (z. B. die Aktivität), die einen Fehler verursacht, und der nicht behandelten Ausnahme geführt hat. Aktivieren Sie zum Abonnieren von Fehlerereignisse aus einer Windows Workflow Foundation, Überwachung, indem ein Nachverfolgungsteilnehmer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ad841-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="ad841-117">Konfigurieren Sie diesen Teilnehmer mit einem Überwachungsprofil, das `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> und `WorkflowInstanceQuery (state="UnhandledException")` abfragt.</span><span class="sxs-lookup"><span data-stu-id="ad841-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="ad841-118">Wenn die Überwachung mit dem ETW-Überwachungsteilnehmer aktiviert wurde, werden die Fehlerereignisse an eine ETW-Sitzung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad841-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="ad841-119">Die Ereignisse können mit der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ad841-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="ad841-120">Diese befindet sich unter dem Knoten **Ereignisanzeige -> Anwendungen und Dienstprotokolle > Microsoft -> Windows-Anwendungsserver-Anwendungen >** im analytischen Kanal.</span><span class="sxs-lookup"><span data-stu-id="ad841-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad841-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad841-121">See also</span></span>

- [<span data-ttu-id="ad841-122">Windows Server App Fabric-Überwachung</span><span class="sxs-lookup"><span data-stu-id="ad841-122">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="ad841-123">Überwachen von Anwendungen mit AppFabric</span><span class="sxs-lookup"><span data-stu-id="ad841-123">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
