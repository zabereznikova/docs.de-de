---
title: Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: b64b92de9cb36807a2bf1eb7ff57f9f6e1a07156
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988932"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="64603-102">Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="64603-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="64603-103">Mit Windows Workflow Foundation (WF) können Sie Workflow bezogene Informationen nachverfolgen, um Details zur Ausführung einer Windows Workflow Foundation Anwendung oder eines Dienstanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="64603-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="64603-104">Windows Workflow Foundation Hosts können Workflow Ereignisse während der Ausführung einer Workflow Instanz erfassen.</span><span class="sxs-lookup"><span data-stu-id="64603-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="64603-105">Wenn der Workflow Fehler oder Ausnahmen generiert, können Sie die Windows Workflow Foundation nach Verfolgungs Details zur Problembehandlung der Verarbeitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="64603-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="64603-106">Problembehandlung von WF mit der WF-Überwachung</span><span class="sxs-lookup"><span data-stu-id="64603-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="64603-107">Um Fehler während der Verarbeitung einer Windows Workflow Foundation Aktivität zu erkennen, können Sie die Überwachung mit einem Überwachungs Profil aktivieren, das eine <xref:System.Activities.Tracking.ActivityStateRecord> Abfrage für einen mit dem Zustand "Faulted" durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="64603-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="64603-108">Die entsprechende Abfrage ist im folgenden Code angegeben.</span><span class="sxs-lookup"><span data-stu-id="64603-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="64603-109">Wenn ein Fehler weitergegeben und in einem Fehlerhandler behandelt wird (z. B. eine <xref:System.Activities.Statements.TryCatch>-Aktivität), kann dies mit einem <xref:System.Activities.Tracking.FaultPropagationRecord> erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="64603-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="64603-110">Der <xref:System.Activities.Tracking.FaultPropagationRecord> zeigt die Quellaktivität des Fehlers und den Namen des Fehlerhandlers an.</span><span class="sxs-lookup"><span data-stu-id="64603-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="64603-111">Der <xref:System.Activities.Tracking.FaultPropagationRecord> enthält Fehlerdetails in Form des Ausnahme Stapels für den Fehler.</span><span class="sxs-lookup"><span data-stu-id="64603-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.</span></span> <span data-ttu-id="64603-112">Die Abfrage, die für eine <xref:System.Activities.Tracking.FaultPropagationRecord> abonniert werden soll, wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="64603-112">The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="64603-113">Wenn ein Fehler nicht innerhalb des Workflows behandelt wird, führt er zu einer nicht behandelten Ausnahme der Workflowinstanz, und die Workflowinstanz wird abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="64603-113">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="64603-114">Um die Details der nicht behandelten Ausnahme zu verstehen, muss das Überwachungsprofil eine Abfrage des Workflowinstanz-Datensatzes nach `state name="UnhandledException"` ausführen, wie im folgenden Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="64603-114">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="64603-115">Wenn eine Workflow Instanz auf eine nicht behandelte Ausnahme stößt, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> wird ein-Objekt ausgegeben, wenn Windows Workflow Foundation Nachverfolgung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="64603-115">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="64603-116">Dieser Überwachungsdatensatz enthält die Fehlerdetails in Form des Ausnahmestapels.</span><span class="sxs-lookup"><span data-stu-id="64603-116">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="64603-117">Es enthält Details zur Fehlerquelle (z. b. die-Aktivität), die einen Fehler verursacht hat und zu der nicht behandelten Ausnahme geführt hat. Aktivieren Sie zum Abonnieren von Fehlerereignissen aus einer Windows Workflow Foundation die Überwachung, indem Sie einen nach Verfolgungs Teilnehmer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="64603-117">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="64603-118">Konfigurieren Sie diesen Teilnehmer mit einem Überwachungsprofil, das `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> und `WorkflowInstanceQuery (state="UnhandledException")` abfragt.</span><span class="sxs-lookup"><span data-stu-id="64603-118">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="64603-119">Wenn die Überwachung mit dem ETW-Überwachungsteilnehmer aktiviert wurde, werden die Fehlerereignisse an eine ETW-Sitzung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="64603-119">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="64603-120">Die Ereignisse können mit der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="64603-120">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="64603-121">Diese finden Sie unter dem Knoten **Ereignisanzeige-> Anwendungs-und Dienst Protokolle-> Microsoft-> Windows-> Anwendungs Servers-Anwendungen** im analytischen Kanal.</span><span class="sxs-lookup"><span data-stu-id="64603-121">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64603-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64603-122">See also</span></span>

- [<span data-ttu-id="64603-123">Windows Server-App-Fabric-Überwachung</span><span class="sxs-lookup"><span data-stu-id="64603-123">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="64603-124">Überwachen von Anwendungen mit App-Fabric</span><span class="sxs-lookup"><span data-stu-id="64603-124">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
