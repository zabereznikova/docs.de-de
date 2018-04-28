---
title: Übersicht über Workflowdienste
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e536dda3-e286-441e-99a7-49ddc004b646
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b0c59c0688fca53a7c7623330f3fdba4f5defd88
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-services-overview"></a>Übersicht über Workflowdienste
Bei Workflowdiensten handelt es sich um Dienste, die auf [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basieren und mithilfe von Workflows implementiert werden. Workflowdienste sind Workflows, die die Messagingaktivitäten zum Senden und Empfangen von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Nachrichten verwenden. Mit .NET Framework 4.5 werden eine Reihe von Messagingaktivitäten eingeführt, mit denen Sie Nachrichten aus einem Workflow senden oder darin empfangen können. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] messagingaktivitäten und wie sie verwendet werden können, zum Implementieren verschiedener Nachrichtenaustauschmuster finden Sie unter [Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/messaging-activities.md).  
  
## <a name="benefits-of-using-workflow-services"></a>Vorteile der Verwendung von Workflowdiensten  
 Da Anwendungen immer stärker dezentral verwendet werden, sind häufiger einzelne Dienste für das Aufrufen anderer Dienste zuständig, um einige Arbeitsaufgaben zu verteilen. Das Implementieren dieser Aufrufe als asynchrone Vorgänge führt zu einem höheren Maß an Komplexität im Code. Zuusätzliche Komplexität ergibt sich aus der Fehlerbehandlung aufgrund der Behandlung von Ausnahmen und der Bereitstellung ausführlicher Nachverfolgungsinformationen. Einige Dienste verfügen häufig über eine lange Ausführungszeit und können beim Warten auf Eingaben wertvolle Systemressourcen binden. Aufgrund dieser Probleme sind verteilte Anwendungen häufig sehr komplex und schwierig zu schreiben und zu verwalten. Workflows sind eine natürliche Möglichkeit, die Koordination asynchroner Arbeit auszudrücken, besonders Aufrufe externer Dienste. Workflows sind auch effektiv, wenn es um die Darstellung Geschäftsprozesse mit langer Laufzeit geht. Diese Qualitäten machen den Workflow zu einem nützlichen Instrument beim Erstellen von Diensten in einer verteilten Umgebung.  
  
## <a name="implementing-a-workflow-service"></a>Implementieren eines Workflowdiensts  
 Beim Implementieren eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts definieren Sie eine Reihe von Verträgen, in denen der Dienst und die von ihm gesendeten und empfangenen Daten beschrieben werden. Die Daten werden als Datenverträge und Nachrichtenverträge dargestellt. Sowohl WCF-Dienste als auch Workflowdienste verwenden Datenvertrags- und Nachrichtenvertragsdefinitionen als Teil ihrer Dienstbeschreibungen. Der Dienst selbst macht Metadaten (im WSDL-Format) verfügbar, um die Vorgänge des Diensts zu beschreiben. Bei WCF definieren Dienst- und Vorgangsverträge den Dienst und seine unterstützten Vorgänge. In einem Workflowdienst sind diese Verträge jedoch Teil des eigentlichen Geschäftsprozesses. Sie werden in den Metadaten von einem Prozess verfügbar gemacht, der als Vertragsrückschluss bezeichnet wird. Wenn ein Workflowdienst mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, wird die Workflowdefinition untersucht, und basierend auf den im Workflow gefundenen Messagingaktivitäten wird ein Vertrag generiert. Zum Generieren des Vertrags werden insbesondere die folgenden Aktivitäten und Eigenschaften verwendet:  
  
 <xref:System.ServiceModel.Activities.Receive>-Aktivität  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <!--zz <xref:System.ServiceModel.Activities.Receive.OperationContractName%2A>  --> `System.ServiceModel.Activities.Receive.OperationContractName`
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>  
  
-   <!--zz <xref:System.ServiceModel.Activities.Receive.ValueType%2A>  --> `System.ServiceModel.Activities.Receive.ValueType`
  
 <xref:System.ServiceModel.Activities.SendReply>-Aktivität  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
-   <!--zz <xref:System.ServiceModel.Activities.SendReply.ValueType%2A> -->
`xref:System.ServiceModel.Activities.SendReply.ValueType`
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität  
  
 Das Endergebnis des Vertragsrückschlusses ist eine Beschreibung des Diensts, bei der die gleichen Datenstrukturen wie für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstverträge und -Vorgangsverträge verwendet werden. Diese Informationen werden dann verwendet, um WSDL für den Workflowdienst verfügbar zu machen.  
  
