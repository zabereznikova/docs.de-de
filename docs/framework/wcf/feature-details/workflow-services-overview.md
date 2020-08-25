---
title: Übersicht über Workflow Dienste
ms.date: 03/30/2017
ms.assetid: e536dda3-e286-441e-99a7-49ddc004b646
ms.openlocfilehash: 7055ea6e6b6d6a5d7bef8d5ff465d2eb0c838bf6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812184"
---
# <a name="workflow-services-overview"></a>Übersicht über Workflow Dienste

Workflow Dienste sind WCF-basierte Dienste, die mithilfe von Workflows implementiert werden. Workflow Dienste sind Workflows, die Messaging Aktivitäten verwenden, um Windows Communication Foundation (WCF)-Nachrichten zu senden und zu empfangen. Mit .NET Framework 4.5 werden eine Reihe von Messagingaktivitäten eingeführt, mit denen Sie Nachrichten aus einem Workflow senden oder darin empfangen können. Weitere Informationen zu Messaging Aktivitäten und deren Verwendung zum Implementieren verschiedener Nachrichtenaustausch Muster finden Sie unter [Messaging Aktivitäten](messaging-activities.md).

## <a name="benefits-of-using-workflow-services"></a>Vorteile der Verwendung von Workflow Diensten

Da Anwendungen immer stärker dezentral verwendet werden, sind häufiger einzelne Dienste für das Aufrufen anderer Dienste zuständig, um einige Arbeitsaufgaben zu verteilen. Das Implementieren dieser Aufrufe als asynchrone Vorgänge führt zu einem höheren Maß an Komplexität im Code. Zuusätzliche Komplexität ergibt sich aus der Fehlerbehandlung aufgrund der Behandlung von Ausnahmen und der Bereitstellung ausführlicher Nachverfolgungsinformationen. Einige Dienste verfügen häufig über eine lange Ausführungszeit und können beim Warten auf Eingaben wertvolle Systemressourcen binden. Aufgrund dieser Probleme sind verteilte Anwendungen häufig sehr komplex und schwierig zu schreiben und zu verwalten. Workflows sind eine natürliche Möglichkeit, die Koordination asynchroner Arbeit auszudrücken, besonders Aufrufe externer Dienste. Workflows sind auch effektiv, wenn es um die Darstellung Geschäftsprozesse mit langer Laufzeit geht. Diese Qualitäten machen den Workflow zu einem nützlichen Instrument beim Erstellen von Diensten in einer verteilten Umgebung.

## <a name="implementing-a-workflow-service"></a>Implementieren eines Workflow Dienstanbieter

Wenn Sie einen WCF-Dienst implementieren, definieren Sie eine Reihe von Verträgen, in denen der Dienst und die gesendeten und empfangenen Daten beschrieben werden. Die Daten werden als Datenverträge und Nachrichtenverträge dargestellt. Sowohl WCF-Dienste als auch Workflowdienste verwenden Datenvertrags- und Nachrichtenvertragsdefinitionen als Teil ihrer Dienstbeschreibungen. Der Dienst selbst macht Metadaten (im WSDL-Format) verfügbar, um die Vorgänge des Diensts zu beschreiben. Bei WCF definieren Dienst- und Vorgangsverträge den Dienst und seine unterstützten Vorgänge. In einem Workflowdienst sind diese Verträge jedoch Teil des eigentlichen Geschäftsprozesses. Sie werden in den Metadaten von einem Prozess verfügbar gemacht, der als Vertragsrückschluss bezeichnet wird. Wenn ein Workflowdienst mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, wird die Workflowdefinition untersucht, und basierend auf den im Workflow gefundenen Messagingaktivitäten wird ein Vertrag generiert. Zum Generieren des Vertrags werden insbesondere die folgenden Aktivitäten und Eigenschaften verwendet:

<xref:System.ServiceModel.Activities.Receive> -Aktivität

- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>

- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>

- <xref:System.ServiceModel.Activities.Receive.Action%2A>

<xref:System.ServiceModel.Activities.SendReply> -Aktivität

- <xref:System.ServiceModel.Activities.SendReply.Action%2A>

<xref:System.ServiceModel.Activities.TransactedReceiveScope> -Aktivität

Das Endergebnis des Vertrags Rückschlusses ist eine Beschreibung des Diensts, die die gleichen Datenstrukturen wie WCF-Dienste und Vorgangs Verträge verwendet. Diese Informationen werden dann verwendet, um WSDL für den Workflowdienst verfügbar zu machen.

