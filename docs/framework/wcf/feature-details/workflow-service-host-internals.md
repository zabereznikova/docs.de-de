---
title: Interne Funktionsweise des Workflowdiensthosts
ms.date: 03/30/2017
ms.assetid: af44596f-bf6a-4149-9f04-08d8e8f45250
ms.openlocfilehash: 0596e15e27460a08f859ec3398afbeae752c86fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826027"
---
# <a name="workflow-service-host-internals"></a>Interne Funktionsweise des Workflowdiensthosts
<xref:System.ServiceModel.WorkflowServiceHost> stellt einen Host für Workflowdienste bereit. Der Host lauscht unter anderem auf eingehende Meldungen, leitet sie an die entsprechende Workflowdienstinstanz weiter und kontrolliert das Entladen und Beibehalten von Workflows. In diesem Thema wird beschrieben, wie eingehende Meldungen vom WorkflowServiceHost verarbeitet werden.  
  
## <a name="workflowservicehost-overview"></a>Übersicht über WorkflowServiceHost  

Mit der <xref:System.ServiceModel.WorkflowServiceHost>-Klasse werden Workflowdienste gehostet. Die Klasse lauscht auf eingehende Meldungen und leitet diese an die entsprechende Dienstinstanz weiter, erstellt neue Dienstinstanzen oder lädt vorhandene Instanzen bei Bedarf aus dem permanenten Speicher. Das folgende Diagramm veranschaulicht, auf die allgemeine Funktionsweise <xref:System.ServiceModel.WorkflowServiceHost> funktioniert: 
  
 ![Diagramm eine Übersicht über den Workflowdiensthost zeigt.](./media/workflow-service-host-internals/workflow-service-host-high-level-overview.gif)  
  
 Das Diagramm zeigt, dass Workflowdienstdefinitionen von <xref:System.ServiceModel.WorkflowServiceHost> aus XAMLX-Dateien und Konfigurationsinformationen aus einer Konfigurationsdatei geladen werden. Außerdem wird eine Überwachungskonfiguration aus dem Überwachungsprofil geladen. <xref:System.ServiceModel.WorkflowServiceHost> macht einen Workflowsteuerungsendpunkt verfügbar, mit dem Sie Steuerungsvorgänge an Workflowinstanzen senden können.  Weitere Informationen finden Sie unter [Workflowsteuerungsendpunkt Beispiel](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md).  
  
 <xref:System.ServiceModel.WorkflowServiceHost> macht darüber hinaus Anwendungsendpunkte zum Lauschen auf eingehende Meldungen verfügbar. Eingehende Meldungen werden an die entsprechende Workflowdienstinstanz gesendet (sofern diese aktuell geladen ist). Bei Bedarf wird eine neue Workflowinstanz erstellt. Wenn eine vorhandene Instanz beibehalten wurde, wird diese aus dem Persistenzspeicher geladen.  
  
