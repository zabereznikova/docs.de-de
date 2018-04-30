---
title: 'Vorgehensweise: Konfigurieren des Leerlaufverhaltens mit WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22c71c0840b4fa44c585dfac4d99bdcbb3227fdb
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a>Vorgehensweise: Konfigurieren des Leerlaufverhaltens mit WorkflowServiceHost
Workflows wechseln in den Leerlaufzustand, sobald sie auf ein Lesezeichen treffen, das zum Fortsetzen einen externen Anstoß erfordert, z. B. wenn die Workflowinstanz per <xref:System.ServiceModel.Activities.Receive> auf die Übermittlung einer Nachricht wartet. Das<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> ist ein Verhalten, mit dem Sie die Dauer des Zeitraums zwischen dem Eintritt einer Dienstinstanz in den Leerlauf und der Beibehaltung oder Entladung einer Dienstinstanz angeben können. Es enthält zwei Eigenschaften, mit denen Sie diese Zeitspannen festlegen können. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> gibt die Zeitspanne zwischen dem Eintritt einer Workflowdienstinstanz in den Leerlauf und dem Zeitpunkt der Beibehaltung der Workflowdienstinstanz an. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> gibt die Zeitspanne zwischen dem Eintritt einer Workflowdienstinstanz in den Leerlauf und dem Zeitpunkt der Entladung der Workflowdienstinstanz an. Die Entladung bedeutet in diesem Fall, dass die Instanz im Instanzspeicher beibehalten und aus dem Arbeitsspeicher entfernt wird. In diesem Thema wird erklärt, wie Sie das <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> -Verhalten in einer Konfigurationsdatei konfigurieren.  
  
### <a name="to-configure-workflowidlebehavior"></a>So konfigurieren Sie WorkflowIdleBehavior  
  
1.  Hinzufügen einer <`workflowIdle`>-Elements auf der <`behavior`> Element innerhalb der <`serviceBehaviors`> Element, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Das `timeToUnload` -Attribut gibt den Zeitraum zwischen dem Eintritt einer Workflowdienstinstanz in den Leerlauf und der Entladung des Workflowdiensts an. Das `timeToPersist` -Attribut gibt den Zeitraum zwischen dem Eintritt einer Workflowdienstinstanz in den Leerlauf und der Beibehaltung der Workflowdienstinstanz an. Der Standardwert für `timeToUnload` beträgt 1 Minute. Der Standardwert für `timeToPersist` lautet <xref:System.TimeSpan.MaxValue>. Wenn im Leerlauf befindliche Instanzen im Arbeitsspeicher, aber aus Gründen der Stabilität beibehalten werden sollen, legen Sie die Werte so fest, dass Folgendes zutrifft: `timeToPersist` < `timeToUnload`. Um zu verhindern, dass im Leerlauf befindliche Instanzen entladen werden, legen Sie `timeToUnload` auf <xref:System.TimeSpan.MaxValue>fest. Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, finden Sie unter [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
  
    > [!NOTE]
    >  Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet. Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
### <a name="to-change-idle-behavior-in-code"></a>So ändern Sie Leerlaufverhalten in Code  
  
-   Im folgenden Beispiel wird die Wartezeit bis zum programmgesteuerten Beibehalten und Entladen geändert.  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
