---
title: Ermitteln eines Diensts mit UniqueListenUriMode (Beispiel)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48b49def3f8f009eeb4ffa0204e9c616b5acfec7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a>Ermitteln eines Diensts mit UniqueListenUriMode (Beispiel)
In diesem Beispiel wird veranschaulicht, wie ein Dienst ermittelt wird, dessen <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.ListenUriMode.Unique> festgelegt ist. Wenn die <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.ListenUriMode.Unique> festgelegt ist, wird die Eindeutigkeit des ListenUri sichergestellt, indem entweder der Port eindeutig festgelegt wird oder der Pfad durch Anhängen einer GUID eindeutig festgelegt wird.  
  
### <a name="features-on-the-service"></a>Funktionen des Diensts  
 Die <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A>-Eigenschaft wird für den TCP-Endpunkt auf <xref:System.ServiceModel.Description.ListenUriMode.Unique> festgelegt. Der Dienst wird dann über eine <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Endpunkt ermittelbar gemacht.  
  
### <a name="features-on-the-client"></a>Funktionen des Clients  
 Dieser Client stellt mithilfe der `Via.Uri`-Methode eine Verbindung mit dem Dienst mit dem richtigen <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> her. Es wird dann eine Abfrage an die von der Methode zurückgegebenen <xref:System.ServiceModel.Discovery.FindResponse> gesendet, ob ein gültiger <xref:System.ServiceModel.Endpoint.ListenUri%2A> darin enthalten ist und dieser sich vom `Address.Uri` unterscheidet. Die entsprechenden Informationen werden dann an die `InvokeCalculatorService`-Methode übergeben. In der `InvokeCalculatorService`-Methode wurde der <xref:System.ServiceModel.Endpoint.ListenUri%2A> vom Aufrufer übergeben. Danach wird dem Clientendpunkt ein `ClientViaBehavior` mit dem richtigen `Via.Uri` hinzugefügt.  
  
##### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie UniqueListenUriMode.sln mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Führen Sie die Dienstanwendung aus, die im Ordner [Projektmappenbasisverzeichnis]\service\bin\debug generiert wird.  
  
4.  Führen Sie die Clientanwendung aus, die im Ordner [Projektmappenbasisverzeichnis]\Client\bin\debug generiert wird.  
  
     Der Client sucht den ausgeführten Dienst und schreibt die vom Endpunkt des Diensts veröffentlichten Metadaten in die Konsole.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a>Siehe auch