## <a name="workflowservicehost-details"></a>Details zum WorkflowServiceHost  
 Das folgende Diagramm zeigt, wie <xref:System.ServiceModel.WorkflowServiceHost> Nachrichten im Detail behandelt:  
  
 ![Diagramm den Nachrichtenfluss Workflowdiensthost zeigt.](./media/workflow-service-host-internals/workflow-service-host-message-flow.gif)  
  
 Das Diagramm enthält drei verschiedene Endpunkte: einen Anwendungsendpunkt, einen Workflowsteuerungsendpunkt sowie einen Workflowhostingendpunkt. Der Anwendungsendpunkt empfängt Meldungen für eine spezifische Workflowinstanz. Der Workflowsteuerungsendpunkt lauscht auf Steuerungsvorgänge. Der Workflowhostingendpunkt lauscht auf Meldungen, die bewirken, dass <xref:System.ServiceModel.WorkflowServiceHost> geladen wird und Workflows ausgeführt werden, die keine Dienstworkflows sind. Alle Meldungen werden, wie im Diagramm gezeigt, von der WCF-Laufzeit verarbeitet.  Die Einschränkung von Workflowdienstinstanzen wird mit der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft erreicht. Diese Eigenschaft schränkt die Anzahl von gleichzeitigen Workflowdienstinstanzen ein. Wenn diese Drosselung überschritten wird, werden zusätzliche Anforderungen für neue Workflowdienstinstanzen oder Anforderungen zum Aktivieren beibehaltener Workflowinstanzen in einer Warteschlange gespeichert. Die in der Warteschlange gespeicherten Anforderungen werden in FIFO-Reihenfolge verarbeitet, unabhängig davon, ob sie Anforderungen für eine neue Instanz oder eine ausgeführte, beibehaltene Instanz sind. Hostrichtlinieninformationen werden geladen, um festzulegen, wie Ausnahmefehler gehandhabt und Workflowdienste im Leerlauf entladen und beibehalten werden. Weitere Informationen zu diesen Themen finden Sie unter [Vorgehensweise: Konfigurieren der Workflow nicht behandelte Ausnahmeverhalten mit WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/config-workflow-unhandled-exception-workflowservicehost.md) und [Vorgehensweise: Konfigurieren des Leerlaufverhaltens mit WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/how-to-configure-idle-behavior-with-workflowservicehost.md). Workflowinstanzen werden gemäß den Hostrichtlinien beibehalten und bei Bedarf erneut geladen. Weitere Informationen zum Workflow Persistenz finden Sie unter: [Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/how-to-configure-persistence-with-workflowservicehost.md), [zum Erstellen eines Workflowdiensts langer](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md), und [Workflowpersistenz](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md).  
  
 Die folgende Abbildung zeigt den Datenfluss aus, wenn von WorkflowServiceHost.Open:  
  
 ![Diagramm, das den Flow zeigt an, wenn von WorkflowServiceHost.Open.](./media/workflow-service-host-internals/workflow-service-host-open.gif)  
  
 Der Workflow wird aus XAML geladen, und die Aktivitätsstruktur wird erstellt. <xref:System.ServiceModel.WorkflowServiceHost> durchläuft die Aktivitätsstruktur und erstellt die Dienstbeschreibung. Die Konfiguration wird auf den Host angewendet. Abschließend beginnt der Host mit dem Lauschen auf eingehende Meldungen.  
  
 Die folgende Abbildung zeigt, was die <xref:System.ServiceModel.WorkflowServiceHost> ist beim Empfang einer Meldung für eine Receive-Aktivität, die CanCreateInstance auf festgelegt `true`:  
  
 ![Entscheidungsstruktur, die von der WF-Host verwendet werden, beim Empfangen einer Meldung und deren CanCreateInstance auf true festgelegt ist.](./media/workflow-service-host-internals/workflow-service-host-receive-message-cancreateinstance.gif)  
  
 Die Meldung wird empfangen und vom WCF-Kanalstapel verarbeitet. Drosselungen werden überprüft und Korrelationsabfragen ausgeführt. Wenn die Meldung an eine vorhandene Instanz gerichtet ist, wird sie übermittelt. Wenn eine neue Instanz erstellt werden muss, wird die Receive-Aktivität der CanCreateInstance-Eigenschaft überprüft. Wenn die Eigenschaft auf True festgelegt ist, wird eine neue Instanz erstellt, und die Meldung wird übermittelt.  
  
 In der folgenden Abbildung wird die Vorgehensweise von <xref:System.ServiceModel.WorkflowServiceHost> beim Empfangen einer Meldung für eine Receive-Aktivität veranschaulicht, deren CanCreateInstance auf False festgelegt ist.  
  
 ![Entscheidungsstruktur, die von der WF-Host verwendet werden, beim Empfangen einer Meldung und deren CanCreateInstance auf false festgelegt ist.](./media/workflow-service-host-internals/workflow-service-host-receive-message.gif)  
  
 Die Meldung wird empfangen und vom WCF-Kanalstapel verarbeitet. Drosselungen werden überprüft und Korrelationsabfragen ausgeführt. Die Meldung ist für eine vorhandene Instanz bestimmt (CanCreateInstance ist auf False festgelegt). Daher wird die Instanz aus dem Persistenzspeicher geladen, das Lesezeichen wird wiederaufgenommen, und der Workflow wird ausgeführt.  
  
> [!WARNING]
> Der Workflowdiensthost kann nicht geöffnet werden, wenn SQL Server nur zum Lauschen auf das NamedPipe-Protokoll konfiguriert wurde.  
  
## <a name="see-also"></a>Siehe auch

- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Hosten von Workflowdiensten](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)
- [Workflowsteuerungsendpunkt](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)
- [Vorgehensweise: Konfigurieren der Workflow nicht behandelte Ausnahmeverhalten mit WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/config-workflow-unhandled-exception-workflowservicehost.md)
- [Erstellen eines Workflowdiensts mit langer Ausführungszeit](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)
- [Workflowpersistenz](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
