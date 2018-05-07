---
title: CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 3e3a173d99f2ba0a2fb33dfd8f91908f03e3e871
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="customdiscoverymetadata"></a>CustomDiscoveryMetadata
In diesem Beispiel wird gezeigt, wie benutzerdefinierte XML-Metadaten in die Suchmetadaten eines sichtbaren Endpunkts eingefügt werden, der von einem Dienst verfügbar gemacht wird. Im Beispiel wird außerdem erläutert, wie ein Client nach dem Dienst suchen und diese benutzerdefinierten Daten extrahieren kann. Das folgende Beispiel besteht aus zwei Projekten, Dienst und Client.  
  
## <a name="service"></a>Dienst  
 In der `main`-Methode wird im Beispiel gezeigt, dass ein Objekt des Typs <xref:System.Xml.Linq.XElement> mit den gewünschten Feldern aufgefüllt und dem <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> hinzugefügt wird. Das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> wird einem bestimmten Endpunkt hinzugefügt. Wenn nach diesem Endpunkt gesucht wird, enthalten die Suchmetadaten die benutzerdefinierten Daten, die hier hinzugefügt wurden.  
  
## <a name="client"></a>Client  
 Das Beispiel zeigt, dass die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode für einen <xref:System.ServiceModel.Discovery.DiscoveryClient> aufgerufen wird. Die entsprechende <xref:System.ServiceModel.Discovery.FindResponse> wird danach für die entsprechenden und erwarteten XML-Elemente abgefragt. Diese Elemente werden dann in der Konsole angezeigt.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zuerst die Dienstanwendung aus, die unter [Projektmappen-Basisverzeichnis]\service\bin\debug generiert wurde, und führen Sie danach die Clientanwendung aus, die unter [Projektmappen-Basisverzeichnis]\Client\bin\debug generiert wurde.  
  
3.  Beachten Sie, dass der Dienst online geschaltet wird, der Client nach dem Dienst sucht und die im Endpunkt veröffentlichten Metadaten anzeigt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a>Siehe auch
