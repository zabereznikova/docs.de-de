---
title: Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: f991533b61705c8d0a1a8e71b632dd53f24dd979
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43724911"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
Windows Workflow Foundation (WF) ermöglicht Ihnen, workflowbezogene Informationen, um Details zur Ausführung eines Windows Workflow Foundation-Anwendung oder Dienst geben zu verfolgen. Windows Workflow Foundation-Hosts können Workflowereignisse während der Ausführung einer Workflowinstanz erfassen. Wenn der Workflow Fehler oder Ausnahmen generiert, können Sie die Windows Workflow Foundation, Nachverfolgen von Details für die Problembehandlung von der Verarbeitung.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Problembehandlung von WF mit der WF-Überwachung  
 Um Fehler bei der Verarbeitung einer Windows Workflow Foundation-Aktivität zu erkennen, können Sie Aktivieren der nachverfolgung mit einem Überwachungsprofil, das für Abfragen eine <xref:System.Activities.Tracking.ActivityStateRecord> mit dem Zustand Faulted durchführt. Die entsprechende Abfrage ist im folgenden Code angegeben.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Wenn ein Fehler weitergegeben und in einem Fehlerhandler behandelt wird (z. B. eine <xref:System.Activities.Statements.TryCatch>-Aktivität), kann dies mit einem <xref:System.Activities.Tracking.FaultPropagationRecord> erkannt werden kann. Der <xref:System.Activities.Tracking.FaultPropagationRecord> zeigt die Quellaktivität des Fehlers und den Namen des Fehlerhandlers an. Der <xref:System.Activities.Tracking.FaultPropagationRecord> enthält Fehlerdetails in Form des Ausnahmestapels für den Fehler. Die Abfrage zum Abonnieren eines <xref:System.Activities.Tracking.FaultPropagationRecord> lautet:  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 Wenn ein Fehler nicht innerhalb des Workflows behandelt wird, führt er zu einer nicht behandelten Ausnahme der Workflowinstanz, und die Workflowinstanz wird abgebrochen. Um die Details der nicht behandelten Ausnahme zu verstehen, muss das Überwachungsprofil eine Abfrage des Workflowinstanz-Datensatzes nach `state name="UnhandledException"` ausführen, wie im folgenden Beispiel angegeben.  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 Wenn eine Workflowinstanz eine nicht behandelte Ausnahme auftritt, wird eine <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> Objekt wird ausgegeben, wenn die Windows Workflow Foundation-nachverfolgung aktiviert wurde.  
  
 Dieser Überwachungsdatensatz enthält die Fehlerdetails in Form des Ausnahmestapels. Er verfügt über die Details der Quelle des Fehlers (z. B. die Aktivität), die einen Fehler verursacht, und der nicht behandelten Ausnahme geführt hat. Aktivieren Sie zum Abonnieren von Fehlerereignisse aus einer Windows Workflow Foundation, Überwachung, indem ein Nachverfolgungsteilnehmer hinzugefügt. Konfigurieren Sie diesen Teilnehmer mit einem Überwachungsprofil, das `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> und `WorkflowInstanceQuery (state="UnhandledException")` abfragt.  
  
 Wenn die Überwachung mit dem ETW-Überwachungsteilnehmer aktiviert wurde, werden die Fehlerereignisse an eine ETW-Sitzung ausgegeben. Die Ereignisse können mit der Ereignisanzeige angezeigt werden. Diese befindet sich unter dem Knoten **Ereignisanzeige -> Anwendungen und Dienstprotokolle > Microsoft -> Windows-Anwendungsserver-Anwendungen >** im analytischen Kanal.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Server App Fabric-Überwachung](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Überwachen von Anwendungen mit AppFabric](https://go.microsoft.com/fwlink/?LinkId=201275)
