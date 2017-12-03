---
title: Visuelle Workflownachverfolgung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0143448f-2044-40a0-8a3d-941f6d12468b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4eca1470ede96541ffb93996e37c75c378a87456
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="visual-workflow-tracking"></a>Visuelle Workflownachverfolgung
In diesem Beispiel wird veranschaulicht, wie eine visuelle Anwendung zur Workflownachverfolgung mit der Debugfunktionalität in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] geschrieben wird.  
  
## <a name="sample-details"></a>Beispieldetails  
 Die Anwendung führt einen einfachen Flussdiagramm-Workflow (definiert in "Workflow.xaml") aus und hostet den Workflow-Designer neu, um den ausgeführten Workflow anzuzeigen. Bei Ausführung des Workflows wird die jeweils gerade ausgeführte Aktivität mit einem gelben Rahmen und Pfeil angezeigt. Außerdem werden vom Workflow generierte Nachverfolgungsdatensätze ebenfalls im Anwendungsfenster angezeigt. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]workflownachverfolgung verwendet wird, finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erneutes hosting von Workflow-Designer finden Sie unter [erneutes Hosten des Workflow-Designers](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md).  
  
 Der Workflowsimulator funktioniert mit zwei Wörterbüchern. Das eine enthält eine Zuordnung zwischen dem gerade ausgeführten Aktivitätsobjekt und der XAML-Zeilennummer, mit der die Aktivität instanziiert wird. Das andere enthält eine Zuordnung zwischen der Aktivitätsinstanz-ID und dem Aktivitätsobjekt. Wenn Nachverfolgungsdatensätze mit einem benutzerdefinierten Nachverfolgungsprofil ausgegeben werden, bestimmt die Anwendung die Instanz-ID der gerade ausgeführten Aktivität und ordnet diese erneut der XAML-Datei zu, mit der sie instanziiert wird. Der neu gehostete Workflow-Designer wird dann angewiesen, die Aktivität auf der Designeroberfläche hervorzuheben und die gleiche Methode wie der Workflowdebugger zu verwenden, d. h. einen gelben Rahmen und einen gelben Pfeil auf der linken Seite des Designers.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei "WorkflowSimulator.sln" im Beispielverzeichnis in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um das Beispiel auszuführen. Die Datei "Workflow.xaml" wird in einem neu gehosteten Workflow-Designer-Fenster angezeigt.  
  
4.  Klicken Sie auf die **Datei** Menü **Workflow ausführen...** .  
  
5.  Die gerade ausgeführte Aktivität wird wie oben beschrieben hervorgehoben, und die Nachverfolgungsdatensätze werden auf der rechten Seite des Anwendungsfensters angezeigt.  
  
6.  Nach Abschluss des Workflows können Sie durch Klicken auf einen Nachverfolgungsdatensatz prüfen, welcher Aktivität dieser entspricht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\VisualWorkflowTracking`