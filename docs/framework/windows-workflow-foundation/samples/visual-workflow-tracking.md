---
title: Visuelle Workflownachverfolgung
ms.date: 03/30/2017
ms.assetid: 0143448f-2044-40a0-8a3d-941f6d12468b
ms.openlocfilehash: 22c91a12bba148e1fa823bb2bf9b3eaf16704c46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182752"
---
# <a name="visual-workflow-tracking"></a>Visuelle Workflownachverfolgung
In diesem Beispiel wird veranschaulicht, wie eine visuelle Anwendung zur Workflownachverfolgung mit der Debugfunktionalität in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] geschrieben wird.

## <a name="sample-details"></a>Beispieldetails
 Die Anwendung führt einen einfachen Flussdiagramm-Workflow (definiert in "Workflow.xaml") aus und hostet den Workflow-Designer neu, um den ausgeführten Workflow anzuzeigen. Bei Ausführung des Workflows wird die jeweils gerade ausgeführte Aktivität mit einem gelben Rahmen und Pfeil angezeigt. Außerdem werden vom Workflow generierte Nachverfolgungsdatensätze ebenfalls im Anwendungsfenster angezeigt. Weitere Informationen zur Workflowverfolgung finden Sie unter [Workflowverfolgung und Ablaufverfolgung](../workflow-tracking-and-tracing.md). Weitere Informationen zum erneuten Hosten des Workflow-Designers finden Sie unter [Neuhosting des Workflow-Designers](../rehosting-the-workflow-designer.md).

 Der Workflowsimulator funktioniert mit zwei Wörterbüchern. Das eine enthält eine Zuordnung zwischen dem gerade ausgeführten Aktivitätsobjekt und der XAML-Zeilennummer, mit der die Aktivität instanziiert wird. Das andere enthält eine Zuordnung zwischen der Aktivitätsinstanz-ID und dem Aktivitätsobjekt. Wenn Nachverfolgungsdatensätze mit einem benutzerdefinierten Nachverfolgungsprofil ausgegeben werden, bestimmt die Anwendung die Instanz-ID der gerade ausgeführten Aktivität und ordnet diese erneut der XAML-Datei zu, mit der sie instanziiert wird. Der neu gehostete Workflow-Designer wird dann angewiesen, die Aktivität auf der Designeroberfläche hervorzuheben und die gleiche Methode wie der Workflowdebugger zu verwenden, d. h. einen gelben Rahmen und einen gelben Pfeil auf der linken Seite des Designers.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Datei WorkflowSimulator.sln aus dem Beispielverzeichnis in Visual Studio 2010.

2. Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.

3. Drücken Sie STRG+F5, um das Beispiel auszuführen. Die Datei "Workflow.xaml" wird in einem neu gehosteten Workflow-Designer-Fenster angezeigt.

4. Klicken Sie auf das Menü **Datei,** und wählen Sie **Workflow ausführen...**.

5. Die gerade ausgeführte Aktivität wird wie oben beschrieben hervorgehoben, und die Nachverfolgungsdatensätze werden auf der rechten Seite des Anwendungsfensters angezeigt.

6. Nach Abschluss des Workflows können Sie durch Klicken auf einen Nachverfolgungsdatensatz prüfen, welcher Aktivität dieser entspricht.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\VisualWorkflowTracking`