> [!NOTE]
>  Mit [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] können Sie ohne zusätzliche Toolunterstützung keine Workflowdienste schreiben, die eine vorhandene Vertragsdefinition verwenden. Workflowdienstverträge werden mithilfe des oben erläuterten Vertragsrückschlussprozesses erstellt. Nachrichtenverträge und Datenverträge werden jedoch vollständig unterstützt.  
  
## <a name="workflow-services-and-msmq-based-bindings"></a>Workflowdienste und MSMQ-basierte Bindungen  
 WCF definiert zwei MSMQ-basierten Bindungen, und zwar <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  MSMQ-basierte Bindungen werden häufig in Verbindung mit Workflowdiensten verwendet, weil diese Dienste für lange Laufzeiten ausgelegt sind. Die MSMQ-basierten Bindungen verfügen über eine `ValidityDuration`-Eigenschaft, die angibt, wie lange MSMQ-Nachrichten voraussichtlich gültig sind. Aufgrund der langfristigen Auslegung von Workflowdiensten ist es möglich, dass die Gültigkeitsdauer einer MSMQ-Nachricht abläuft, bevor der Workflowdienst diese verarbeiten kann. Es ist daher sehr wichtig, die Gültigkeitsdauer einer MSMQ-Bindung auf einen passenden Wert festzulegen. Dieser Wert muss basierend auf dem Workflows und der jeweiligen Verarbeitung von Nachrichten ausgewählt werden. Wenn Sie z. B. über einen Workflow mit einer <xref:System.ServiceModel.Activities.Receive>-Aktivität gefolgt von einer benutzerdefinierten Aktivität mit einer Ausführungsdauer von 10 Minuten verfügen, auf die dann eine weitere <xref:System.ServiceModel.Activities.Receive>-Aktivität folgt, ist der richtige Wert für `ValidityDuration` höher als 10 Minuten.  
  
## <a name="hosting-a-workflow-service"></a>Hosten eines Workflowdiensts  
 Wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste müssen auch Workflowdienste gehostet werden. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste verwenden die <xref:System.ServiceModel.ServiceHost>-Klasse zum Hosten von Diensten, Workflowdienste verwenden <xref:System.ServiceModel.Activities.WorkflowServiceHost> zum Hosten von Diensten. Wie bei [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten auch, können Workflowdienste auf verschiedene Arten gehostet werden, z. B.:  
  
-   In einer verwalteten [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Anwendung  
  
-   in Internetinformationsdienste (IIS).  
  
-   Unter dem Windows-Prozessaktivierungsdienst (WAS)  
  
-   Unter einem verwalteten Windows-Dienst  
  
 Unter einer verwalteten [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Anwendung oder einem verwalteten Windows-Dienst gehostete Workflowdienste erstellen eine Instanz der <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Klasse und übergeben an diese eine Instanz von <xref:System.ServiceModel.Activities.WorkflowService>, worin die Workflowdefinition innerhalb der <xref:System.ServiceModel.Activities.WorkflowService.Body%2A>-Eigenschaft enthalten ist. Eine Workflowdefinition, die Messagingaktivitäten enthält, wird als Workflowdienst verfügbar gemacht.  
  
 Um einen Workflowdienst unter IIS zu hosten, fügen Sie die XAMLX-Datei mit der Workflowdienstdefinition in ein virtuelles Verzeichnis ein. Ein Standardendpunkt (mit <xref:System.ServiceModel.BasicHttpBinding>) wird automatisch erstellt, Weitere Informationen, finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md). Sie können auch eine Web.config-Datei in das virtuelle Verzeichnis einfügen, um eigene Endpunkte anzugeben. Wenn sich die Workflowdefinition in einer Assembly befindet, können Sie eine SVC-Datei in das virtuelle Verzeichnis und die Workflowassembly in das Verzeichnis "App_Code" einfügen. In der SVC-Datei muss die Diensthostfactory und die Klasse angegeben sein, die den Workflowdienst implementiert. Das folgende Beispiel zeigt, wie Sie die Diensthostfactory und die Klasse angeben, die den Workflowdienst implementiert.  
  
```  
<%@ServiceHost Factory=" System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory  
Service="EchoService"%>  
```
