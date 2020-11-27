---
title: Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 62f2240831dd33bdaf78655199aad75b7e29c59c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293571"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Verwenden der Nachverfolgung zum Beheben von Anwendungsfehlern

Mit Windows Workflow Foundation (WF) können Sie Workflow bezogene Informationen nachverfolgen, um Details zur Ausführung einer Windows Workflow Foundation Anwendung oder eines Dienstanbieter zu erhalten. Windows Workflow Foundation Hosts können Workflow Ereignisse während der Ausführung einer Workflow Instanz erfassen. Wenn der Workflow Fehler oder Ausnahmen generiert, können Sie die Windows Workflow Foundation nach Verfolgungs Details zur Problembehandlung der Verarbeitung verwenden.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Problembehandlung von WF mit der WF-Überwachung  

 Um Fehler während der Verarbeitung einer Windows Workflow Foundation Aktivität zu erkennen, können Sie die Überwachung mit einem Überwachungs Profil aktivieren, das eine Abfrage für einen <xref:System.Activities.Tracking.ActivityStateRecord> mit dem Zustand "Faulted" durchgeführt hat. Die entsprechende Abfrage ist im folgenden Code angegeben.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Wenn ein Fehler weitergegeben und in einem Fehlerhandler behandelt wird (z. B. eine <xref:System.Activities.Statements.TryCatch>-Aktivität), kann dies mit einem <xref:System.Activities.Tracking.FaultPropagationRecord> erkannt werden kann. Der <xref:System.Activities.Tracking.FaultPropagationRecord> zeigt die Quellaktivität des Fehlers und den Namen des Fehlerhandlers an. Der <xref:System.Activities.Tracking.FaultPropagationRecord> enthält Fehlerdetails in Form des Ausnahme Stapels für den Fehler. Die Abfrage, die für eine abonniert werden soll, <xref:System.Activities.Tracking.FaultPropagationRecord> wird im folgenden Beispiel gezeigt.  
  
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
  
 Wenn eine Workflow Instanz auf eine nicht behandelte Ausnahme stößt, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> wird ein-Objekt ausgegeben, wenn Windows Workflow Foundation Nachverfolgung aktiviert wurde.  
  
 Dieser Überwachungsdatensatz enthält die Fehlerdetails in Form des Ausnahmestapels. Es enthält Details zur Fehlerquelle (z. b. die-Aktivität), die einen Fehler verursacht hat und zu der nicht behandelten Ausnahme geführt hat. Aktivieren Sie zum Abonnieren von Fehlerereignissen aus einer Windows Workflow Foundation die Überwachung, indem Sie einen nach Verfolgungs Teilnehmer hinzufügen. Konfigurieren Sie diesen Teilnehmer mit einem Überwachungsprofil, das `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> und `WorkflowInstanceQuery (state="UnhandledException")` abfragt.  
  
 Wenn die Überwachung mit dem ETW-Überwachungsteilnehmer aktiviert wurde, werden die Fehlerereignisse an eine ETW-Sitzung ausgegeben. Die Ereignisse können mit der Ereignisanzeige angezeigt werden. Diese finden Sie unter dem Knoten **Ereignisanzeige->Anwendungs-und Dienst Protokolle->Microsoft->Windows->Anwendungs Servers-Anwendungen** im analytischen Kanal.  
  
## <a name="see-also"></a>Weitere Informationen

- [Windows Server-App-Fabric-Überwachung](/previous-versions/appfabric/ee677251(v=azure.10))
- [Überwachen von Anwendungen mit App-Fabric](/previous-versions/appfabric/ee677276(v=azure.10))
