---
title: Zwischenspeichern von Channels mit Send
ms.date: 03/30/2017
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
ms.openlocfilehash: 619088def1f5e443a31244516655d75d1e25c9cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503814"
---
# <a name="channel-caching-with-send"></a>Zwischenspeichern von Channels mit Send
Der <xref:System.ServiceModel.Activities.SendMessageChannelCache> ermöglicht unterschiedliche Ebenen des Zwischenspeicherns von Channels mit der <xref:System.ServiceModel.Activities.Send>-Aktivität und der <xref:System.ServiceModel.Activities.SendParametersContent>-Aktivität für Benutzer. Das Zwischenspeichern auf Instanzebene ist standardmäßig aktiviert, und in diesem Beispiel werden die folgenden Funktionen veranschaulicht:  
  
1.  Freigeben eines <xref:System.ServiceModel.Activities.SendMessageChannelCache> über eine Anwendungsdomäne hinweg.  
  
2.  Deaktivieren Sie des Zwischenspeicherns von Channels.  
  
3.  Freigeben eines <xref:System.ServiceModel.Activities.SendMessageChannelCache> in Workflowinstanzen in einem <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Erweiterung, <xref:System.ServiceModel.Activities.Send>-Aktivität, <xref:System.ServiceModel.Activities.Receive>-Aktivität, <xref:System.ServiceModel.Activities.ReceiveContent>-Aktivität und <xref:System.ServiceModel.Activities.SendReply>-Aktivität.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie die unter "\EchoWorkflowService\bin\debug generierte Anwendung "EchoWorkflowService" aus.  
  
3.  Führen Sie die unter "\EchoWorkflowClient\bin\debug" generierte Anwendung "EchoWorkflowClient" aus.  
  
4.  Der Client ruft den Echo-Vorgang für den Dienst auf, und gibt die Ergebnisse aus. Wenn die Ergebnisse ausgegeben wurden, drücken Sie die EINGABETASTE, um den Client und den Dienst zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
