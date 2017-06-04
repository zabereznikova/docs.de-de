---
title: "Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Konfigurieren"
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)
In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] müssen Sie den Zugriff auf die von einem Datendienst verfügbar gemachten Ressourcen explizit gewähren.  Daher müssen Sie nach der Erstellung eines neuen Datendiensts explizit den Zugriff auf einzelne Ressourcen als Entitätenmengen bereitstellen.  Dieses Thema zeigt, wie der Lese\- und Schreibzugriff für fünf der Entitätenmengen im Northwind\-Datendienst aktiviert wird, der erstellt wird, wenn Sie den [\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) abschließen. Da die <xref:System.Data.Services.EntitySetRights>\-Enumeration mit dem <xref:System.FlagsAttribute> definiert wird, können Sie mehrere Berechtigungen für eine einzelne Entitätenmenge mithilfe eines logischen ODER\-Operators angeben.  
  
> [!NOTE]
>  Jeder Client, der auf die ASP.NET\-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen.  Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst schützen, um nicht autorisierten Zugriff auf Ressourcen zu verhindern.  Weitere Informationen finden Sie unter [NIB: ASP.NET Security](http://msdn.microsoft.com/de-de/04b37532-18d9-40b4-8e5f-ee09a70b311d).  
  
### So aktivieren Sie den Zugriff auf den Datendienst  
  
-   Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`\-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Dies ermöglicht Clients, Lese\- und Schreibzugriff auf die `Orders`\-Entitätenmenge und die `Order_Details`\-Entitätenmenge sowie Lesezugriff auf die `Customers`\-Entitätenmenge zu erhalten.  
  
## Siehe auch  
 [Vorgehensweise: Entwickeln eines WCF\-Datendiensts, der auf IIS ausgeführt wird](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)   
 [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)