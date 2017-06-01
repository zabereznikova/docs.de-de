---
title: "Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation
Mit dem folgenden Verfahren werden die Schritte beschrieben, die durchgeführt werden müssen, um ASP.NET\-Webdienst\-Clientcode zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu migrieren.  
  
## Vorgehensweise  
  
#### So migrieren Sie ASP.NET\-Webdienst\-Clientcode zu WCF  
  
1.  Stellen Sie sicher, dass für den Client ein umfassender Satz an Tests vorhanden ist.  
  
2.  Verwenden Sie Visual Studio 2005, um ein Upgrade der Clientanwendung auf .NET 2.0 durchzuführen.Führen Sie die Tests aus.  
  
3.  Entfernen Sie ASP.NET\-Clientcode aus dem Clientprojekt.Dieser Code wird mithilfe des WSDL.exe\-Tools in Modulen generiert.  
  
4.  Generieren Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientcode mit [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).Fügen Sie diesen Code zum Clientprojekt hinzu, und fügen Sie die Konfigurationsausgabe in die bestehende Konfigurationsdatei des Clients ein.  
  
5.  Kompilieren Sie die Anwendung.Korrigieren Sie die Kompilierungsfehler, indem Sie Verweise auf ehemalige ASP.NET\-Clienttypen durch Verweise auf die neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clienttypen ersetzen.  
  
6.  Führen Sie die Tests aus.  
  
## Siehe auch  
 [Vorgehensweise: Migrieren von ASP.NET\-Webdienstcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)