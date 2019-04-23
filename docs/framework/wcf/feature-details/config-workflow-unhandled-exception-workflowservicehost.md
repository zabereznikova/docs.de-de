---
title: 'Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: cd3729019b5371b5313bba3814758c723c0d448a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318745"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost
Das <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist ein Verhalten, über das Sie die Aktion angeben können, die ausgeführt wird, wenn eine nicht behandelte Ausnahme innerhalb eines unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflows auftritt. In diesem Thema wird erläutert, wie Sie dieses Verhalten in einer Konfigurationsdatei konfigurieren.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>So konfigurieren Sie WorkflowUnhandledExceptionBehavior  
  
1. Hinzufügen eine <`workflowUnhandledException`> Element in ein <`behavior`> Element innerhalb einer <`serviceBehaviors`>-Element, mit der `action` Attribut gibt die Aktion an, wenn eine nicht behandelte Ausnahme auftritt, wie im folgenden Beispiel gezeigt.  
  
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
    >  Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet. Weitere Informationen finden Sie unter [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Dieses Verhalten kann im Code konfiguriert werden, wie im folgenden Beispiel gezeigt.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     Die `action` -Attribut der <`workflowUnhandledException`>-Element kann auf einen der folgenden Werte festgelegt:  
  
     **abandon**  
     Bricht die Instanz im Arbeitsspeicher ab, ohne den beibehaltenen Instanzzustand (also Rollback zum letzten Beibehaltungspunkt) zu ändern.  
  
     **abandonAndSuspend**  
     Bricht die Instanz im Arbeitsspeicher ab und aktualisiert die beibehaltene Instanz, die angehalten werden soll.  
  
     **cancel**  
     Ruft Abbruchhandler für die Instanz auf und schließt dann die Instanz im Arbeitsspeicher ab, wobei diese ggf. auch aus dem Instanzspeicher entfernt wird.  
  
     **terminate**  
     Schließt die Instanz im Arbeitsspeicher ab und entfernt diese aus dem Instanzspeicher.  
  
     Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, finden Sie unter [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
