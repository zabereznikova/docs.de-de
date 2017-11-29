---
title: Suchrouterdienst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 663ece44a18ae073412376bc11a1d70927740e8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-router-service"></a>Suchrouterdienst
In diesem Beispiel wird veranschaulicht, wie Suchnachrichten an einen anderen Endpunkt weitergeleitet werden.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Suchrouting  
  
## <a name="discussion"></a>Diskussion  
 Suchrouting ist in einem Szenario nützlich, in dem ein Client mit einem Proxy nach einem Dienst sucht und dieser Dienst für den Proxy nicht verfügbar ist, der Proxy jedoch einen anderen Proxy kennt. Dieser Proxy kann das Suchpaket vom Client an den zweiten Proxy weiterleiten. Der zweite Proxy kann nach dem Dienst suchen und die Antworten an den ursprünglichen Client zurückgeben.  
  
 In diesem Beispiel sendet ein Client eine Nachricht an eine Suchroutingkomponente. Diese Nachricht wird an einen bestimmten Endpunkt des Suchrouters gesendet. Der Router leitet die Nachricht dann an einen UDP-Multicastendpunkt weiter. Die Überprüfungsnachricht wird an den Multicastendpunkt gesendet, und ein Dienst, der eine UDP-Multicastadresse überwacht, reagiert auf diesen Suchrouter. Der Suchrouter sammelt die Antworten und sendet sie an den Client zurück.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Erstellen Sie das Beispiel.  
  
2.  Führen Sie die ausführbare DiscoveryRouter-Datei aus.  
  
3.  Führen Sie die ausführbare Dienstdatei aus dem Buildverzeichnis aus.  
  
4.  Führen Sie die ausführbare Clientanwendung aus. Beachten Sie, dass der Client den Dienst sucht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
