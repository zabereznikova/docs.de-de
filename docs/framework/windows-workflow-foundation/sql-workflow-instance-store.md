---
title: SQL-Workflowinstanzspeicher
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 638ad75155bae30f3cd1d126d27e8e0542026ab0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="sql-workflow-instance-store"></a>SQL-Workflowinstanzspeicher
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] enthält den SQL-Workflowinstanzspeicher, mit dem Workflows die Zustandsinformationen zu Workflowinstanzen in einer Datenbank von SQL Server 2005 oder SQL Server 2008 speichern können. Diese Funktion wird hauptsächlich in Form der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Klasse implementiert, die von der abstrakten <xref:System.Runtime.DurableInstancing.InstanceStore>-Klasse des Persistenzframeworks abgeleitet wird. Die Funktion SQL-Workflowinstanzspeicher besteht aus einem SQL-Persistenzanbieter, der eine konkrete Implementierung der Persistenz-API darstellt, mit der ein Host Persistenzbefehle an den Speicher sendet.  
  
 Der SQL-Workflowinstanzspeicher unterstützt selbst gehostete Workflows oder Workflowdienste, die die <xref:System.Activities.WorkflowApplication> verwenden, oder den <xref:System.ServiceModel.WorkflowServiceHost> sowie Dienste, die mit <xref:System.ServiceModel.WorkflowServiceHost> in WAS gehostet werden. Sie können die Funktion SQL-Workflowinstanzspeicher für selbst gehostete Dienste programmgesteuert konfigurieren. Verwenden Sie dazu das Objektmodell, das von der Funktion bereitgestellt wird. Sie können diese Funktion für Dienste konfigurieren, die vom <xref:System.ServiceModel.WorkflowServiceHost> programmgesteuert über das Objektmodell und mithilfe einer XML-Konfigurationsdatei gehostet werden.  
  
 Die SQL-Workflowinstanzspeicher-Funktion (**SqlWorkflowInstanceStore** Klasse) implementiert nicht <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> und bieten somit keine persistenzunterstützung für permanente WCF-Dienste von außerhalb des Workflows. Außerdem implementiert er auch den <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> nicht und bietet somit keine Persistenzunterstützung für 3.x-Workflows. Die Funktion unterstützt Persistenz nur für Workflows und Workflowdienste für WF 4.0 (und höher). Die Funktion unterstützt ausschließlich SQL Server 2005-Datenbanken und SQL Server 2008-Datenbanken.  
  
 In den Themen in diesem Abschnitt werden die Eigenschaften und Funktionen des SQL-Workflowinstanzspeichers beschrieben, und Sie finden Informationen zum Konfigurieren des Speichers.  
  
 Windows Server AppFabric stellt einen eigenen Instanzspeicher und eigene Tools bereit, um die Konfiguration und die Verwendung des Instanzspeichers zu vereinfachen. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]finden Sie unter [Windows Server AppFabric-Instanzspeicher](http://go.microsoft.com/fwlink/?LinkId=201201). [!INCLUDE[crabout](../../../includes/crabout-md.md)]die App Fabric SQL Server-Persistenzdatenbank finden Sie unter [App Fabric SQL Server-Persistenzdatenbank](http://go.microsoft.com/fwlink/?LinkId=201202)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Eigenschaften des SQL-Workflowinstanzspeichers](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [Vorgehensweise: Aktivieren der SQL-Persistenz für Workflows und Workflowdienste](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [Instanzaktivierung](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [Unterstützung für Abfragen](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [Erweiterbarkeit des Speichers](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [Sicherheit](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [SQL Server-Persistenzdatenbank](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkID=177735)