> [!NOTE]
> Mit [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] können Sie ohne zusätzliche Toolunterstützung keine Workflowdienste schreiben, die eine vorhandene Vertragsdefinition verwenden. Workflowdienstverträge werden mithilfe des oben erläuterten Vertragsrückschlussprozesses erstellt. Nachrichtenverträge und Datenverträge werden jedoch vollständig unterstützt.

## <a name="workflow-services-and-msmq-based-bindings"></a>Workflow Dienste und MSMQ-basierte Bindungen

WCF definiert zwei MSMQ-basierten Bindungen, und zwar <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  MSMQ-basierte Bindungen werden häufig in Verbindung mit Workflowdiensten verwendet, weil diese Dienste für lange Laufzeiten ausgelegt sind. Die MSMQ-basierten Bindungen verfügen über eine `ValidityDuration`-Eigenschaft, die angibt, wie lange MSMQ-Nachrichten voraussichtlich gültig sind. Aufgrund der langfristigen Auslegung von Workflowdiensten ist es möglich, dass die Gültigkeitsdauer einer MSMQ-Nachricht abläuft, bevor der Workflowdienst diese verarbeiten kann. Es ist daher sehr wichtig, die Gültigkeitsdauer einer MSMQ-Bindung auf einen passenden Wert festzulegen. Dieser Wert muss basierend auf dem Workflows und der jeweiligen Verarbeitung von Nachrichten ausgewählt werden. Wenn Sie z. B. über einen Workflow mit einer <xref:System.ServiceModel.Activities.Receive>-Aktivität gefolgt von einer benutzerdefinierten Aktivität mit einer Ausführungsdauer von 10 Minuten verfügen, auf die dann eine weitere <xref:System.ServiceModel.Activities.Receive>-Aktivität folgt, ist der richtige Wert für `ValidityDuration` höher als 10 Minuten.

## <a name="hosting-a-workflow-service"></a>Hosting eines Workflow Diensts

Wie bei WCF-Diensten müssen Workflow Dienste gehostet werden. WCF-Dienste verwenden die <xref:System.ServiceModel.ServiceHost> -Klasse zum Hosten von Diensten und Workflow Diensten <xref:System.ServiceModel.Activities.WorkflowServiceHost> , die zum Hosten von-Diensten Wie bei WCF-Diensten können Workflow Dienste auf unterschiedlichste Weise gehostet werden, z. b.:

- In einer verwalteten .NET Framework-Anwendung.

- in Internetinformationsdienste (IIS).

- Unter dem Windows-Prozessaktivierungsdienst (WAS)

- Unter einem verwalteten Windows-Dienst

Workflow Dienste, die in einer verwalteten .NET Framework-Anwendung oder einem verwalteten Windows-Dienst gehostet werden, erstellen eine Instanz der <xref:System.ServiceModel.Activities.WorkflowServiceHost> -Klasse und übergeben ihr eine Instanz der-Klasse <xref:System.ServiceModel.Activities.WorkflowService> , die die Workflow Definition innerhalb der- <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> Eigenschaft enthält. Eine Workflowdefinition, die Messagingaktivitäten enthält, wird als Workflowdienst verfügbar gemacht.

Um einen Workflowdienst unter IIS zu hosten, fügen Sie die XAMLX-Datei mit der Workflowdienstdefinition in ein virtuelles Verzeichnis ein. Ein Standard Endpunkt (mit <xref:System.ServiceModel.BasicHttpBinding> ) wird automatisch erstellt, um weitere Informationen zu erhalten. Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md). Sie können auch eine Web.config-Datei in das virtuelle Verzeichnis einfügen, um eigene Endpunkte anzugeben. Wenn sich die Workflowdefinition in einer Assembly befindet, können Sie eine SVC-Datei in das virtuelle Verzeichnis und die Workflowassembly in das Verzeichnis "App_Code" einfügen. In der SVC-Datei muss die Diensthostfactory und die Klasse angegeben sein, die den Workflowdienst implementiert. Das folgende Beispiel zeigt, wie Sie die Diensthostfactory und die Klasse angeben, die den Workflowdienst implementiert.

```aspx-csharp
<%@ServiceHost Factory="System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory"
Service="EchoService"%>
```
