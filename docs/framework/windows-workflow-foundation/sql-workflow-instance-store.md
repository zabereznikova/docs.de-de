---
title: SQL-Workflowinstanzspeicher
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 38cf83ebb8417009c6aa205aa29cd633d1232f0a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540231"
---
# <a name="sql-workflow-instance-store"></a>SQL-Workflowinstanzspeicher
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] enthält den SQL-Workflowinstanzspeicher, mit dem Workflows die Zustandsinformationen zu Workflowinstanzen in einer Datenbank von SQL Server 2005 oder SQL Server 2008 speichern können. Diese Funktion wird hauptsächlich in Form der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Klasse implementiert, die von der abstrakten <xref:System.Runtime.DurableInstancing.InstanceStore>-Klasse des Persistenzframeworks abgeleitet wird. Die Funktion SQL-Workflowinstanzspeicher besteht aus einem SQL-Persistenzanbieter, der eine konkrete Implementierung der Persistenz-API darstellt, mit der ein Host Persistenzbefehle an den Speicher sendet.  
  
 Der SQL-Workflowinstanzspeicher unterstützt selbst gehostete Workflows oder Workflowdienste, die die <xref:System.Activities.WorkflowApplication> verwenden, oder den <xref:System.ServiceModel.WorkflowServiceHost> sowie Dienste, die mit <xref:System.ServiceModel.WorkflowServiceHost> in WAS gehostet werden. Sie können die Funktion SQL-Workflowinstanzspeicher für selbst gehostete Dienste programmgesteuert konfigurieren. Verwenden Sie dazu das Objektmodell, das von der Funktion bereitgestellt wird. Sie können diese Funktion für Dienste konfigurieren, die vom <xref:System.ServiceModel.WorkflowServiceHost> programmgesteuert über das Objektmodell und mithilfe einer XML-Konfigurationsdatei gehostet werden.  
  
 Die Funktion "SQL-**workflowinstanzspeicher" (SqlWorkflowInstanceStore** -Klasse) implementiert nicht <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> und bietet daher keine persistenzunterstützung für permanente WCF-Dienste, die keine Workflows sind. Außerdem implementiert er auch den <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> nicht und bietet somit keine Persistenzunterstützung für 3.x-Workflows. Die Funktion unterstützt Persistenz nur für Workflows und Workflowdienste für WF 4.0 (und höher). Die Funktion unterstützt ausschließlich SQL Server 2005-Datenbanken und SQL Server 2008-Datenbanken.  
  
 In den Themen in diesem Abschnitt werden die Eigenschaften und Funktionen des SQL-Workflowinstanzspeichers beschrieben, und Sie finden Informationen zum Konfigurieren des Speichers.  
  
 Windows Server AppFabric stellt einen eigenen Instanzspeicher und eigene Tools bereit, um die Konfiguration und die Verwendung des Instanzspeichers zu vereinfachen. Weitere Informationen finden Sie unter [Windows Server App Fabric-Instanzspeicher](/previous-versions/appfabric/ff383417(v=azure.10)). Weitere Informationen zum App-Fabric SQL Server Persistenzdatenbank finden Sie unter [App Fabric SQL Server Persistenzdatenbank](/previous-versions/appfabric/ee790819(v=azure.10)) .  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
- [Eigenschaften des SQL-Workflowinstanzspeichers](properties-of-sql-workflow-instance-store.md)  
  
- [Vorgehensweise: Aktivieren der SQL-Persistenz für Workflows und Workflowdienste](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
- [Instanzaktivierung](instance-activation.md)  
  
- [Unterstützung für Abfragen](support-for-queries.md)  
  
- [Erweiterbarkeit des Speichers](store-extensibility.md)  
  
- [Security](security.md)  
  
- [SQL Server-Persistenzdatenbank](sql-server-persistence-database.md)  
  
## <a name="see-also"></a>Siehe auch

- [Persistenzbeispiele](/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100))
