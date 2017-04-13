---
title: "Kryptografische Flexibilit&#228;t in WCF-Sicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# Kryptografische Flexibilit&#228;t in WCF-Sicherheit
In diesem Beispiel wird gezeigt, wie ein Standard\-\/benutzerdefinierter Algorithmus angegeben wird, um eine agile Kryptografieimplementierung in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Client und \-Dienst bereitzustellen.  Das Beispiel besteht aus den folgenden Projekten:  
  
 Dienst  
 Dies ist ein selbst gehosteter [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst, mit dem die `ICalculator`\-Schnittstelle implementiert und der Endpunkt mit der <xref:System.ServiceModel.WsHttpBinding> sichergestellt wird, wobei die sichere Sitzung und zuverlässige Sitzung deaktiviert wurde.  Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`\-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.  
  
 Client  
 Hierbei handelt es sich um einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client, der nach erfolgreicher Authentifizierung auf den Dienst zugreift.  Er ruft die Vorgänge auf, die von der `ICalculator`\-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden.  Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`\-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.  
  
### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die CryptoAgility\-Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Öffnen Sie den [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], und navigieren Sie zum Verzeichnis \\WCF\\Basic\\Security\\CryptoAgility\\Service\\bin. Führen Sie die SERVICE.EXE\-Datei mit Administratorberechtigungen aus, indem Sie mit der rechten Maustaste auf service.exe klicken und **Als Administrator ausführen** auswählen.  
  
4.  Navigieren Sie zum Verzeichnis \\WCF\\Basic\\Security\\CryptoAgility\\Client\\bin, und führen Sie die CLIENT.EXE\-Datei wie gewohnt aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## Siehe auch  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)