---
title: Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: ee9aaaae80f213f026a222ac1754ae8b4fdf2d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517042"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
Windows Workflow Foundation (WF) können Sie verfolgen, workflowbezogene Informationen, um Details in die Ausführung eines Windows Workflow Foundation-Anwendung oder Dienst zu gewähren. Windows Workflow Foundation-Hosts können Workflowereignisse während der Ausführung einer Workflowinstanz erfassen. Wenn der Workflow Fehler oder Ausnahmen generiert, können Sie die Windows Workflow Foundation-Details zur Problembehandlung bei deren Verarbeitung nachverfolgt.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Problembehandlung von WF mit der WF-Überwachung  
 Um Fehler bei der Verarbeitung einer Windows Workflow Foundation-Aktivität zu erkennen, können Sie Aktivieren der nachverfolgung mit einem Überwachungsprofil, das eine Abfrage für ein <xref:System.Activities.Tracking.ActivityStateRecord> mit dem Status der Faulted. Die entsprechende Abfrage ist im folgenden Code angegeben.  
  
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
  
 Wenn eine Workflowinstanz eine nicht behandelte Ausnahme trifft eine <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> Objekt wird ausgegeben, wenn die Windows Workflow Foundation-Überwachung aktiviert wurde.  
  
 Dieser Überwachungsdatensatz enthält die Fehlerdetails in Form des Ausnahmestapels. Er verfügt über die Details der Quelle des Fehlers (z. B. die Aktivität), die einen Fehler verursacht, und in der nicht behandelten Ausnahme geführt hat. Um Fehlerereignisse aus einer Windows Workflow Foundation zu abonnieren, aktivieren Sie Überwachung, indem ein Nachverfolgungsteilnehmer hinzugefügt. Konfigurieren Sie diesen Teilnehmer mit einem Überwachungsprofil, das `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> und `WorkflowInstanceQuery (state="UnhandledException")` abfragt.  
  
 Wenn die Überwachung mit dem ETW-Überwachungsteilnehmer aktiviert wurde, werden die Fehlerereignisse an eine ETW-Sitzung ausgegeben. Die Ereignisse können mit der Ereignisanzeige angezeigt werden. Diese finden Sie unter dem Knoten **Ereignisanzeige -> Anwendungen und Dienstprotokolle -> Microsoft -> Windows -> Anwendungsserver-Anwendungen** im analytischen Kanal.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Server App Fabric-Überwachung](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)
