---
title: Beispiel für die asynchrone Suche
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1545791eceae6d4651ca5299a84623466e8b4976
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="asynchronous-find-sample"></a>Beispiel für die asynchrone Suche
In diesem Beispiel wird gezeigt, wie der asynchrone Suchvorgang aus einer Clientanwendung verwendet wird.  
  
## <a name="sample-details"></a>Beispieldetails  
 Der Vorteil dieses Entwurfsmusters besteht darin, dass der Client in Folge der Suchanforderung asynchron über die gefundenen Endpunkte benachrichtigt wird. Öffnen Sie die Datei Client.cs, um die Funktionsweise zu sehen. Beachten Sie, dass zwei Delegaten an den Ereignishandlern des <xref:System.ServiceModel.Discovery.DiscoveryClient>-Objekts angefügt sind. Ein Delegat wird aufgerufen, wenn ein <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>-Ereignis ausgelöst wird, und ein anderer Delegat wird jedes Mal aufgerufen, wenn ein <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>-Ereignis ausgelöst wird. Im Beispiel wird gezeigt, wie Sie dieses Muster in der Anwendung verwenden können.  
  
> [!NOTE]
>  In diesem Beispiel werden HTTP-Endpunkte verwendet. Zur Ausführung müssen die richtigen URL-ACLs hinzugefügt werden. Weitere Informationen finden Sie unter [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt. Es empfiehlt sich, die folgenden Argumente durch die Domäne und den Benutzernamen zu ersetzen, wenn der Befehl nicht funktioniert. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie die Datei AsyncFind.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Öffnen Sie eine [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung, und navigieren Sie zum Verzeichnis \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug oder \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug, und führen Sie Service.exe aus.  
  
4.  Nachdem der Dienst gestartet wurde, navigieren Sie zum Verzeichnis \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug oder WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug, und führen Sie Client.exe aus.  
  
5.  Beobachten Sie, ob der Client den Dienst finden und aufrufen kann.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a>Siehe auch
