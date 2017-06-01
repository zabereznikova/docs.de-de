---
title: "CustomDiscoveryMetadata | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# CustomDiscoveryMetadata
In diesem Beispiel wird gezeigt, wie benutzerdefinierte XML\-Metadaten in die Suchmetadaten eines sichtbaren Endpunkts eingefügt werden, der von einem Dienst verfügbar gemacht wird.  Im Beispiel wird außerdem erläutert, wie ein Client nach dem Dienst suchen und diese benutzerdefinierten Daten extrahieren kann.  Das folgende Beispiel besteht aus zwei Projekten, Dienst und Client.  
  
## Dienst  
 In der `main`\-Methode wird im Beispiel gezeigt, dass ein Objekt des Typs <xref:System.Xml.Linq.XElement> mit den gewünschten Feldern aufgefüllt und dem <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> hinzugefügt wird.  Das <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> wird einem bestimmten Endpunkt hinzugefügt.  Wenn nach diesem Endpunkt gesucht wird, enthalten die Suchmetadaten die benutzerdefinierten Daten, die hier hinzugefügt wurden.  
  
## Client  
 Das Beispiel zeigt, dass die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>\-Methode für einen <xref:System.ServiceModel.Discovery.DiscoveryClient> aufgerufen wird.  Die entsprechende <xref:System.ServiceModel.Discovery.FindResponse> wird danach für die entsprechenden und erwarteten XML\-Elemente abgefragt.  Diese Elemente werden dann in der Konsole angezeigt.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zuerst die Dienstanwendung aus, die unter \[Projektmappen\-Basisverzeichnis\]\\service\\bin\\debug generiert wurde, und führen Sie danach die Clientanwendung aus, die unter \[Projektmappen\-Basisverzeichnis\]\\Client\\bin\\debug generiert wurde.  
  
3.  Beachten Sie, dass der Dienst online geschaltet wird, der Client nach dem Dienst sucht und die im Endpunkt veröffentlichten Metadaten anzeigt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## Siehe auch