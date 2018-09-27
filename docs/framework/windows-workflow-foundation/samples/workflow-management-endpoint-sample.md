---
title: Workflowverwaltungsendpunkt (Beispiel)
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 398ace1c198f0db0268c44083ccc98c5ba2d2c7f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399124"
---
# <a name="workflow-management-endpoint-sample"></a>Workflowverwaltungsendpunkt (Beispiel)
In diesem Beispiel wird gezeigt, wie ein Workflowsteuerungsendpunkt verwendet werden kann, um Workflows sowohl lokal als auch remote zu erstellen und auszuführen. Das Beispiel veranschaulicht, wie ein Steuerungsendpunkt gehostet wird und Clients geschrieben werden, die den Steuerungsendpunkt aufrufen, um die Instanz eines Workflows zu erstellen und auszuführen. Der Workflow ist kein Dienst.  
  
 Auf der Dienstseite des Beispiels wird ein Workflow mit WorkflowServiceHost gehostet und WorkflowControlEndpoint hinzugefügt, damit Clients Steuerungsvorgänge (Anhalten, Starten usw.) ausführen können. Ein benutzerdefinierter CreationEndpoint wird ebenfalls hinzugefügt, damit der Workflow erstellt werden kann. Der Dienst verwendet dann diese Endpunkte, um den Workflow in einem angehaltenen Zustand zu starten und anschließend fortzusetzen. Der Client führt die gleichen Vorgänge aus, jedoch vom Clientcode aus. Für Weitere Informationen zu diesen finden Sie unter Schnittstellen [Workflowsteuerungsendpunkt](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md).  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorrechten aus.  
  
2.  Öffnen Sie die Projektmappe "ManagementEndpoint.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Um die Projektmappe zu erstellen, drücken Sie STRG + UMSCHALT + B, oder wählen Sie **Projektmappe** aus der **erstellen** Menü.  
  
4.  Starten Sie die Anwendung "ManagementEndpoint.exe".  
  
5.  Starten Sie die Anwendung "Client.exe".  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`