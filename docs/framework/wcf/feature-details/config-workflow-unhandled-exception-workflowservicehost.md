---
title: 'Vorgehensweise: Konfigurieren der Workflow nicht behandelte Ausnahmeverhalten mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 9a13bb9390e891295491722898bd780bc1cac587
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636156"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Vorgehensweise: Konfigurieren der Workflow nicht behandelte Ausnahmeverhalten mit WorkflowServiceHost
Das <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist ein Verhalten, über das Sie die Aktion angeben können, die ausgeführt wird, wenn eine nicht behandelte Ausnahme innerhalb eines unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflows auftritt. In diesem Thema wird erläutert, wie Sie dieses Verhalten in einer Konfigurationsdatei konfigurieren.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>So konfigurieren Sie WorkflowUnhandledExceptionBehavior  
  
1.  Hinzufügen eine <`workflowUnhandledException`> Element in ein <`behavior`> Element innerhalb einer <`serviceBehaviors`>-Element, mit der `action` Attribut gibt die Aktion an, wenn eine nicht behandelte Ausnahme auftritt, wie im folgenden Beispiel gezeigt.  
  
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
