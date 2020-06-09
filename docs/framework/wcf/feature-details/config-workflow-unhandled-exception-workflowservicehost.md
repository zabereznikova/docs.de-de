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
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost
Das <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist ein Verhalten, über das Sie die Aktion angeben können, die ausgeführt wird, wenn eine nicht behandelte Ausnahme innerhalb eines unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflows auftritt. In diesem Thema wird erläutert, wie Sie dieses Verhalten in einer Konfigurationsdatei konfigurieren.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>So konfigurieren Sie WorkflowUnhandledExceptionBehavior  
  
1. Fügen Sie ein <`workflowUnhandledException`>-Element in einem <`behavior`> Element innerhalb eines <>-Elements hinzu. verwenden Sie dabei `serviceBehaviors` das-Attribut, `action` um die Aktion anzugeben, die ausgeführt werden soll, wenn eine nicht behandelte Ausnahme auftritt, wie im folgenden Beispiel gezeigt.  
  
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
    > Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet. Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md).  
  
     Dieses Verhalten kann im Code konfiguriert werden, wie im folgenden Beispiel gezeigt.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     Das- `action` Attribut des <`workflowUnhandledException`>-Elements kann auf einen der folgenden Werte festgelegt werden:  
  
     **heit**  
     Bricht die Instanz im Arbeitsspeicher ab, ohne den beibehaltenen Instanzzustand (also Rollback zum letzten Beibehaltungspunkt) zu ändern.  
  
     **abandonAndSuspend**  
     Bricht die Instanz im Arbeitsspeicher ab und aktualisiert die beibehaltene Instanz, die angehalten werden soll.  
  
     **cancel**  
     Ruft Abbruchhandler für die Instanz auf und schließt dann die Instanz im Arbeitsspeicher ab, wobei diese ggf. auch aus dem Instanzspeicher entfernt wird.  
  
     **aufzu**  
     Schließt die Instanz im Arbeitsspeicher ab und entfernt diese aus dem Instanzspeicher.  
  
     Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> finden Sie unter [Erweiterbarkeit des Workflow Dienst Hosts](workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterbarkeit des Workflowdiensthosts](workflow-service-host-extensibility.md)
- [Workflowdienste](workflow-services.md)
