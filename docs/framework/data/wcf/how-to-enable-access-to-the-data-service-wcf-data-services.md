---
title: 'Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 98584405b0c6a86f424f4bf82e29ea33197dfbeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)
In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] müssen Sie den Zugriff auf die von einem Datendienst verfügbar gemachten Ressourcen explizit gewähren. Daher müssen Sie nach der Erstellung eines neuen Datendiensts explizit den Zugriff auf einzelne Ressourcen als Entitätenmengen bereitstellen. In diesem Thema wird gezeigt, wie So aktivieren Sie lesen und Schreibzugriff auf fünf der Entität festgelegt wird, in der Northwind-Datendienst, die erstellt wird, beim Durchführen der [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Da die <xref:System.Data.Services.EntitySetRights>-Enumeration mit dem <xref:System.FlagsAttribute> definiert wird, können Sie mehrere Berechtigungen für eine einzelne Entitätenmenge mithilfe eines logischen OR-Operators angeben.  
  
> [!NOTE]
>  Jeder Client, der auf die ASP.NET-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen. Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst schützen, um nicht autorisierten Zugriff auf Ressourcen zu verhindern. Weitere Informationen finden Sie unter [NIB: ASP.NET-Sicherheit](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d).  
  
### <a name="to-enable-access-to-the-data-service"></a>So aktivieren Sie den Zugriff auf den Datendienst  
  
-   Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Dies ermöglicht Clients, Lese- und Schreibzugriff auf die `Orders`-Entitätenmenge und die `Order_Details`-Entitätenmenge sowie Lesezugriff auf die `Customers`-Entitätenmenge zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Entwickeln Sie einen WCF-Datendienst unter IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
